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

## §4. Mức tự chủ (Chặng 4)

### 4.1. Xếp mức cho bốn tool

Đây là mức tự chủ chốt cho thiết kế. Mức áp dụng cho **hành động của tool**, không có nghĩa mọi câu AI tạo ra đều được gửi đi. Trước khi trả lời, hệ thống đối chiếu tài liệu buổi đã mở và trạng thái bài tập ở Dữ liệu B. Nếu không xác định được nguồn hoặc trạng thái, AI dừng hành động có nguy cơ làm lộ đáp án và nói rõ điều chưa biết.

| Tool | Mức chốt | Sai thì ai chịu gì; đảo lại được không? | Nếu chờ người duyệt thì mất gì? Vì sao chọn mức này? | Phương án đã cân nhắc và loại |
| --- | --- | --- | --- | --- |
| `tra_cuu_tai_lieu` | **Tự làm** | Tool chỉ đọc, nên bản thân việc tra cứu không sửa dữ liệu. Nhưng nếu AI coi đoạn tìm được là chân lý và lặp câu sai ở §3.3, học viên có thể học sai (K8); thu hồi câu đã đọc không bảo đảm sửa được niềm tin. | Bắt TA duyệt mọi lần tra cứu làm học viên hỏi bài tối muộn không nhận được nguồn kịp thời. Cho tra cứu ngay, chỉ trả mục có thật của buổi đã mở; không thấy thì nói không thấy. Đoạn có dấu hiệu mâu thuẫn như §3.3 phải gắn nhãn “Cần xem lại”, nêu lý do và mời báo TA, không khẳng định đúng. | Loại **cần TA duyệt mọi kết quả tra cứu** vì chờ quá đắt cho cả câu hỏi bình thường; loại **tự tin lặp nguyên văn mọi kết quả** vì K8 chứng minh trích đúng vẫn có thể sai. |
| `goi_y_bai_tap` | **Tự làm, giới hạn theo trạng thái bài** | Nếu đưa, xác nhận hoặc phủ nhận đáp số Bài 3 đang mở, học viên có thể chép hoặc dò đáp án (K5, K6). Xóa gợi ý sau đó không thu hồi được thông tin đã đọc. | Bắt TA duyệt từng gợi ý khiến học viên hỏi sau 22:00 phải chờ đến ca 08:00, có thể mất thời gian làm bài trước hạn 13/11 23:59. Cho AI tự gửi **gợi ý phương pháp/bước đầu**, có §3.1–§3.2, nhưng chặn đáp số, đánh giá đúng/sai và lời giải hoàn chỉnh khi bài còn mở. Nếu chưa biết bài mở hay đã đóng, không gửi gợi ý về kết quả; hỏi lại hoặc chuyển TA. Bài 2 đã hết hạn và có đáp án công bố được giải thích đầy đủ (K10). | Loại **tự gửi mọi gợi ý** vì K6 cho thấy cả một chữ “đúng” cũng làm hỏng giới hạn; loại **TA duyệt mọi gợi ý** vì người học cần hỗ trợ ngoài giờ trực. |
| `chuyen_TA` | **Cần học viên duyệt** | Nếu gửi nhầm câu hỏi hoặc ngữ cảnh, học viên mất quyền kiểm soát nội dung chia sẻ; có thể rút yêu cầu nhưng TA có thể đã đọc. Nếu báo “đã chuyển” khi tool lỗi, học viên tưởng có người hỗ trợ và lỡ thời gian (K7). | Xem trước và xác nhận là một bước ngắn, ít tốn thời gian hơn hậu quả gửi nhầm. Học viên xem câu hỏi, phần ngữ cảnh và giờ trực 08:00–22:00 rồi bấm **Gửi TA**. Chỉ báo “Đã chuyển” sau khi tool thành công; lỗi thì giữ bản nháp để thử lại. Ngoài giờ trực, báo yêu cầu sẽ được xem từ ca tiếp theo, không hứa giờ trả lời. | Loại **tự gửi ngay** vì học viên chưa biết nội dung nào được chia sẻ; loại **cấm chuyển TA** vì K8 cần người có thẩm quyền kiểm tra tài liệu. |
| `dang_FAQ` | **Cần TA duyệt** | FAQ sai khiến nhiều học viên học sai cùng lúc; gỡ bài được nhưng không thu hồi được điều họ đã đọc, đặc biệt với câu sai ở §3.3 (K8). Câu hỏi nguyên văn còn có thể chứa thông tin riêng của học viên. | Chờ TA làm FAQ xuất hiện muộn, nhưng một FAQ chưa đăng không cản học viên nhận gợi ý riêng hay gửi câu hỏi cho TA. AI chỉ soạn bản nháp; TA xem câu hỏi đã ẩn danh, câu trả lời, mã mục và cảnh báo nguồn trước khi bấm đăng. Quá giờ trực thì giữ nháp, không đăng tự động. | Loại **AI tự đăng rồi cho gỡ** vì gỡ không đảo được việc cả lớp đã đọc; loại **cấm cả việc đăng FAQ** vì TA vẫn có thể kiểm chứng và phổ biến câu trả lời đúng. |

**Luật tách bước:** `chuyen_TA` gồm **soạn/xem trước** (chưa gửi, học viên sửa hoặc hủy được) và **gửi thật** (chỉ sau xác nhận). `dang_FAQ` gồm **soạn nháp** và **đăng** (chỉ TA xác nhận). Đây là tách bước của hai tool trong track, không giả định AI có thêm quyền tự sửa tài liệu hay tự đăng. Với `goi_y_bai_tap`, hệ thống lấy trạng thái bài từ Dữ liệu B trước khi cho gửi; trạng thái không rõ thì không đoán.

### 4.2. Tool khó xếp nhất: `goi_y_bai_tap`

Tool này có giá ở cả hai phía. **Cho tự làm không giới hạn** thì K6 có thể biến câu “đúng chưa?” thành một lần xác nhận đáp số; lời xin lỗi sau đó không cứu được. **Bắt TA duyệt mọi gợi ý** thì học viên hỏi tối muộn phải chờ hết giờ trực; ngay cả K10, bài đã có đáp án công bố, cũng bị chặn vô ích. **Cấm hẳn** thì sản phẩm không còn giúp học viên tự học từng bước.

**Quyết định:** cho tự gửi gợi ý bước đầu khi biết chắc bài đang mở; từ chối đưa hoặc kiểm đáp số; với bài đã đóng và có đáp án công bố thì được giải thích đầy đủ. Nếu hệ thống không chặn được nội dung có đáp số/nhận xét đúng sai, nó không gửi gợi ý đó và mời học viên hỏi TA. Cách chốt này giữ hỗ trợ tức thì mà chặn lỗi đắt nhất ở K6. Khi trình bày, nhóm cần nói rõ đây là lựa chọn thiết kế sau khi cân ba mức trên; chưa có ghi nhận lựa chọn độc lập ban đầu của từng thành viên.

### 4.3. Thử mức trên hai ca đắt nhất và một ca bình thường ở §2

| Kịch bản | AI làm gì; học viên thấy gì? | Cái sai ở §2 có bị chặn? | Còn việc tự làm khi lẽ ra phải hỏi? | Học viên bình thường có phải chờ vô ích? |
| --- | --- | --- | --- | --- |
| **K6 — xin xác nhận đáp số Bài 3 đang mở** | Đọc trạng thái “đang mở” từ Dữ liệu B; `tra_cuu_tai_lieu` lấy §3.1–§3.2; `goi_y_bai_tap` chỉ gửi cách tự kiểm từng bước như [S1]–[S3]. Muốn hỏi TA thì [S4] mở bản xem trước và chờ học viên xác nhận. | **Có**, nếu bộ chặn loại cả “đúng”, “sai”, đáp số và lời giải hoàn chỉnh. Chỉ xin lỗi sau khi gửi sai là không đủ. | **Không**: AI không tự xác nhận đáp số hoặc tự chuyển câu hỏi cho TA. Nếu không chắc trạng thái bài, phải dừng gợi ý về kết quả. | **Không**: gợi ý phương pháp đến ngay; chỉ bước gửi TA mới cần học viên duyệt. |
| **K8 — câu sai trong tài liệu §3.3** | `tra_cuu_tai_lieu` tìm đúng §3.3 nhưng giao diện [S5]–[S6] gắn “Cần xem lại”, đưa phản ví dụ phương sai 0,25 và độ lệch chuẩn 0,5. [S7] cho học viên duyệt bản báo TA; `dang_FAQ` chỉ là nháp chờ TA. | **Có đối với lỗi lặp lại câu sai như sự thật**: người học thấy rõ câu gốc đang bị nghi vấn, không có FAQ sai xuất hiện tự động. Chưa thể bảo đảm phát hiện mọi lỗi kiến thức khác. | **Không**: AI không tự sửa tài liệu chính thức, không tự báo TA và không tự đăng FAQ. | **Không**: học viên nhận ngay phần giải thích và cảnh báo; việc xác minh chính thức chờ TA. |
| **K10 — hỏi Bài 2 đã hết hạn và có đáp án công bố** | Kiểm tra Dữ liệu B: bài đã hết hạn 06/11, đáp án công bố 07/11. `tra_cuu_tai_lieu` lấy §3.1; `goi_y_bai_tap` giải thích phép tính và đáp án công bố là 6. | **Có**: tránh lỗi áp nhầm luật bài đang mở rồi từ chối một câu được phép giải thích. | **Không**: trạng thái bài và đáp án đều có trong trang khoá học; không cần hỏi TA để xác minh. | **Không**: học viên nhận lời giải thích ngay. |

### 4.4. Lời hứa với người dùng thay đổi

Đặt `goi_y_bai_tap` ở mức **tự làm có giới hạn** đổi lời hứa từ “AI sẽ kiểm tra hoặc giải hộ bài của bạn” thành: **“Bạn nhận được gợi ý bước đầu ngay cả ngoài giờ TA; với bài đang mở, trợ lý không đưa hay xác nhận đáp số. Khi tài liệu có dấu hiệu sai, trợ lý nêu rõ điểm nghi vấn và giúp bạn gửi cho TA sau khi bạn xác nhận.”** Prototype phải cho thấy đúng lời hứa này ở [S1]–[S7]: có gợi ý ngay, có nguồn và cảnh báo, có bản xem trước trước khi gửi TA, không có nút kiểm đáp số hay tự đăng FAQ.

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

