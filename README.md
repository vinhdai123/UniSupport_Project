# UNISUPPORT PROJECT - HỆ THỐNG HỖ TRỢ SINH VIÊN

Kho lưu trữ tài liệu đặc tả và kế hoạch thực thi của dự án UniSupport (Aurora University).

---

## 1. Kế hoạch Tổng thể và Tiến độ Dự án (Master Plan & Schedule)

Toàn bộ lộ trình 22 tuần (11 Sprints), phân bổ nhân sự và luồng phụ thuộc công việc của dự án UniSupport được thiết lập và quản lý trực tiếp trên GitHub Projects:

| Chế độ hiển thị | Nội dung theo dõi | Liên kết truy cập |
| :--- | :--- | :--- |
| **Monthly Roadmap** | Biểu đồ Gantt theo dõi tiến độ chi tiết theo từng tháng | [Xem Monthly Roadmap](https://github.com/users/Huybao312/projects/2/views/1) |
| **Quarterly Roadmap** | Biểu đồ Gantt tổng thể toàn dự án theo từng giai đoạn (P1 - P9) | [Xem Quarterly Roadmap](https://github.com/users/Huybao312/projects/2/views/2) |
| **Master Plan Table** | Bảng dữ liệu chi tiết 30 công việc, thời lượng, Sprint và Dependencies | [Xem Bảng Master Plan](https://github.com/users/Huybao312/projects/2/views/4) |

---

## 2. Tổng quan Sản phẩm (Product Overview)

Tài liệu định nghĩa bài toán, mục tiêu, chân dung người dùng và giới hạn phạm vi dự án:

* [Tổng quan Sản phẩm (Product Overview)](./docs/01-product/product-overview.md)
* [Phát biểu Bài toán (Problem Statement)](./docs/01-product/problem-statement.md)
* [Mục tiêu Dự án (Goals & Objectives)](./docs/01-product/goals-and-non-goals.md)
* [Chân dung Người dùng (Actors & Roles)](./docs/01-product/actors-and-roles.md)
* [Phạm vi Sản phẩm & Giả định (Product Scope)](./docs/01-product/product-scope.md)

---

## 3. Quy tắc Nghiệp vụ Cốt lõi (Domain Rules)

Tài liệu định nghĩa thuật ngữ, quy tắc hệ thống (SLA) và vòng đời dữ liệu:

* [Từ điển Thuật ngữ (Terminology)](./docs/02-domain/terminology.md)
* [Quy tắc Nghiệp vụ (Business Rules & SLA)](./docs/02-domain/business-rules.md)
* [Vòng đời Trạng thái (State Transition)](./docs/02-domain/state-transition.md)

---

## 4. Hồ sơ Yêu cầu Sản phẩm (PRD - Modules)

Tài liệu Đặc tả Yêu cầu Sản phẩm được phân rã theo cấu trúc module chuẩn Agile. Theo nguyên tắc thiết kế hệ thống, phân hệ Xác thực (User Auth) được định nghĩa đầu tiên làm nền tảng, tiếp nối bằng các phân hệ nghiệp vụ lõi:

| Mã Module | Tên Phân hệ Nghiệp vụ | Giai đoạn | Tài liệu Đặc tả (PRD) |
| :--- | :--- | :--- | :--- |
| **MOD-AUTH** | Phân hệ Xác thực & Phân quyền (Auth & RBAC) | Phase P3 | [Xem PRD Phân hệ Xác thực](./docs/03-modules/M01-auth-rbac/prd.md) |
| **MOD-STU** | Phân hệ Sinh viên (Student Portal) | Phase P4 | [Xem PRD Phân hệ Sinh viên](./docs/03-modules/M02-student-portal/prd.md) |
| **MOD-STAFF**| Phân hệ Cán bộ (Staff Service Desk)| Phase P4 | [Xem PRD Phân hệ Cán bộ](./docs/03-modules/M03-staff-desk/prd.md) |
| **MOD-ADMIN**| Phân hệ Quản lý, Cấu hình & SLA | Phase P5 | [Xem PRD Phân hệ Quản trị](./docs/03-modules/M04-admin-config/prd.md) |
| **MOD-REP** | Phân hệ Dashboard & Báo cáo | Phase P6 | [Xem PRD Phân hệ Báo cáo](./docs/03-modules/M05-dashboard-report/prd.md) |
