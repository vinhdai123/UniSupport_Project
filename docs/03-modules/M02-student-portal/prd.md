# MODULE M02: STUDENT PORTAL (CỔNG SINH VIÊN)

## Feature: FR-01-1 - Tạo yêu cầu hỗ trợ (Submit Ticket)

### 1. User Story
Là sinh viên, tôi muốn gửi yêu cầu hỗ trợ với các trường thông tin linh hoạt tùy theo danh mục, để yêu cầu của tôi được chuyển đến đúng bộ phận xử lý.

### 2. Acceptance Criteria (AC)
**AC1: Data Binding (Read-only)**
* Given: Màn hình Create Ticket.
* When: Render component.
* Then: Tự động trích xuất `student_id`, `full_name`, `email` từ JWT Token. Hiển thị dạng Read-only (Disable input).

**AC2: Dynamic Extra Field (Logic động)**
* Given: Khối Category.
* When: User chọn Category = `Course_Registration` hoặc `Examination`.
* Then: Bắt buộc render Input `Mã môn học` (Required).
* When: User chọn Category = `Tuition_Payment`.
* Then: Bắt buộc render Input `Mã giao dịch` (Required).

**AC3: Priority Reason Rules**
* Given: Khối Priority (Mặc định: Medium).
* When: User đổi sang `High`.
* Then: Bắt buộc render Textarea `Lý do khẩn cấp` (Min: 20 ký tự). Nếu rỗng, chặn submit. Mức `Urgent` không được phép xuất hiện ở UI này.

**AC4: Create Ticket Processing**
* Given: Form data hợp lệ.
* When: Call API Submit.
* Then: Backend tạo record. Auto-generate `ticket_code` (Prefix: AU-YYYY-). Auto-set `status` = 'NEW'. Auto-calculate `sla_deadline` dựa trên logic: `created_at` + hours tương ứng với priority.

### 3. Technical Breakdown
**3.1. Database Schema (Bảng Tickets)**
* `id` (UUID, PK)
* `ticket_code` (VARCHAR, Unique, Format: AU-2026-XXXX)
* `student_id` (UUID, FK -> Users, Index)
* `category_id` (UUID, FK -> Categories)
* `department_id` (UUID, FK -> Departments, Auto-assigned by Category)
* `subject` (VARCHAR 150)
* `description` (TEXT)
* `extra_code` (VARCHAR 50, Nullable)
* `priority` (ENUM: 'LOW', 'MEDIUM', 'HIGH', 'URGENT')
* `priority_reason` (TEXT, Nullable)
* `status` (ENUM: 'NEW', 'IN_PROGRESS', 'PENDING', 'RESOLVED', 'CLOSED')
* `created_at` (TIMESTAMP)
* `sla_deadline` (TIMESTAMP)

**3.2. API Contract**
* **POST** `/api/v1/tickets`
* **Request:** `{ "category_id": "...", "subject": "...", "description": "...", "extra_code": "CS101", "priority": "HIGH", "priority_reason": "...", "attachments": ["url1", "url2"] }`
* **Response (201):** `{ "ticket_code": "AU-2026-0001", "sla_deadline": "2026-10-10T12:00:00Z", "status": "NEW" }`
