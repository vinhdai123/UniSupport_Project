# MODULE M05: DASHBOARD & REPORT

## Feature: FR-04-1 - Metric & Báo cáo hiệu suất

### 1. User Story
Với tư cách là Quản lý, tôi muốn xem các chỉ số về hiệu suất SLA và trạng thái các ticket thuộc phòng ban của mình để có thể giám sát khối lượng công việc và hiệu quả xử lý.

### 2. Acceptance Criteria (AC)
**AC1: SLA Performance Calculation**
* Given: Manager Dashboard.
* When: Load chỉ số "Tỷ lệ xử lý đúng hạn".
* Then: Backend tính toán dựa trên công thức: `(Số ticket RESOLVED có resolved_at <= sla_deadline) / (Tổng số ticket RESOLVED) * 100`. Chỉ tính các ticket thuộc department của Manager.

**AC2: Backlog Query**
* Given: Manager Dashboard.
* When: Load chỉ số "Ticket tồn đọng (Backlog)".
* Then: Backend query count tất cả tickets có status = `NEW`, `IN_PROGRESS`, `PENDING` và `sla_deadline` < `current_time`.

### 3. Technical Breakdown
**3.1. API Contract**
* **GET** `/api/v1/reports/metrics` (Auth header xác định Manager & Department)
* **Response (200):** `{ "total_tickets": 500, "resolved_tickets": 400, "sla_compliance_rate": 85.5, "backlog_overdue": 12 }`
