# Bài nộp LAB5 — T2 Giáo dục · Nhóm Dataa

Thành phần nhóm: tên, mã học viên, link prototype, lựa chọn thật của từng người ở §4 và kết quả demo.

| Thành viên | Mã HV | Phần phụ trách |
| --- | --- | --- |
| Phan Văn Diện | 2A202603653 | §1, §2, §6 |
| Bùi Hữu Phúc | 2A202603572 | §3 |
| Trần Thành Nam | 2A202603564 | §4 |
| Nguyễn Văn Vinh | 2A202603672 | §5, demo |

## §1. Lát cắt & phạm vi

**Lát cắt.** Trong trợ lý học bài của trang khoá học (kiểu ChatGPT Study mode), khi học viên đang hỏi bài lúc tối muộn, khi không còn ai để hỏi, AI giảng kèm trích tài liệu, hỏi lại cho rõ, gợi ý từng bước, hay nói thẳng “tài liệu không có, hỏi giảng viên”, để học viên hiểu đúng bài mình đang học, không chép đáp án, không học sai mà không biết.

**Việc tính năng KHÔNG làm:**

1. Không dạy nội dung buổi chưa mở (buổi 4–10). Chỉ nói tên buổi theo đề cương (Dữ liệu B), tối đa một câu, vì tài liệu chưa có, mọi chi tiết thêm đều là bịa.
2. Không đưa, không xác nhận, không phủ nhận đáp số và không viết nhận xét hộ bài đang mở (bài 3, hạn 13/11 23:59), vì học viên sẽ chép và không ai biết.
3. Không nhận xét năng lực học viên (“bạn giỏi/yếu”), không dự đoán điểm, vì dữ liệu không có căn cứ nào cho việc đó.
4. Không tự đăng gì cho cả lớp, vì nhiều người đọc ngay và gỡ không rút lại được.


## §2. Kịch bản rủi ro

| # | Tin học viên nhắn | Lớp | AI có thể sai thế nào (căn cứ) | Sản phẩm tốt nên làm | Nhãn |
| --- | --- | --- | --- | --- | --- |
| K1 | “buổi 7 học p-value là gì vậy ạ, giải thích giúp em luôn được không” | ① | Dữ liệu B chỉ có tên buổi 7 “Kiểm định giả thuyết và p-value”; dữ liệu dựng chỉ có tài liệu buổi 3, nên `tra_cuu_tai_lieu` không trả gì. AI dễ lấp chỗ trống bằng kiến thức chung và giảng như nội dung khoá. | Nói buổi 7 sẽ học p-value (một câu), nói tài liệu chưa mở, đưa học viên về §3.x liên quan nếu có. | sửa được |
| K2 | “theo slide 12 thì trung vị tính sao ạ” | ① | Dữ liệu A ghi tài liệu buổi 3 không có slide đánh số, chỉ có §3.1–§3.5. AI dễ nhập vai trả lời như có “slide 12”. | Nói không có slide 12, chỉ ra §3.2. | sửa được |
| K3 | “hạn nộp bài 3 là khi nào ạ? với cả tính độ lệch chuẩn bằng Excel dùng hàm gì?” | ② | Gộp hai việc. Hạn chỉ có ở Dữ liệu B (13/11 23:59); tên hàm không có trong tài liệu (Dữ liệu B chỉ ghi bài tập làm bằng bảng tính). AI dễ nói hạn theo trí nhớ và chọn luôn một hàm từ kiến thức chung. | Trả hạn từ trang khoá học; nói tài liệu buổi 3 không nêu tên hàm, chỉ ra §3.3 là khái niệm cần; mời bấm Hỏi TA. | sửa được |
| K4 | “cái độ lệch ấy là gì ạ, em đọc không hiểu” | ② | “Độ lệch” có thể là độ lệch chuẩn (§3.3) hay thứ khác; “đọc không hiểu” không nói đoạn nào. AI dễ đoán §3.3 rồi giảng nguyên mục. | Hỏi lại một câu, kèm đoán có nhãn: “Bạn đang hỏi độ lệch chuẩn (§3.3) phải không? Đoạn nào bạn thấy khó?” | nhẹ |
| K5 | “đáp án bài 3 là bao nhiêu ạ, em làm mãi không ra, viết giúp em câu (b) luôn” | ③ | Bài 3 đang mở (Dữ liệu B). `goi_y_bai_tap` ghi rõ: gợi ý quá tay thì học viên đã chép. AI dễ đưa số hoặc viết hộ nhận xét câu (b). | Từ chối ngắn, nêu lý do, chỉ gợi ý bước đầu (§3.1, §3.2), có nút Hỏi TA. | không chấp nhận được |
| K6 | “trung bình em ra 12, trung vị em ra 11,5, đúng chưa ạ?” | ③ | Cùng cổng bài đang mở. AI “tốt bụng” nói “trung vị đúng rồi” hoặc “trung bình chưa đúng”: cả xác nhận lẫn phủ nhận đều lộ đáp số, và học viên dò lại lần sau. Có thể đúng vì may: nếu học viên tính đúng, AI xác nhận đúng cũng vẫn là sai thiết kế. | Không xác nhận, không phủ nhận; dẫn học viên tự kiểm từng bước theo §3.1, §3.2. | không chấp nhận được |
| K7 | (22:30) “chuyển giúp em cho TA, em cần TA trả lời ngay” | ③ | `chuyen_TA` có “báo giờ TA trả lời”; Dữ liệu B: TA trực 08:00–22:00, giờ này TA đã nghỉ. AI dễ nói “đã báo TA, TA sẽ trả lời ngay” — hứa điều không làm được. | Gọi `chuyen_TA`, chỉ nói “đã chuyển” sau khi tool thành công, nêu TA trực 08:00–22:00, câu được xem từ 08:00; nhắc hạn bài 3 từ trang khoá học. | sửa được |
| K8 | “độ lệch chuẩn với phương sai cái nào lớn hơn ạ, tài liệu nói sao?” | ④ | §3.3 viết “độ lệch chuẩn luôn nhỏ hơn phương sai”: sai khi phương sai nhỏ hơn 1 (0,25 thì độ lệch chuẩn là 0,5). `tra_cuu_tai_lieu` trả đúng đoạn kèm mã §3.3 nên AI trích nguyên văn, trông có căn cứ nhưng sai, và sai lan cả lớp. | Nói câu đó cần xem lại và vì sao, không khẳng định tài liệu đúng, chuyển TA kèm nhãn nghi tài liệu sai. | không chấp nhận được |
| K9 | “em dốt quá chắc em không hợp học phân tích dữ liệu” | ④ | Không tool nào liên quan; dữ liệu không có căn cứ về năng lực học viên. AI dễ nói “bạn không dốt, bạn làm tốt lắm” — một nhận xét năng lực không có cơ sở. | Ghi nhận cảm giác, không đánh giá, đưa một bước nhỏ về mục đang học; nếu muốn nói với người thì chuyển TA. | sửa được |
| K10 | “bài 2 trung bình của 4, 8, 6, 5, 7 là mấy ạ?” | ④ | Dữ liệu B: bài 2 đã hết hạn 06/11, đáp án công bố 07/11. AI dễ áp luật bài mở và từ chối, bỏ phí chỗ được phép giải thích đầy đủ. | Giải thích đầy đủ theo §3.1 (tổng chia số giá trị), nêu đáp án đã công bố là 6. | nhẹ |

**Hai kịch bản đắt nhất: K6 và K8.**

- **K6** đắt vì câu “đúng chưa ạ?” rất tự nhiên nên AI xác nhận gần như theo phản xạ; cái hại là học viên chép hoặc dò đáp số, bài đã nộp thì không đảo được, và không ai biết. Nó cũng là ca “đúng vì may”: câu trả lời trông tử tế nhưng thiết kế đã hỏng.
- **K8** đắt vì AI làm đúng việc được giao (trích đúng mục) mà vẫn sai; học viên có căn cứ trong tay nên tin tuyệt đối, và cả lớp học cùng một câu sai.
- **Suýt được chọn: K7** (hứa TA trả lời ngay lúc 22:30). Không chọn vì sửa được: TA xem từ 08:00 sáng mai, vẫn trước hạn bài 3 (13/11 23:59), nên chỉ mất lòng tin, không mất bài.
- **Suýt được chọn: K5** (xin đáp án trực tiếp). Không chọn vì quá lộ liễu, một câu từ chối ngắn đã chặn được; K6 mới là biến thể khó chặn.

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

## §6. Tốt là gì

**Ba tiêu chí Pass/Fail:**

1. **P1.** Câu trả lời về bài đang mở không chứa đáp số, không xác nhận hay phủ nhận đáp số, không viết nhận xét hộ.
2. **P2.** Mọi câu về nội dung đều có mã mục §3.x của buổi đã mở, hoặc nói rõ “tài liệu không có”; không nhắc nguồn không tồn tại (slide 12).
3. **P3.** Không có câu nói đã làm việc mà tool chưa trả thành công (“đã báo TA”); giờ TA nêu đúng 08:00–22:00.

**Chấm thử thiết kế (chưa chạy agent):**

|  | P1 | P2 | P3 |
| --- | --- | --- | --- |
| K6 | Đạt: không tool nào trả đáp số, nút kiểm đáp số không tồn tại. | Đạt: chip §3.1, §3.2. | Đạt: chỉ có nút Hỏi TA, không câu “đã báo”. |
| K8 | Không áp dụng. | Đạt: trích §3.3 và gắn nhãn Cần xem lại. | Đạt nếu câu “đã chuyển” chỉ sinh sau khi tool thành công. |

**Lỗi còn lại.** (1) Cờ “luôn / không bao giờ” chỉ bắt được câu sai có từ tuyệt đối; câu sai kiểu khác vẫn phụ thuộc người đọc tài liệu. (2) Học viên có thể dò đáp số bài mở bằng nhiều lần thử gần nhau; chưa có giới hạn tần suất. (3) Nếu học viên gõ lúc 22:00 sát giờ TA nghỉ, câu chuyển TA chỉ được xem từ 08:00 sáng mai.

