# LAB5 · T2 Giáo dục — Trợ lý học bài tối muộn

Bài nộp LAB5 (AI20K K5, ngày 5), lớp L3A, track **T2 Giáo dục**: thiết kế trợ lý học bài kiểu Study mode tích hợp vào trang khoá học, tập trung vào lúc AI không chắc hoặc sai, và việc nào AI được tự làm.

## Trong repo có gì

| Đường dẫn | Nội dung |
|---|---|
| [`spec.md`](spec.md) | Bài nộp: lát cắt, 12 kịch bản rủi ro, thiết kế khi AI sai, mức tự chủ, prototype, tiêu chí đạt, demo |
| [`prototype/index.html`](prototype/index.html) | Prototype bấm được, hai màn hình: chat của học viên và hàng chờ của TA |
| [`prototype/man-hinh-hoc-vien.png`](prototype/man-hinh-hoc-vien.png) | Ảnh màn hình học viên, có số chú thích |
| [`prototype/man-hinh-TA.png`](prototype/man-hinh-TA.png) | Ảnh màn hình TA, có số chú thích |

## Xem prototype

Tải repo về và mở `prototype/index.html` bằng trình duyệt. Không cần cài đặt, không cần mạng, không có API key.

Đường bấm ca khó:

1. Bấm tin mồi "Độ lệch chuẩn với phương sai cái nào lớn hơn ạ?" (tài liệu sai ở §3.3).
2. Bấm "Thử phản ví dụ", rồi "Rút câu hỏi" và "Gửi lại".
3. Bấm tin mồi "Em tính bài 3 ra trung vị 11,5…" (xin xác nhận đáp số bài đang mở).
4. Sang tab "TA · hàng chờ": xử lý cờ §3.3 thì nút "Đăng cho cả lớp" mới mở.

Bật ô "Hiện số chú thích" để thấy các số 1–8 khớp với bảng ở `spec.md` §5.

## Ghi chú

- Câu trả lời của AI trong prototype là dựng sẵn, chọn theo từ khoá; không có lời gọi AI thật.
- Toàn bộ dữ liệu là dữ liệu dựng của track T2, không có dữ liệu của người thật.
