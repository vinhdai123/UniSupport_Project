# MODULE M02: STAFF DESK (KHÔNG GIAN CÁN BỘ)

## Feature: FR-02-1 - Hàng đợi xử lý Ticket (Staff Queue)

### 1. User Story
Với tư cách là nhân viên, tôi muốn xem danh sách các yêu cầu (ticket) đã được phân công cho bộ phận của mình theo thứ tự ưu tiên, để có thể xử lý các yêu cầu khẩn cấp trước khi đến hạn SLA.

### 2. Acceptance Criteria (AC)
**AC1: Data Isolation (Phân quyền dữ liệu)**
* Given: API Get Tickets của Staff.
* When: Staff request danh sách.
* Then: Backend bắt buộc append điều kiện `WHERE department_id = [Staff.department_id]` (lấy từ JWT). Không trả về dữ liệu của phòng ban khác. Filter loại bỏ các ticket có status `CLOSED`.

**AC2: SLA Warning (Cảnh báo UI)**
* Given: Bảng danh sách Ticket trên Frontend.
* When: `sla_deadline` - `current_time` <= 25% tổng thời lượng SLA.
* Then: Tô màu field SLA thành Vàng (Warning).
* When: `current_time` > `sla_deadline`.
* Then: Tô màu field SLA thành Đỏ (Overdue).

**AC3: Default Sorting**
* Given: Render bảng danh sách.
* When: Request lần đầu (không có custom sort).
* Then: Backend trả data order theo: `sla_deadline` ASC, sau đó đến `priority` DESC.

### 3. Technical Breakdown
**3.1. API Contract**
* **GET** `/api/v1/staff/tickets?page=1&limit=20&status=NEW,IN_PROGRESS&search=AU-2026`
* **Response (200):** `{ "data": [ { "ticket_code": "...", "priority": "HIGH", "status": "NEW", "created_at": "...", "sla_deadline": "..." } ], "meta": { "total": 150 } }`

---

## Feature: FR-02-2 - Thao tác xử lý Ticket (Ticket Actions)

### 1. User Story
As a Staff member, I want to update ticket status, reassign tickets, and reply to students so that issues can be resolved.

### 2. Acceptance Criteria (AC)
**AC1: Reassign (Chuyển phòng ban)**
* Given: Ticket detail view.
* When: Staff chọn "Chuyển tiếp" và chọn Department mới.
* Then: Bắt buộc nhập `Internal Note` (Lý do chuyển). Nếu bỏ trống, chặn call API.

**AC2: Change Status to Resolved**
* Given: Dropdown thay đổi trạng thái.
* When: Chọn status `RESOLVED`.
* Then: Bắt buộc gọi API thêm một Comment phản hồi cho Student. Đánh dấu `resolved_at` timestamp trên DB.

### 3. Technical Breakdown
**3.1. Database Schema (Bảng Ticket_Histories)**
* `id` (UUID, PK)
* `ticket_id` (UUID, FK -> Tickets)
* `action_by` (UUID, FK -> Users)
* `action_type` (ENUM: 'STATUS_CHANGE', 'REASSIGN', 'INTERNAL_NOTE')
* `old_value` (VARCHAR)
* `new_value` (VARCHAR)
* `note` (TEXT)
* `created_at` (TIMESTAMP)

**3.2. API Contract**
* **PATCH** `/api/v1/staff/tickets/:id/reassign`
* **Request:** `{ "new_department_id": "...", "note": "Chuyển nhầm phòng" }`
