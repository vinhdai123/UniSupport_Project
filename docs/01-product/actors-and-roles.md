# CHÂN DUNG NGƯỜI DÙNG (ACTORS & ROLES)

Hệ thống UniSupport được thiết kế phân quyền (RBAC) xoay quanh 04 nhóm người dùng chính:

## 1. Persona 1: Sinh viên (Student)
* **Vai trò:** Người dùng cuối gửi yêu cầu hỗ trợ.
* **Khó khăn hiện tại:** Không biết yêu cầu đang được xử lý ở đâu, bởi ai.
* **Mục tiêu hệ thống:** Tạo Ticket, theo dõi tiến độ, trao đổi bổ sung thông tin và nhận thông báo kết quả.
* **Bối cảnh sử dụng:** Trình duyệt trên Desktop hoặc thiết bị Mobile.

## 2. Persona 2: Cán bộ xử lý (Staff)
* **Vai trò:** Nhân viên các phòng ban chịu trách nhiệm tiếp nhận và xử lý Ticket.
* **Khó khăn hiện tại:** Yêu cầu phân tán qua nhiều email, dễ bỏ sót deadline.
* **Mục tiêu hệ thống:** Quản lý hàng đợi Ticket được phân công, phản hồi sinh viên và luân chuyển Ticket đúng chuyên môn.

## 3. Persona 3: Quản lý phòng ban (Manager)
* **Vai trò:** Trưởng/Phó phòng ban chuyên môn.
* **Mục tiêu hệ thống:** Theo dõi workload của phòng, giám sát các Ticket sắp quá hạn, điều chuyển công việc giữa các cán bộ và theo dõi hiệu suất (SLA).

## 4. Persona 4: Quản trị viên (Administrator)
* **Vai trò:** Cán bộ IT hoặc Ban điều hành hệ thống.
* **Mục tiêu hệ thống:** Quản lý danh mục hỗ trợ, cơ cấu phòng ban, quy tắc định tuyến tự động (Routing Rules), quản trị kho FAQ và tài khoản người dùng.
