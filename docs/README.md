# Mục lục tài liệu dự án UniSupport

<!-- Hướng dẫn
- File này là mục lục BẮT BUỘC. Nội dung không có trong mục lục và không tìm được thì không được tính.
- Đổi tên hoặc gộp file thì sửa đường dẫn ở bảng dưới cho đúng.
- Mỗi thông tin chỉ có một nơi gốc; nơi khác dẫn lại mã (FR-…, Q-…, MS-…), không chép lại nội dung.
-->

## Thứ tự đọc tài liệu

1. **Bài toán và phạm vi:** [Tổng quan sản phẩm](01-product/README.md), [Chi tiết bài toán](01-product/problem-statement.md), [Phân vai](01-product/actors-and-roles.md), [Mục tiêu BG/UG và Non-goals](01-product/goals-and-non-goals.md), [Phạm vi cam kết trong Proposal](08-project/proposal.docx) và [Phạm vi chi tiết phục vụ PRD](01-product/product-scope.md)
2. **Yêu cầu chức năng & phi chức năng:** [Danh sách module](03-modules/README.md) → PRD từng phân hệ:
   - [M01 – Security, Authentication & RBAC](03-modules/M01-auth-rbac/prd.md)
   - [M02 – Student Portal](03-modules/M02-student-portal/prd.md)
   - [M03 – Staff Desk](03-modules/M03-staff-desk/prd.md)
   - [M04 – Management & Administration](03-modules/M04-management-admin/prd.md)
   - [M05 – Dashboard & Report](03-modules/M05-dashboard-report/prd.md)
   - [Yêu cầu phi chức năng (NFR)](05-non-functional-requirements/README.md)
3. **Nghiệm thu & Kiểm thử:** [Kịch bản test](06-acceptance/test-scenarios.md), [Ma trận truy vết](06-acceptance/traceability-matrix.md)
4. **Giá và kế hoạch:** [Báo giá (Excel)](08-project/quotation.xlsx), [Lịch baseline và cơ sở chia mốc](08-project/master-plan.md), [Workbook Master Plan](08-project/master-plan.xlsx), [Sổ rủi ro](08-project/risk-register.md)
5. **Cách làm việc & Chất lượng:** [Team Charter](08-project/team-charter.md), [Kế hoạch chất lượng](09-quality/quality-plan.md)
6. **Quản lý sản phẩm:** [Quy trình feedback](10-product-management/feedback-process.md), [Roadmap](10-product-management/roadmap.md), [Chỉ số giá trị](10-product-management/success-metrics.md)
7. **Quản trị dự án:** [Cơ chế báo cáo](11-governance/reporting.md), [Giám sát & EVM](11-governance/monitoring.md), [Quy trình Change Request](11-governance/change-control.md), [Báo cáo tuần minh họa](11-governance/weekly-report-example.md)
8. **Tài liệu kỹ thuật & Hỗ trợ:** [Nghiệp vụ miền & Quy tắc](02-domain/README.md) ([Thuật ngữ](02-domain/terminology.md), [Quy tắc](02-domain/business-rules.md), [Trạng thái](02-domain/state-transition.md)), [Luồng quy trình](04-workflows/README.md), [Kiến trúc hệ thống](07-architecture/README.md), [Hồ sơ phát hành Proposal](08-project/sent/README.md)

---

## Tra nhanh vị trí

| Nội dung | Ở đâu |
| --- | --- |
| **Phạm vi cam kết với khách hàng** | [Proposal](08-project/proposal.docx), mục Giải pháp và phạm vi thực hiện, tra phần In-Scope và Out-of-Scope. [Product Scope](01-product/product-scope.md) diễn giải phạm vi theo nhóm chức năng để tra PRD. |
| **Mục tiêu và giới hạn sản phẩm** | [Goals and Non-goals](01-product/goals-and-non-goals.md) là nguồn tra mục tiêu có mã `BG-xx`, `UG-xx` và giới hạn `NG-xx`. |
| **Nguồn lực & Nhân sự** | `08-project/master-plan.xlsx` sheet Resources, ước tính QA từ dòng 704; [08-project/team-charter.md](08-project/team-charter.md) |
| **Giá và hạng mục báo giá** | [08-project/quotation.xlsx](08-project/quotation.xlsx) (sheet Báo giá) |
| **Baseline đang áp dụng (3.2)** | [Baseline, người duyệt và ngày khởi động](08-project/master-plan.md#baseline-đang-áp-dụng). Workbook [Master Plan](08-project/master-plan.xlsx): sheet **Hướng dẫn** chỉ đường; Milestones ở sheet **Milestone Matrix**, WBS và Gantt ở sheet **Master Schedule (Gantt)**, Resources, Change Log. Khởi động **05/10/2026**, MS-08 **12/03/2027**. |
| **Phương án P-01: cửa sổ phản hồi 5 ngày (chưa áp dụng)** | [Workbook Master Plan](08-project/master-plan.xlsx), sheet **Nghiệm thu** kiểm cửa sổ phản hồi và sheet **Kịch bản** thử capacity, QA và CR-01. Ngày **17/03/2027** của MS-08 thuộc phép thử phản hồi. [Giải thích phép thử](08-project/master-plan.md#cách-nhận-feedback-của-client-sau-mỗi-milestone). |
| **Phương án P-02: lịch liên mốc (chưa áp dụng)** | Sheet **Lịch liên mốc** và **Tải liên mốc** trong [Master Plan](08-project/master-plan.xlsx). [Cách tính và trạng thái chờ duyệt](08-project/master-plan.md#phương-án-p-02-lịch-liên-mốc-chưa-áp-dụng). |
| **Phương án P-03: phản hồi 3 ngày (đề xuất thương lượng OQ-08)** | Sheet **Lịch phản hồi 3 ngày** và **Tải phản hồi 3 ngày** trong [Master Plan](08-project/master-plan.xlsx). [Phương án chọn để thương lượng](08-project/master-plan.md#phương-án-p-03-phản-hồi-3-ngày-đề-xuất-thương-lượng-oq-08). |
| **Sổ theo dõi rủi ro** | [08-project/risk-register.md](08-project/risk-register.md) |
| **Quy trình Change Request** | [11-governance/change-control.md](11-governance/change-control.md); [Mẫu issue Change Request](../.github/ISSUE_TEMPLATE/4-change-request.md) |
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
| **Kịch bản test** | `TS-xxx` (ví dụ `TS-001`) | `docs/06-acceptance/test-scenarios.md` | Mã AC hoặc NFR được test |
| **Hạng mục báo giá** | `Q-xx` | `docs/08-project/quotation.xlsx` | Module hoặc FR thuộc hạng mục |
| **Milestone** | `MS-01` – `MS-08` | `docs/08-project/master-plan.xlsx`, GitHub Milestones | Phần bàn giao, điều kiện nghiệm thu |
| **Công việc (Task)** | `#xx` | GitHub Issues | Mã FR, Milestone, owner theo vai trò hoặc assignee, hạn chót |
| **Mã giá theo vai trò, gói** | `DG01` – `DG11` | `docs/08-project/quotation.xlsx` sheet Đơn giá; dùng lại ở sheet Chi tiết effort và Resources của Master Plan | Vai trò hoặc gói, đơn giá |
| **Phương án kế hoạch chưa áp dụng** | `P-01` – `P-04` | `docs/08-project/master-plan.xlsx` sheet Change Log, bảng phương án | Sheet tính toán, câu hỏi mở liên quan |
| **Chỉ số giá trị** | `SM-01` – `SM-07` | `docs/10-product-management/success-metrics.md` | Mục tiêu, cách đo, người theo dõi |
| **Câu hỏi mở** | `OQ-01` – `OQ-08` | `docs/08-project/open-questions.md` | Người chốt, hạn chốt, mốc hoặc task bị chặn |
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
| **Feedback & Khiếu nại** | Mô phỏng | Đánh giá CSAT theo FR-STU-05 và kênh góp ý do PM/BA tiếp nhận |
| **Change Request** | Mô phỏng | Kịch bản áp dụng theo quy trình chuẩn khi có thay đổi |

---

## Người chịu trách nhiệm file Word/Excel

| File | Người chịu trách nhiệm chính |
| --- | --- |
| `08-project/proposal.docx` | Trần Vĩnh Đại — theo README cập nhật tại dfe998d |
| `08-project/quotation.xlsx` | Phùng Ngô Huy Bảo — theo README cập nhật tại dfe998d |
| `08-project/master-plan.xlsx` | Phùng Ngô Huy Bảo — theo README cập nhật tại dfe998d |
