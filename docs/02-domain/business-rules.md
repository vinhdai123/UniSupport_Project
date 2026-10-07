# QUY TẮC NGHIỆP VỤ (BUSINESS RULES)

Các quy tắc logic nền tảng áp dụng cho toàn bộ hoạt động của hệ thống UniSupport.

## BR-01: Định danh Ticket (Ticket ID)
* Mỗi Ticket khi tạo thành công sẽ được cấp một mã định danh duy nhất không trùng lặp.
* **Định dạng:** `AU-YYYY-XXXX` (Trong đó: `AU` là mã trường Aurora, `YYYY` là năm hiện tại, `XXXX` là số tự tăng bắt đầu từ 0001).
* *Ví dụ:* `AU-2026-0001`.

## BR-02: Quy định về Tệp đính kèm (Attachment Rules)
* **Số lượng:** Tối đa 03 tệp trên mỗi lần gửi/bổ sung.
* **Dung lượng:** Tối đa 5MB / 1 tệp.
* **Định dạng cho phép:** `.pdf`, `.jpg`, `.jpeg`, `.png`. Hệ thống phải chặn toàn bộ các định dạng thực thi mã độc.

## BR-03: Ma trận Thời hạn xử lý (SLA Matrix)
Thời hạn cam kết xử lý tiêu chuẩn được tính tự động dựa trên mức độ ưu tiên (Priority) của Ticket:
* **Khẩn cấp (Urgent):** 04 giờ làm việc.
* **Cao (High):** 12 giờ làm việc.
* **Trung bình (Medium - Mặc định):** 24 giờ làm việc.
* **Thấp (Low):** 48 giờ làm việc.

## BR-04: Cảnh báo quá hạn (SLA Alerts)
* **Cảnh báo Vàng:** Kích hoạt khi thời gian SLA còn lại $\le 25\%$ (Ticket sắp quá hạn).
* **Cảnh báo Đỏ:** Kích hoạt khi thời gian hiện tại vượt qua hạn chót xử lý (Ticket đã quá hạn / Overdue).

## BR-05: Quy tắc Mở lại Ticket (Reopen Window)
* Sinh viên chỉ được phép nhấn nút "Mở lại Ticket" trong vòng **72 giờ (03 ngày)** kể từ thời điểm Cán bộ đổi trạng thái sang `Hoàn thành`.
* Hết 72 giờ, Ticket tự động khóa vĩnh viễn (`Closed`) và không thể tác động thêm.
