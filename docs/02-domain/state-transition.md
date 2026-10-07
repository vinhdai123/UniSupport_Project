# VÒNG ĐỜI TRẠNG THÁI TICKET (TICKET STATE TRANSITION)

Sơ đồ và các quy tắc chuyển đổi trạng thái của một Ticket trong hệ thống UniSupport.

## 1. Danh sách Trạng thái (Ticket States)
1. **Mới tạo (New):** Màu Xanh dương. Ticket vừa được sinh viên tạo, đang nằm trong hàng đợi hoặc chưa có người thụ lý.
2. **Đang xử lý (In Progress):** Màu Cam. Cán bộ đã tiếp nhận và đang tiến hành kiểm tra, giải quyết.
3. **Cần bổ sung (Pending):** Màu Vàng. Cán bộ yêu cầu sinh viên cung cấp thêm thông tin hoặc giấy tờ. Ticket tạm dừng tính SLA.
4. **Hoàn thành (Resolved):** Màu Xanh lá. Cán bộ đã giải quyết xong và gửi kết quả cho sinh viên. 
5. **Đóng (Closed):** Màu Xám. Trạng thái ẩn (hệ thống tự động đóng vĩnh viễn sau khi Hoàn thành được 72 giờ).

## 2. Các luồng chuyển đổi hợp lệ (Valid Transitions)
* `[Mới tạo]` $\rightarrow$ Cán bộ nhấn Nhận xử lý $\rightarrow$ `[Đang xử lý]`
* `[Đang xử lý]` $\rightarrow$ Cán bộ gửi yêu cầu bổ sung $\rightarrow$ `[Cần bổ sung]`
* `[Cần bổ sung]` $\rightarrow$ Sinh viên gửi thêm tài liệu $\rightarrow$ `[Đang xử lý]`
* `[Đang xử lý]` $\rightarrow$ Cán bộ gửi kết quả cuối cùng $\rightarrow$ `[Hoàn thành]`
* `[Hoàn thành]` $\rightarrow$ Sinh viên bấm Mở lại (trong 72h) $\rightarrow$ `[Đang xử lý]`
* `[Hoàn thành]` $\rightarrow$ Trôi qua 72h $\rightarrow$ `[Đóng]`

## 3. Ràng buộc cập nhật (State Constraints)
* Chỉ có **Cán bộ** và **Hệ thống** mới có quyền chuyển Ticket sang `Hoàn thành`.
* Khi chuyển sang `Hoàn thành`, cán bộ bắt buộc phải nhập nội dung giải quyết.
* Khi Ticket ở trạng thái `Cần bổ sung` hoặc `Đóng`, tính năng Chat trực tiếp sẽ bị tạm khóa.
