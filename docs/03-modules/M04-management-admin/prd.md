# MODULE M04: ADMIN CONFIG (QUẢN TRỊ & CẤU HÌNH)

## FR-ADM-01 – Quản lý danh mục yêu cầu

### 1. User Story

Là **Quản trị viên**, tôi muốn quản lý các danh mục yêu cầu để hệ thống có thể phân loại Ticket theo từng nhóm nghiệp vụ và sử dụng các danh mục này trong quá trình tạo Ticket và phân luồng Ticket.

### 2. Input

- Tên danh mục.
- Mô tả danh mục.
- Trạng thái sử dụng của danh mục (nếu áp dụng).

> Các trường dữ liệu cụ thể của Category, quy tắc đặt tên và trạng thái sử dụng: **TBD – Pending Confirmation**.

### 3. Processing

#### 3.1. Xem danh sách Category

1. Administrator truy cập chức năng quản lý danh mục.
2. Hệ thống kiểm tra quyền quản trị.
3. Hệ thống lấy danh sách Category hiện có.
4. Hệ thống hiển thị thông tin của các Category để Administrator theo dõi và quản lý.

#### 3.2. Tạo Category

1. Administrator chọn chức năng tạo Category mới.
2. Hệ thống hiển thị form nhập thông tin Category.
3. Administrator nhập các thông tin cần thiết.
4. Administrator xác nhận tạo Category.
5. Hệ thống kiểm tra các trường bắt buộc.
6. Nếu dữ liệu không hợp lệ:
   - Không tạo Category.
   - Hiển thị thông tin cần bổ sung hoặc chỉnh sửa.
7. Nếu dữ liệu hợp lệ:
   - Hệ thống tạo Category mới.
   - Lưu Category vào hệ thống.
8. Category sau khi được tạo có thể được sử dụng trong các chức năng liên quan.

#### 3.3. Cập nhật Category

1. Administrator chọn một Category đã tồn tại.
2. Hệ thống hiển thị thông tin hiện tại của Category.
3. Administrator chỉnh sửa thông tin.
4. Administrator xác nhận lưu thay đổi.
5. Hệ thống kiểm tra dữ liệu.
6. Nếu hợp lệ:
   - Cập nhật thông tin Category.
7. Các chức năng sử dụng Category nhận thông tin mới theo cấu hình hiện tại.

### 4. Output

Sau khi xử lý thành công, hệ thống cung cấp:

- Danh sách Category hiện có.
- Thông tin Category đã được tạo hoặc cập nhật.
- Category khả dụng cho:
  - Sinh viên lựa chọn khi tạo Ticket.
  - Hệ thống phân loại Ticket.
  - Cấu hình Routing Rule.

Nếu thao tác không thành công:

- Dữ liệu Category không bị cập nhật không hợp lệ.
- Hệ thống hiển thị thông báo lỗi hoặc thông tin cần chỉnh sửa.

### 5. Acceptance Criteria

**AC1 – Xem danh sách Category**

- Given: Administrator đã đăng nhập và có quyền quản trị Category.
- When: Administrator truy cập màn hình quản lý danh mục.
- Then: Hệ thống hiển thị danh sách Category hiện có.

**AC2 – Tạo Category thành công**

- Given: Administrator đang ở chức năng tạo Category.
- When: Administrator nhập đầy đủ thông tin bắt buộc và xác nhận tạo.
- Then: Hệ thống tạo Category mới và lưu Category vào hệ thống.

**AC3 – Thiếu thông tin bắt buộc**

- Given: Administrator đang tạo Category.
- When: Administrator gửi form nhưng thiếu thông tin bắt buộc.
- Then: Hệ thống không tạo Category và thông báo thông tin cần bổ sung.

**AC4 – Cập nhật Category**

- Given: Category đã tồn tại.
- When: Administrator chỉnh sửa thông tin hợp lệ và lưu.
- Then: Hệ thống cập nhật thông tin Category.

**AC5 – Sử dụng Category khi tạo Ticket**

- Given: Category đã được cấu hình và đang khả dụng.
- When: Sinh viên truy cập chức năng tạo Ticket.
- Then: Category có thể được sử dụng để phân loại yêu cầu.

**AC6 – Sử dụng Category trong Routing Rule**

- Given: Category tồn tại trong hệ thống.
- When: Administrator cấu hình Routing Rule.
- Then: Category có thể được sử dụng làm thông tin phục vụ cấu hình phân luồng Ticket.

**AC7 – Kiểm soát quyền**

- Given: Người dùng không có quyền quản trị Category.
- When: Người dùng yêu cầu tạo hoặc cập nhật Category.
- Then: Hệ thống không cho phép thực hiện thao tác.


