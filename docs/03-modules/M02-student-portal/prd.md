## Feature: FR-STU-01 – Tạo yêu cầu hỗ trợ (Submit Ticket)

### 1. User Story

Là **Sinh viên**, tôi muốn gửi yêu cầu hỗ trợ trực tuyến theo danh mục để yêu cầu của tôi được hệ thống ghi nhận và chuyển vào quy trình xử lý phù hợp.

### 2. Input

- Danh mục yêu cầu.
- Tiêu đề yêu cầu.
- Nội dung yêu cầu.
- Tài liệu/hình ảnh đính kèm (nếu có).

> Danh sách Category, các trường thông tin cụ thể và quy tắc Validation chi tiết: **TBD – Pending Confirmation**.

### 3. Processing

1. Sinh viên truy cập chức năng **Tạo Ticket**.
2. Hệ thống hiển thị các danh mục yêu cầu hiện có.
3. Sinh viên chọn danh mục phù hợp.
4. Sinh viên nhập tiêu đề và nội dung yêu cầu.
5. Sinh viên có thể đính kèm tài liệu/hình ảnh nếu cần.
6. Sinh viên thực hiện gửi yêu cầu.
7. Hệ thống kiểm tra các trường thông tin bắt buộc.
8. Nếu dữ liệu không hợp lệ:
   - Hệ thống không tạo Ticket.
   - Hiển thị thông báo để Sinh viên biết thông tin cần bổ sung hoặc chỉnh sửa.
9. Nếu dữ liệu hợp lệ:
   - Hệ thống tạo Ticket mới.
   - Liên kết Ticket với tài khoản Sinh viên đang đăng nhập.
   - Ghi nhận danh mục và nội dung yêu cầu.
   - Ghi nhận tài liệu/hình ảnh đính kèm nếu có.
10. Hệ thống tự động tạo một Ticket ID cho Ticket.
11. Hệ thống thiết lập trạng thái ban đầu của Ticket là `Mới tạo`.
12. Hệ thống ghi nhận thời điểm tạo Ticket.
13. Ticket được chuyển sang quy trình **Routing** để xác định phòng ban xử lý dựa trên danh mục và Routing Rule đã được cấu hình.
14. Hệ thống thông báo cho Sinh viên rằng Ticket đã được tạo thành công.

### 4. Output

Sau khi tạo Ticket thành công, hệ thống cung cấp tối thiểu:

- Ticket ID.
- Tiêu đề Ticket.
- Danh mục yêu cầu.
- Trạng thái hiện tại: `Mới tạo`.
- Thời điểm tạo Ticket.

Nếu tạo Ticket không thành công:

- Ticket không được ghi nhận.
- Hệ thống hiển thị thông báo lỗi hoặc thông tin cần bổ sung.

### 5. Acceptance Criteria

**AC1 – Hiển thị chức năng tạo Ticket**

- **Given:** Sinh viên đã đăng nhập và có quyền sử dụng Student Portal.
- **When:** Sinh viên truy cập chức năng tạo Ticket.
- **Then:** Hệ thống hiển thị form tạo yêu cầu và các danh mục có thể lựa chọn.

**AC2 – Tạo Ticket thành công**

- **Given:** Sinh viên đã nhập đầy đủ các thông tin bắt buộc.
- **When:** Sinh viên gửi yêu cầu.
- **Then:** Hệ thống tạo một Ticket mới và liên kết Ticket với đúng tài khoản Sinh viên.

**AC3 – Tự động tạo Ticket ID**

- **Given:** Ticket được tạo thành công.
- **When:** Hệ thống hoàn tất việc ghi nhận Ticket.
- **Then:** Hệ thống tự động cấp một Ticket ID để nhận diện Ticket.

> Định dạng Ticket ID: **TBD – Pending Confirmation**.

**AC4 – Trạng thái ban đầu**

- **Given:** Ticket vừa được tạo thành công.
- **When:** Hệ thống ghi nhận Ticket.
- **Then:** Trạng thái ban đầu của Ticket phải là `Mới tạo`.

**AC5 – Ghi nhận thời điểm tạo**

- **Given:** Ticket được tạo thành công.
- **When:** Hệ thống lưu Ticket.
- **Then:** Hệ thống phải ghi nhận thời điểm Ticket được tạo.

**AC6 – Thiếu thông tin bắt buộc**

- **Given:** Sinh viên đang ở form tạo Ticket.
- **When:** Sinh viên gửi yêu cầu nhưng thiếu một hoặc nhiều thông tin bắt buộc.
- **Then:** Hệ thống không tạo Ticket và thông báo các thông tin cần bổ sung.

**AC7 – Đính kèm tài liệu/hình ảnh**

- **Given:** Sinh viên có tài liệu hoặc hình ảnh cần cung cấp.
- **When:** Sinh viên thêm Attachment vào yêu cầu.
- **Then:** Attachment hợp lệ được ghi nhận và liên kết với Ticket.

> Quy định File Type, File Size và số lượng Attachment được đặc tả tại FR riêng về Attachment và hiện ở trạng thái **TBD – Pending Confirmation** nếu chưa được Aurora University xác nhận.

**AC8 – Chuyển sang quy trình phân luồng**

- **Given:** Ticket được tạo thành công.
- **When:** Hệ thống hoàn tất việc ghi nhận Ticket.
- **Then:** Ticket được chuyển sang quy trình Routing để xác định phòng ban xử lý theo Category và Routing Rule đã được cấu hình.

**AC9 – Không để Sinh viên tự chọn phòng ban xử lý**

- **Given:** Sinh viên đang tạo Ticket.
- **When:** Sinh viên chọn Category và gửi yêu cầu.
- **Then:** Việc xác định phòng ban xử lý được thực hiện bởi Routing Process của hệ thống, không phải do Sinh viên tự quyết định.

**AC10 – Thông báo kết quả tạo Ticket**

- **Given:** Sinh viên gửi yêu cầu.
- **When:** Ticket được tạo thành công.
- **Then:** Hệ thống thông báo tạo Ticket thành công và cung cấp Ticket ID cho Sinh viên.