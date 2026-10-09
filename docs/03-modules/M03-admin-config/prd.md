# MODULE M03: ADMIN CONFIG (QUẢN TRỊ & CẤU HÌNH)

## Feature: FR-03-1 - Quản lý Category & Routing

### 1. User Story
Với tư cách là Quản trị viên, tôi muốn cấu hình các danh mục hỗ trợ và liên kết chúng với các phòng ban cụ thể để hệ thống tự động chuyển ticket đến đúng phòng ban phụ trách.

### 2. Acceptance Criteria (AC)
**AC1: Mapping Category to Department**
* Given: Màn hình tạo mới/edit Category.
* When: Admin điền form.
* Then: Bắt buộc phải chọn 1 `department_id` để map với Category đó.

### 3. Technical Breakdown
**3.1. Database Schema (Bảng Categories)**
* `id` (UUID, PK)
* `name` (VARCHAR 100, Unique)
* `department_id` (UUID, FK -> Departments) (Core logic for Auto-routing)
* `is_active` (BOOLEAN)
