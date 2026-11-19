# Chỉ số giá trị (Success Metrics & KPIs)

Các mục tiêu dưới đây là **đề xuất trong tình huống Mô phỏng**, cần Aurora University và PM xác nhận trước khi dùng để đánh giá. Thời kỳ báo cáo dùng UTC+7. Khi mẫu số bằng 0 hoặc thiếu dữ liệu bắt buộc, ghi N/A và lý do. Số liệu chưa đủ kỳ theo dõi được ghi là tạm tính.

| Chỉ số | Mục tiêu đề xuất | Đối tượng, cách đo và nguồn | Kỳ và người theo dõi |
| --- | --- | --- | --- |
| Kích hoạt sinh viên | ≥ 80% sau 3 tháng đầu | Số tài khoản sinh viên thuộc danh sách được cấp lúc mở vận hành có lần đăng nhập thành công đầu tiên trong kỳ ÷ số tài khoản sinh viên hợp lệ trong danh sách đó. Danh sách cấp và lịch sử đăng nhập là hai nguồn đối soát. Báo cáo riêng nhóm cấp bổ sung. | Lũy kế từ mở vận hành, chốt sau 3 tháng. PM/BA và Phòng CTSV. |
| Kích hoạt cán bộ | 100% sau 3 tháng đầu | Cùng định nghĩa kích hoạt nhưng dùng danh sách tài khoản **cán bộ xử lý** và kết quả đăng nhập của riêng nhóm này. Mỗi tài khoản tính một lần. | Lũy kế từ mở vận hành, chốt sau 3 tháng. PM/BA và đầu mối các phòng. |
| Thời gian phản hồi đầu tiên (FRT) | ≤ 4 giờ làm việc mỗi Ticket | Với Ticket tạo trong tuần, đo từ lúc tạo đến phản hồi công khai đầu tiên của cán bộ theo lịch làm việc đã xác nhận. Dùng lịch sử Ticket; ghi riêng số chưa phản hồi và số đã quá mục tiêu tại ngày chốt. | Hằng tuần. Trưởng phòng. |
| Tỷ lệ đúng hạn SLA | ≥ 90% | Ticket duy nhất vào `Resolved` lần đầu trong kỳ và đúng hạn ÷ số Ticket duy nhất vào `Resolved` lần đầu trong kỳ có SLA hợp lệ. Dùng lịch sử trạng thái, hạn và quy tắc dừng đồng hồ đã xác nhận. Báo riêng bản ghi thiếu SLA. | Hằng tuần và hằng tháng. Trưởng phòng và PM/BA. |
| Tỷ lệ Ticket mở lại | ≤ 5% | Mẫu số là Ticket duy nhất lần đầu vào `Resolved` trong tháng. Tử số là Ticket trong cùng nhóm có ít nhất một sự kiện `Resolved → In Progress` do mở lại trong cửa sổ PRD đã xác nhận, mỗi Ticket tính một lần. Dùng lịch sử trạng thái, chốt sau khi toàn bộ nhóm qua cửa sổ mở lại. Nếu cửa sổ chưa xác nhận, ghi N/A. | Theo nhóm tháng. QA và trưởng phòng. |
| CSAT | ≥ 4,2/5 | Tổng điểm ÷ số đánh giá hợp lệ gửi trong kỳ theo FR-STU-05, mỗi Ticket tối đa một đánh giá. Báo kèm số đánh giá làm mẫu. | Hằng tuần. Trưởng phòng và PM/BA. |
| Độ sẵn sàng | ≥ 99,5% | Số phút dịch vụ sẵn sàng ÷ số phút trong khung vận hành đã xác nhận. Đối chiếu giám sát dịch vụ và biên bản sự cố. Khi chưa chốt khung giờ hoặc thiếu log, ghi N/A. | Hằng tháng. DevOps và Tech Lead. |

Các công thức tỷ lệ nhân kết quả với 100%. Nếu nguồn dữ liệu chưa có báo cáo sẵn, PM xác định cách trích xuất được cấp quyền trước khi đo. Chỉ số vận hành và mục tiêu xử lý Ticket dùng quy tắc SLA từ [PRD](../03-modules/M04-management-admin/prd.md), [nghiệp vụ miền](../02-domain/business-rules.md) và trạng thái xác nhận tại [OQ-05](../08-project/open-questions.md). Hạn xử lý **lỗi phần mềm** theo [Quality Plan](../09-quality/quality-plan.md#mức-độ-lỗi-và-cách-xử-lý).
