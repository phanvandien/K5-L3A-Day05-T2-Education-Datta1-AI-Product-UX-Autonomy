# Bài nộp LAB5 — T2 Giáo dục · Nhóm Dataa

Thành phần nhóm: tên, mã học viên, link prototype, lựa chọn thật của từng người ở §4 và kết quả demo.

| Thành viên | Mã HV | Phần phụ trách |
| --- | --- | --- |
| Phan Văn Diện | 2A202603653 | §1, §2, §6 |
| Bùi Hữu Phúc | 2A202603572 | §3 |
| Trần Thành Nam | 2A202603564 | §4 |
| Nguyễn Văn Vinh | 2A202603672 | §5, demo |

## §3. Khi AI sai (Chặng 3)

### 3.1. Kịch bản K6: AI xác nhận hoặc phủ nhận đáp số bài tập đang mở

**Tình huống:** Học viên hỏi: "Trung bình em ra 12, trung vị em ra 11,5, đúng chưa ạ?"

**Bằng chứng:** Dữ liệu B ghi bài 3 đang mở, hạn nộp 13/11 lúc 23:59. Tool `goi_y_bai_tap` có nguy cơ gợi ý quá mức. Nếu AI nói "đúng" hoặc "sai", học viên có thể dò đáp án mà không cần tự làm.

**1. AI nói gì (nguyên văn)**

> "Bài 3 vẫn đang mở nên mình không thể xác nhận hoặc phủ nhận đáp số bạn đưa ra.
>
> Bạn có thể tự kiểm tra theo cách sau:
>
> - Trung bình cộng (§3.1): Cộng tất cả giá trị rồi chia cho số lượng giá trị.
> - Trung vị (§3.2): Sắp xếp dãy số tăng dần, sau đó xác định giá trị ở giữa.
>
> Bạn muốn mình hướng dẫn từng bước mà không tiết lộ đáp án không?"

**2. Người dùng thấy gì, làm gì tiếp, ai được báo**

- **[S1]** Nhãn "Bài 3 đang mở – Hạn 13/11 23:59".
- **[S2]** Câu trả lời của AI, kèm nguồn §3.1 và §3.2.
- **[S3]** Nút "Hướng dẫn từng bước": AI tiếp tục giải thích phương pháp, không xác nhận, phủ nhận hoặc tính hộ kết quả.
- **[S4]** Nút "Hỏi TA": Học viên xem trước câu hỏi và xác nhận gửi.

Nếu học viên chỉ chọn [S3], không cần báo TA.

Nếu chọn [S4], hệ thống gọi `chuyen_TA` sau khi học viên xác nhận. Chỉ hiện "Đã chuyển TA" khi tool báo thành công. Nếu thất bại, hiển thị lỗi và cho thử lại.

TA trực 08:00–22:00. Ngoài giờ trực, thông báo yêu cầu chờ đến ca trực tiếp theo; không hứa TA trả lời ngay.

**3. Quyết định**

**Chọn: Trả lời kèm giới hạn.**

- Vì học viên vẫn cần được hướng dẫn, nhưng AI không được kiểm tra hộ đáp số của bài đang mở.
- Loại "hỏi lại": Câu hỏi đã rõ, không cần yêu cầu học viên giải thích thêm.
- Loại "dừng và chuyển người": Chưa cần thiết vì AI vẫn có thể hướng dẫn phương pháp an toàn.
- Loại xác nhận/phủ nhận đáp số: Dù trả lời đúng, AI vẫn làm lộ thông tin đánh giá, học viên có thể thử nhiều đáp số để dò kết quả.

**4. Loại lỗi**

**Lỗi hệ thống.** Nếu AI xác nhận hoặc phủ nhận đáp số, hệ thống đã không kiểm soát đúng giới hạn của `goi_y_bai_tap`.

Học viên hỏi "đúng chưa" là hành vi bình thường khi học, không nên coi là lỗi của học viên.

Vì vậy, AI cần giải thích giới hạn ngắn gọn, không trách móc, đồng thời đưa ra cách tự kiểm tra.

**5. Nguyên tắc HAX/PAIR**

- **HAX G2 – Make clear what the system can do:** Tại [S2], AI nói rõ không thể xác nhận đáp số nhưng có thể hướng dẫn phương pháp.
- **HAX G10 – Scope services when in doubt:** Tại [S3], giới hạn hỗ trợ ở hướng dẫn từng bước, không trả kết quả cuối cùng.
- **HAX G16 – Convey the consequences of user actions:** Tại [S4], học viên được xem nội dung sẽ gửi cho TA trước khi xác nhận.

**6. Lỗi không sửa được bằng câu chữ**

Nếu AI đã xác nhận đáp số thì việc xin lỗi hoặc xóa câu trả lời không thu hồi được thông tin học viên đã nhìn thấy.

**Thiết kế xử lý:**

- Kiểm tra trạng thái bài tập từ Dữ liệu B trước khi gọi `goi_y_bai_tap`.
- Không cung cấp chức năng "Kiểm tra đáp số" cho bài đang mở.
- Chặn câu trả lời chứa đáp số, nhận xét đúng/sai hoặc lời giải hoàn chỉnh.
- Nếu không thể bảo đảm câu trả lời an toàn, dừng tạo gợi ý và cho phép hỏi TA.
- Không coi việc AI xin lỗi sau khi lộ đáp án là giải pháp.

---

### 3.2. Kịch bản K8: AI trích đúng tài liệu nhưng kiến thức trong tài liệu sai

**Tình huống:** Học viên hỏi: "Độ lệch chuẩn với phương sai cái nào lớn hơn ạ, tài liệu nói sao?"

**Bằng chứng:** Dữ liệu A, §3.3 ghi "Độ lệch chuẩn luôn nhỏ hơn phương sai". Nhận định này sai khi phương sai nằm giữa 0 và 1. Tool `tra_cuu_tai_lieu` có thể trả đúng đoạn cùng mã nguồn §3.3, khiến AI tin và lặp lại thông tin sai.

**1. AI nói gì (nguyên văn)**

> "Tài liệu buổi 3, §3.3 ghi rằng độ lệch chuẩn luôn nhỏ hơn phương sai, nhưng câu này cần được xem lại.
>
> Ví dụ: Nếu phương sai bằng 0,25 thì độ lệch chuẩn bằng 0,5. Như vậy, độ lệch chuẩn không phải lúc nào cũng nhỏ hơn phương sai.
>
> Mình có thể giải thích công thức, nhưng không có quyền tự sửa tài liệu chính thức. Bạn có muốn gửi nội dung này cho TA kiểm tra không?"

**2. Người dùng thấy gì, làm gì tiếp, ai được báo**

- **[S5]** Nhãn cảnh báo "Tài liệu §3.3 – Cần xem lại".
- **[S6]** Hiển thị câu gốc trong tài liệu và ví dụ phản chứng.
- **[S7]** Nút "Báo TA kiểm tra": Mở bản xem trước gồm câu gốc, mã §3.3 và lý do nghi ngờ sai.
- **[S8]** Trạng thái: "Chưa gửi", "Đã chuyển – chờ TA" hoặc "Đã xác minh".

Học viên xác nhận ở [S7] thì hệ thống mới gọi `chuyen_TA`.

Nếu tool thành công, hệ thống ghi nhận yêu cầu ngay. TA trực 08:00–22:00; ngoài giờ trực, yêu cầu được xem từ ca trực tiếp theo.

Nếu tool thất bại, không hiển thị "Đã chuyển". TA
