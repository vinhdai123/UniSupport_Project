# PRODUCT OVERVIEW – UNISUPPORT

## 1. Thông tin sản phẩm

| Thông tin | Mô tả |
|---|---|
| Tên sản phẩm | UniSupport – Student Support Management System |
| Khách hàng | Aurora University |
| Quy mô phục vụ | Khoảng 3.000 sinh viên |
| Loại sản phẩm | Web-based Student Support Management System |
| Người dùng chính | Student, Staff, Manager, Administrator |
| Thời gian triển khai | 23 tuần |
| Go-live Target | Tuần 23 |

> Project Sponsor: **TBD / Reference Client Brief** nếu chưa được xác nhận trong Proposal.

---

## 2. Tổng quan sản phẩm

UniSupport là hệ thống quản lý yêu cầu hỗ trợ sinh viên tập trung,
được xây dựng cho Aurora University nhằm tiếp nhận, phân loại,
phân luồng, xử lý và theo dõi các yêu cầu hỗ trợ trên một nền tảng thống nhất.

Hệ thống hướng đến:

- Quản lý tập trung yêu cầu hỗ trợ.
- Cho phép Sinh viên theo dõi quá trình xử lý và tra cứu FAQ.
- Hỗ trợ Cán bộ tiếp nhận và xử lý Ticket.
- Hỗ trợ Quản lý theo dõi workload, thời hạn và hiệu suất xử lý.
- Hỗ trợ Quản trị viên quản lý các cấu hình và dữ liệu nền.
- Cung cấp Dashboard và báo cáo phục vụ công tác quản lý.

Chi tiết mục tiêu dự án được mô tả tại:

`goals-and-non-goals.md`

---

## 3. Đối tượng sử dụng

UniSupport hỗ trợ 04 Role:

| Role | Mục đích chính |
|---|---|
| Student | Gửi, theo dõi và trao đổi về yêu cầu hỗ trợ |
| Staff | Tiếp nhận và xử lý Ticket |
| Manager | Giám sát và điều phối hoạt động xử lý |
| Administrator | Quản lý cấu hình và tài khoản hệ thống |

Chi tiết trách nhiệm và phạm vi của từng Role được mô tả tại:

`actors-and-roles.md`

---

## 4. Giá trị sản phẩm

### 4.1. Đối với Sinh viên

- Có một kênh hỗ trợ trực tuyến tập trung.
- Chủ động theo dõi quá trình xử lý yêu cầu.
- Có thể tự tra cứu FAQ và hướng dẫn hỗ trợ.

### 4.2. Đối với Cán bộ

- Quản lý Ticket trong một không gian làm việc tập trung.
- Hỗ trợ theo dõi và phối hợp quá trình xử lý.
- Có lịch sử xử lý để phục vụ theo dõi công việc.

### 4.3. Đối với Quản lý và Nhà trường

- Theo dõi Ticket tồn đọng và thời hạn xử lý.
- Theo dõi workload và hiệu suất xử lý.
- Có Dashboard và báo cáo phục vụ công tác quản lý.

---

## 5. Core Capabilities

### 5.1. Ticket Management

Tiếp nhận, phân loại, phân luồng, phân công, theo dõi và xử lý Ticket.

### 5.2. Communication & Notification

Hỗ trợ trao đổi trên Ticket và thông báo cho Sinh viên khi có cập nhật quan trọng.

### 5.3. Processing Deadline Management

Thiết lập và theo dõi thời hạn xử lý, đồng thời cảnh báo Ticket
sắp đến hạn hoặc quá hạn.

### 5.4. System Administration

Quản lý:

- User & Role.
- Category.
- Department.
- Priority.
- Routing Rule.
- FAQ / Knowledge Base.
- Response Template.

### 5.5. Dashboard & Reporting

Cung cấp:

- Ticket statistics.
- Completion Rate.
- Backlog.
- Average Processing Time.
- Performance by Department / Staff.
- Common Issues.
- Ticket Trends.
- Student Satisfaction.
- CSV Export.

### 5.6. Authentication & Authorization

- Đăng nhập bằng tài khoản UniSupport.
- Reset Password.
- Role-based Functional Access.
- Data Access Control.
- Attachment Access Control.
- Audit các thao tác quan trọng.

> Chi tiết từng capability được đặc tả trong các PRD Module M01–M05.

---

## 6. Success Metrics

Các chỉ số dưới đây được sử dụng để theo dõi hiệu quả vận hành
sau khi hệ thống được đưa vào sử dụng.

| Mã | Metric | Ý nghĩa |
|---|---|---|
| SM-01 | Ticket Completion Rate | Tỷ lệ Ticket hoàn thành |
| SM-02 | Overdue Ticket Rate | Tỷ lệ Ticket quá thời hạn xử lý |
| SM-03 | Average Processing Time | Thời gian xử lý Ticket trung bình |
| SM-04 | Ticket Backlog | Số lượng Ticket tồn đọng |
| SM-05 | Student Satisfaction | Mức độ hài lòng của Sinh viên |

> Target value, công thức tính và kỳ đánh giá:
> **TBD – Pending Confirmation**.

Các metric trên không tự tạo thêm phạm vi chức năng.
Chúng sử dụng dữ liệu từ Dashboard & Reporting đã nằm trong In-Scope.

---

## 7. Product Boundaries

UniSupport được triển khai dưới dạng **Web Application**.

Hệ thống:

- Hỗ trợ Desktop và Mobile thông qua Responsive Web Design.
- Hỗ trợ Tiếng Việt và Tiếng Anh.
- Sử dụng tài khoản nội bộ UniSupport.
- Áp dụng Role-Based Access Control.

Các giới hạn và nội dung ngoài phạm vi được quản lý tại:

`goals-and-non-goals.md`

và:

`product-scope.md`

Không lặp lại toàn bộ Out-of-Scope tại tài liệu này để tránh
duy trì cùng một requirement ở nhiều nơi.

---

## 8. Release Target

Tổng thời gian triển khai dự kiến: **23 tuần**.

### Tuần 1–5

- Khởi động dự án.
- Xác nhận yêu cầu.
- Phân tích và thiết kế.
- Hoàn thiện UI/UX Prototype.

### Tuần 6–18

- Phát triển nền tảng và Authentication.
- Phát triển Ticket Flow.
- Phát triển Management & Administration.
- Phát triển Dashboard & Reporting.
- Hoàn thiện Responsive và đa ngôn ngữ.

### Tuần 19–20

- Tích hợp toàn hệ thống.
- System Testing.
- Security Review.
- Fix lỗi.

### Tuần 21–22

- User Acceptance Testing.
- Hoàn thiện phiên bản nghiệm thu.

### Tuần 23

- Go-live.
- Hướng dẫn sử dụng.
- Bàn giao hệ thống, mã nguồn và tài liệu.

