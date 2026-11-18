# UniSupport — Student Support Management System

Hệ thống quản lý và xử lý yêu cầu hỗ trợ tập trung cho sinh viên Trường Đại học Aurora (Aurora University). Khách hàng và đội thực thi là Mô phỏng. Dự án được lập kế hoạch, đặc tả và quản trị theo chuẩn môn học Software Project Management (SPM).

- Hướng dẫn dùng bộ khung repo: [`HUONG-DAN.md`](HUONG-DAN.md).
- Toàn bộ tài liệu dự án: Bắt đầu từ mục lục [`docs/README.md`](docs/README.md) (thứ tự đọc, tra cứu nhanh, quy ước mã).
- Kế hoạch và theo dõi công việc: Xem tab Issues, Milestones và Projects của repository này.

---

## Thành viên nhóm thực hiện

| MSSV | Họ tên | Trách nhiệm tài liệu đề xuất |
| --- | --- | --- |
| 23090009  | Trần Vĩnh Đại | Proposal, Quản lý chất lượng, Quản lý sản phẩm |
| 23090011 | Nguyễn Thành An | Team Charter, Git |
| 23090017 | Phùng Ngô Huy Bảo | Master Plan, Quản trị và giám sát, Báo giá |
| 23090020 | Huỳnh Hữu Như Mẫn | PRD, Review |

MSSV và phân công tài liệu theo bản README được nhóm cập nhật tại commit dfe998d. Trưởng nhóm đối chiếu feedback R1. Reviewer, dự phòng và quyền merge được xác nhận theo Team Charter. Ánh xạ tên với tài khoản GitHub do thành viên bổ sung.

---

## Cấu trúc thư mục tài liệu (`docs/`)

Toàn bộ tài liệu quản lý dự án được tổ chức chuẩn hóa theo 11 phân mục của `spm-starter`:

1. [`01-product/`](docs/01-product/README.md): Tổng quan sản phẩm, bài toán nghiệp vụ, mục tiêu, đối tượng sử dụng và phạm vi.
2. [`02-domain/`](docs/02-domain/README.md): Nghiệp vụ miền, thuật ngữ chuẩn hóa, quy tắc nghiệp vụ và vòng đời chuyển trạng thái Ticket.
3. [`03-modules/`](docs/03-modules/README.md): Đặc tả yêu cầu chức năng (PRD) của 5 module cốt lõi (M01–M05).
4. [`04-workflows/`](docs/04-workflows/README.md): Sơ đồ luồng tiếp nhận, xử lý, phân luồng và đánh giá chất lượng dịch vụ.
5. [`05-non-functional-requirements/`](docs/05-non-functional-requirements/README.md): Yêu cầu phi chức năng (Mock data, đa ngôn ngữ, web responsive, usability, hiệu năng, bảo mật).
6. [`06-acceptance/`](docs/06-acceptance/test-scenarios.md): Kịch bản kiểm thử (Test Scenarios) và Ma trận truy vết yêu cầu (Traceability Matrix).
7. [`07-architecture/`](docs/07-architecture/README.md): Kiến trúc hệ thống phân tầng và giải pháp công nghệ.
8. [`08-project/`](docs/08-project/): Kế hoạch tổng thể 23 tuần ([master-plan.xlsx](docs/08-project/master-plan.xlsx)), Báo giá ([quotation.xlsx](docs/08-project/quotation.xlsx)), Proposal ([proposal.docx](docs/08-project/proposal.docx)), [Team Charter](docs/08-project/team-charter.md), Sổ rủi ro, Giả định, Ràng buộc.
9. [`09-quality/`](docs/09-quality/quality-plan.md): Kế hoạch chất lượng (QA/QC, Definition of Done, Quản lý lỗi, Điều kiện release).
10. [`10-product-management/`](docs/10-product-management/): Quy trình feedback, Lộ trình sản phẩm (Roadmap) và Chỉ số giá trị (Success Metrics).
11. [`11-governance/`](docs/11-governance/): Cơ chế báo cáo, Giám sát tiến độ & EVM, và Quy trình kiểm soát thay đổi (Change Request).
