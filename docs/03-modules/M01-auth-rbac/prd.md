# MODULE M01: SECURITY, AUTHENTICATION & RBAC

## Feature: FR-05-1 - Đăng nhập hệ thống (User Login)

### 1. User Story
Với tư cách là Người dùng (Sinh viên/Nhân viên/Quản trị viên), tôi muốn đăng nhập vào hệ thống bằng thông tin xác thực nội bộ để có thể truy cập các tính năng được cấp quyền cho vai trò của mình.

### 2. Acceptance Criteria (AC)
**AC1: Validate Form Data**
* Given: Màn hình Login.
* When: User nhập data.
* Then: `username` không chứa khoảng trắng; `password` tối thiểu 8 ký tự. Disable nút Submit nếu form invalid.

**AC2: Kiểm tra First Login**
* Given: User submit form hợp lệ.
* When: Backend kiểm tra DB thấy `is_first_login == true`.
* Then: Không cấp Token. Trả về mã lỗi 403 (Force Password Change) và Redirect sang màn hình đổi mật khẩu.

**AC3: Cấp JWT Token**
* Given: User submit form hợp lệ.
* When: Backend kiểm tra DB thấy `is_first_login == false` và password match.
* Then: Sinh JWT Access Token (Expiration: 24h). Payload bắt buộc chứa `user_id`, `role`, `department_id`.

### 3. Technical Breakdown
**3.1. Database Schema (Bảng Users)**
* `id` (UUID, PK)
* `username` (VARCHAR 50, Unique, Index)
* `password_hash` (VARCHAR 255)
* `role` (ENUM: 'STUDENT', 'STAFF', 'MANAGER', 'ADMIN')
* `department_id` (UUID, FK -> Departments, Nullable for Student/Admin)
* `is_first_login` (BOOLEAN, Default: true)

**3.2. API Contract**
* **POST** `/api/v1/auth/login`
* **Request:** `{ "username": "...", "password": "..." }`
* **Response (200):** `{ "token": "jwt_string", "role": "STUDENT" }`
* **Response (403):** `{ "error": "Require password change", "require_action": "CHANGE_PASSWORD" }`

---

## Feature: FR-05-2 - Import tài khoản nội bộ (User Import)

### 1. User Story
As an Admin, I want to import users in bulk via a CSV file so that I do not have to create accounts manually.

### 2. Acceptance Criteria (AC)
**AC1: Validate File Upload**
* Given: Màn hình Admin Import.
* When: Upload file.
* Then: File bắt buộc định dạng `.csv`. Max size 5MB. Bắt buộc có các cột: `username`, `full_name`, `email`, `role`, `department_id`.

**AC2: Auto-generate Password & Flag**
* Given: File CSV hợp lệ.
* When: Backend xử lý import.
* Then: Mật khẩu mặc định sinh ra theo rule: `Student@ + username` hoặc `Staff@ + username`. Bắt buộc set `is_first_login = true`.

### 3. Technical Breakdown
**3.1. API Contract**
* **POST** `/api/v1/admin/users/import` (Multipart/form-data)
* **Request:** `file` (.csv)
* **Response (200):** `{ "success_count": 100, "error_count": 2, "errors": [{ "row": 5, "message": "Duplicate username" }] }`
