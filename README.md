# UNISUPPORT PROJECT
## Student Support Management System – Aurora University

Kho lưu trữ tài liệu phân tích, đặc tả yêu cầu và kế hoạch triển khai
của dự án **UniSupport – Student Support Management System**.

UniSupport là hệ thống Web hỗ trợ Aurora University quản lý tập trung
các yêu cầu hỗ trợ sinh viên, bao gồm quá trình tiếp nhận, phân loại,
phân luồng, xử lý, theo dõi, quản lý thời hạn và báo cáo.

---

# 1. Project Planning & Schedule

Kế hoạch triển khai tổng thể của UniSupport được quản lý trên
**GitHub Projects**.

Theo Proposal, tổng thời gian triển khai dự kiến là **23 tuần**
với các Phase từ `P1` đến `P9`.

| View | Mục đích | Link |
|---|---|---|
| **Monthly Roadmap** | Theo dõi tiến độ công việc theo thời gian chi tiết | [Xem Monthly Roadmap](https://github.com/users/Huybao312/projects/2/views/1) |
| **Quarterly Roadmap** | Theo dõi các Phase chính của dự án | [Xem Quarterly Roadmap](https://github.com/users/Huybao312/projects/2/views/2) |
| **Master Plan Table** | Theo dõi công việc, thời lượng, Sprint, dependency và tiến độ | [Xem Master Plan](https://github.com/users/Huybao312/projects/2/views/4) |

> GitHub Projects là nơi theo dõi tiến độ thực thi.
>
> Proposal là nguồn chuẩn cho Timeline, Milestone và phạm vi cam kết với khách hàng.

---

# 2. Product Documentation

Thư mục `docs/01-product/` chứa các tài liệu mô tả sản phẩm
ở mức tổng quan.

| Tài liệu | Nội dung |
|---|---|
| [Product Overview](./docs/01-product/product-overview.md) | Tổng quan sản phẩm, giá trị và Core Capabilities |
| [Problem Statement](./docs/01-product/problem-statement.md) | Bài toán và vấn đề UniSupport cần giải quyết |
| [Goals & Non-Goals](./docs/01-product/goals-and-non-goals.md) | Mục tiêu và các nội dung không thuộc mục tiêu dự án |
| [Actors & Roles](./docs/01-product/actors-and-roles.md) | 04 Role và phạm vi trách nhiệm |
| [Product Scope](./docs/01-product/product-scope.md) | In-Scope, Out-of-Scope, Assumptions và Scope Change Control |

### Source of Truth

`product-scope.md` là tài liệu tham chiếu chính đối với:

- In-Scope.
- Out-of-Scope.
- Assumptions.
- Scope Change Control.
- Scope Acceptance.

Các tài liệu Product khác chỉ tóm tắt hoặc tham chiếu đến phạm vi này
để tránh lặp Requirement.

---

# 3. Domain & Business Rules

Thư mục `docs/02-domain/` định nghĩa các khái niệm và quy tắc nghiệp vụ
được sử dụng chung giữa nhiều Module.

| Tài liệu | Nội dung |
|---|---|
| [Terminology](./docs/02-domain/terminology.md) | Định nghĩa thuật ngữ sử dụng trong hệ thống |
| [Business Rules](./docs/02-domain/business-rules.md) | Các quy tắc nghiệp vụ dùng chung |
| [State Transition](./docs/02-domain/state-transition.md) | Trạng thái và vòng đời Ticket |

Các giá trị nghiệp vụ chưa được Aurora University xác nhận phải được đánh dấu:

`TBD – Pending Confirmation`

Business Rules không nên định nghĩa lại Functional Requirement của từng Module.

---

# 4. Product Requirements – Modules

Functional Requirements của UniSupport được phân chia theo Module.

Authentication & Authorization được định nghĩa trước
vì đây là nền tảng kiểm soát quyền truy cập cho các Module nghiệp vụ.

| Module | Tên Module | Phase | PRD |
|---|---|---|---|
| **M01** | Authentication & RBAC | P3 | [M01 PRD](./docs/03-modules/M01-auth-rbac/prd.md) |
| **M02** | Student Portal | P4 | [M02 PRD](./docs/03-modules/M02-student-portal/prd.md) |
| **M03** | Staff Desk | P4 | [M03 PRD](./docs/03-modules/M03-staff-desk/prd.md) |
| **M04** | Management & Administration | P5 | [M04 PRD](./docs/03-modules/M04-management-admin/prd.md) |
| **M05** | Dashboard & Reporting | P6 | [M05 PRD](./docs/03-modules/M05-dashboard-report/prd.md) |

---

# 5. Global Non-Functional Requirements

Các yêu cầu áp dụng cho toàn bộ hệ thống được quản lý riêng để tránh
lặp lại trong từng Module PRD.

[Global Non-Functional Requirements](./docs/03-modules/global-nfr.md)

Bao gồm các nhóm yêu cầu chính:

- Development & Testing sử dụng Mock Data.
- Hỗ trợ Tiếng Việt và Tiếng Anh.
- Responsive trên Desktop và Mobile.
- Giao diện đơn giản, nhất quán và dễ sử dụng.

---

# 6. Module Responsibility

Để tránh Requirement bị định nghĩa trùng lặp giữa nhiều Module,
mỗi nhóm chức năng có một Module chịu trách nhiệm chính.

| Responsibility | Owner |
|---|---|
| Authentication & Functional/Data Authorization | M01 |
| Student Ticket Interaction | M02 |
| Ticket Processing | M03 |
| Management, Deadline & System Configuration | M04 |
| Dashboard & Reporting | M05 |
| Shared Business Rules | `docs/02-domain/` |
| Shared UI / NFR | `global-nfr.md` |

Các Module khác có thể tham chiếu Requirement nhưng không nên
định nghĩa lại cùng một Business Rule hoặc Functional Requirement.

---

# 7. Requirement Documentation Convention

Mỗi Functional Requirement trong PRD được viết theo cấu trúc:

1. **User Story**
2. **Input**
3. **Processing**
4. **Output**
5. **Acceptance Criteria**

Acceptance Criteria ưu tiên sử dụng:

`Given / When / Then`

Ví dụ:

```text
Given: Staff có quyền xử lý Ticket.
When: Staff cập nhật trạng thái hợp lệ.
Then: Hệ thống lưu trạng thái mới và ghi nhận thay đổi vào Ticket History.