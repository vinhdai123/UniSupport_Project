# Mục lục tài liệu dự án UniSupport

<!-- Hướng dẫn
- File này là mục lục BẮT BUỘC. Nội dung không có trong mục lục và không tìm được thì không được tính.
- Đổi tên hoặc gộp file thì sửa đường dẫn ở bảng dưới cho đúng.
- Mỗi thông tin chỉ có một nơi gốc; nơi khác dẫn lại mã (FR-…, Q-…, MS-…), không chép lại nội dung.
-->

## Thứ tự đọc tài liệu

1. **Bài toán và phạm vi:** [Proposal (Word)](08-project/proposal.docx), [Tổng quan sản phẩm](01-product/README.md) ([Chi tiết bài toán](01-product/problem-statement.md), [Mục tiêu](01-product/goals-and-non-goals.md), [Phân vai](01-product/actors-and-roles.md), [Phạm vi](01-product/product-scope.md))
2. **Yêu cầu chức năng & phi chức năng:** [Danh sách module](03-modules/README.md) → PRD từng phân hệ:
   - [M01 – Security, Authentication & RBAC](03-modules/M01-auth-rbac/prd.md)
   - [M02 – Student Portal](03-modules/M02-student-portal/prd.md)
   - [M03 – Staff Desk](03-modules/M03-staff-desk/prd.md)
   - [M04 – Management & Administration](03-modules/M04-management-admin/prd.md)
   - [M05 – Dashboard & Report](03-modules/M05-dashboard-report/prd.md)
   - [Yêu cầu phi chức năng (NFR)](05-non-functional-requirements/README.md)
3. **Nghiệm thu & Kiểm thử:** [Kịch bản test](06-acceptance/test-scenarios.md), [Ma trận truy vết](06-acceptance/traceability-matrix.md)
4. **Giá và kế hoạch:** [Báo giá (Excel)](08-project/quotation.xlsx), [Master Plan](08-project/master-plan.md) + [Master Plan (Excel)](08-project/master-plan.xlsx), [Sổ rủi ro](08-project/risk-register.md)
5. **Cách làm việc & Chất lượng:** [Team Charter](08-project/team-charter.md), [Kế hoạch chất lượng](09-quality/quality-plan.md)
6. **Quản lý sản phẩm:** [Quy trình feedback](10-product-management/feedback-process.md), [Roadmap](10-product-management/roadmap.md), [Chỉ số giá trị](10-product-management/success-metrics.md)
7. **Quản trị dự án:** [Cơ chế báo cáo](11-governance/reporting.md), [Giám sát & EVM](11-governance/monitoring.md), [Quy trình Change Request](11-governance/change-control.md), [Báo cáo tuần minh họa](11-governance/weekly-report-example.md)
8. **Tài liệu kỹ thuật & Hỗ trợ:** [Nghiệp vụ miền & Quy tắc](02-domain/README.md) ([Thuật ngữ](02-domain/terminology.md), [Quy tắc](02-domain/business-rules.md), [Trạng thái](02-domain/state-transition.md)), [Luồng quy trình](04-workflows/README.md), [Kiến trúc hệ thống](07-architecture/README.md), [Hồ sơ phát hành Proposal](08-project/sent/README.md)

---

## Tra nhanh vị trí

| Nội dung | Ở đâu |
| --- | --- |
| **Phạm vi (Scope: Làm và Không làm)** | `08-project/proposal.docx`; `01-product/goals-and-non-goals.md`, `01-product/product-scope.md` |
| **Nguồn lực & Nhân sự** | `08-project/master-plan.xlsx` sheet Resources, ước tính QA từ dòng 704; [08-project/team-charter.md](08-project/team-charter.md) |
| **Giá và hạng mục báo giá** | [08-project/quotation.xlsx](08-project/quotation.xlsx) (sheet Báo giá) |
| **Kế hoạch 23 tuần & Milestone** | [08-project/master-plan.xlsx](08-project/master-plan.xlsx), [08-project/master-plan.md](08-project/master-plan.md) |
| **Sổ theo dõi rủi ro** | [08-project/risk-register.md](08-project/risk-register.md) |
| **Quy trình Change Request** | [11-governance/change-control.md](11-governance/change-control.md); Issue mẫu `4-change-request.md` |
| **Definition of Done (DoD)** | [09-quality/quality-plan.md](09-quality/quality-plan.md) mục Definition of Done |
| **Giả định, ràng buộc, câu hỏi mở** | [assumptions.md](08-project/assumptions.md), [constraints.md](08-project/constraints.md), [open-questions.md](08-project/open-questions.md) |
| **Tuyến báo cáo & Họp định kỳ** | [11-governance/reporting.md](11-governance/reporting.md) |
| **Giám sát chỉ số & Ngưỡng cảnh báo** | [11-governance/monitoring.md](11-governance/monitoring.md) |

---

## Quy ước mã định danh

| Đối tượng | Dạng | Nơi gốc | Liên kết phải ghi |
| --- | --- | --- | --- |
| **Module** | `M01` – `M05` | `docs/03-modules/` | |
| **Yêu cầu chức năng** | `FR-AUTH-xx`, `FR-STU-xx`, `FR-STF-xx`, `FR-ADM-xx`, `FR-RPT-xx` | `prd.md` từng module | |
| **Tiêu chí nghiệm thu** | `FR-xxx-xx/AC-xx` | `prd.md` từng module | |
| **Yêu cầu phi chức năng** | `NFR-GLOBAL-xx`, `NFR-PERF-xx`, `NFR-SEC-xx` | `docs/05-non-functional-requirements/README.md` | |
| **Kịch bản test** | `TS-xx` | `docs/06-acceptance/test-scenarios.md` | Mã AC hoặc NFR được test |
| **Hạng mục báo giá** | `Q-xx` | `docs/08-project/quotation.xlsx` | Module hoặc FR thuộc hạng mục |
| **Milestone** | `MS-01` – `MS-08` | `docs/08-project/master-plan.xlsx`, GitHub Milestones | Phần bàn giao, điều kiện nghiệm thu |
| **Công việc (Task)** | `#xx` | GitHub Issues | Mã FR, Milestone, owner theo vai trò hoặc assignee, hạn chót |
| **Rủi ro** | `R-01` – `R-13` | `docs/08-project/master-plan.xlsx` sheet Risk Register, dẫn từ `risk-register.md` | Chủ sở hữu (Owner), giải pháp ứng phó |
| **Change Request** | `CR-xx` | GitHub Issues (nhãn `change-request`) | Tài liệu và task đã cập nhật |
| **Giả định** | `A-xx` | `docs/08-project/proposal.docx` mục 3, dẫn từ `assumptions.md` | Tác động và trạng thái |

---

## Dữ liệu mô phỏng

| Phần | Mô phỏng? | Ghi chú |
| --- | --- | --- |
| **Khách hàng** | Mô phỏng | Aurora University (Trường Đại học Aurora) |
| **Đội thực thi** | Mô phỏng | 1 PM/BA, 1 Tech Lead, 2 FE, 2 BE, 1 DevOps, 1 QA, 1 UI/UX |
| **Dữ liệu kiểm thử** | Mô phỏng | 100% Mock Data trên Staging (4 nhóm role, 50 tickets mẫu) |
| **Feedback & Khiếu nại** | Mô phỏng | Kịch bản khảo sát CSAT và biểu mẫu In-App |
| **Change Request** | Mô phỏng | Kịch bản áp dụng theo quy trình chuẩn khi có thay đổi |

---

## Người chịu trách nhiệm file Word/Excel

| File | Người chịu trách nhiệm chính |
| --- | --- |
| `08-project/proposal.docx` | Trần Vĩnh Đại — phân công đề xuất theo Charter |
| `08-project/quotation.xlsx` | Huỳnh Hữu Như Mẫn — phân công đề xuất theo Charter |
| `08-project/master-plan.xlsx` | Huỳnh Hữu Như Mẫn — phân công đề xuất theo Charter |
