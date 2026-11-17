# Báo cáo tuần minh họa UniSupport

Mô phỏng lập ngày 17/11/2026 cho đợt rà soát tài liệu R1. Người lập là PM kiêm BA. Người nhận dự kiến là nhóm và đại diện Aurora University Mô phỏng. Trạng thái hồ sơ là Vàng vì còn quyết định nghiệp vụ và thông tin thành viên cần xác nhận.

## Kết quả chuẩn bị

| Hạng mục | Bằng chứng | Trạng thái |
| --- | --- | --- |
| Kế hoạch bàn giao | [Master Plan](../08-project/master-plan.md), Milestone Matrix của workbook | Đề xuất đồng bộ MS-01 đến MS-08, chờ review PR |
| Đặc tả và kiểm thử | [PRD](../03-modules/README.md), [RTM](../06-acceptance/traceability-matrix.md) | 33 FR, 97 AC chức năng, 19 AC NFR toàn cục và 6 ngưỡng NFR đã có kịch bản dự kiến |
| Hồ sơ Proposal | [Hồ sơ phát hành](../08-project/sent/README.md) | Đã xuất PDF, đang chờ xác nhận gửi |
| Công việc và thay đổi | GitHub Issues và Milestones của repo, lọc nhãn task hoặc change-request | PM đối chiếu metadata với PR và baseline |

## Theo dõi tiến độ và giờ công

Dự án đang ở mức lập tài liệu và kế hoạch theo chuẩn môn học. Giờ công thực tế, số test đã thực thi, PV, EV, AC và SPI/CPI ghi **N/A — chưa có dữ liệu thực thi**. Số lượng test ở trên là kịch bản đã soạn. Khi có thực thi, PM tổng hợp giờ từ Issue và đối chiếu theo WBS/Resources, tránh cộng trùng parent và việc con.

## Vướng mắc và quyết định

| Nội dung | Người theo dõi | Ảnh hưởng | Bước tiếp theo |
| --- | --- | --- | --- |
| MSSV và ánh xạ tên–GitHub | Trưởng nhóm | Chưa hoàn thiện thông tin nộp bài | Thành viên xác nhận tại README |
| Tham số nghiệp vụ và NFR còn đề xuất | PM/BA và QA | Chưa đủ căn cứ chốt nghiệm thu | Ghi quyết định tại Issue, đồng bộ PRD và test |
| Ngày baseline đã qua so với ngày lập báo cáo | PM | Ngày trong mô phỏng chưa phản ánh lịch triển khai thực tế | Xác nhận tình huống mô phỏng hoặc tái lập lịch qua thay đổi baseline có lưu vết |

## Kế hoạch kỳ tiếp theo

Người review độc lập đối chiếu ba luồng đăng nhập, gửi Ticket và CSV từ Q-xx đến FR/AC, MS-xx, parent task và TS-xxx. Nhóm xác nhận phân công Charter, tham số còn mở và hoàn thiện thông tin thành viên. PM theo dõi [CR-01 Mô phỏng](https://github.com/vinhdai123/UniSupport_Project/issues/102) theo [quy trình thay đổi](change-control.md).
