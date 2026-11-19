# Quy trình tiếp nhận và xử lý feedback

## Kênh nhận feedback

- **Trong phạm vi Release 1.0:** sinh viên đánh giá Ticket ở trạng thái Hoàn thành (`Resolved`) theo [FR-STU-05](../03-modules/M02-student-portal/prd.md). Điểm 1–2 sao yêu cầu nhận xét. PM/BA hoặc đầu mối nhà trường đọc báo cáo CSAT và định tuyến thủ công cho đơn vị liên quan.
- **Góp ý chung:** PM/BA tiếp nhận qua email đầu mối, buổi demo, UAT hoặc họp định kỳ, rồi ghi [Feedback Issue](../../.github/ISSUE_TEMPLATE/3-feedback.md). Biểu mẫu góp ý In-App dùng chung và tự động chuyển CSAT thấp là ý tưởng backlog, chờ đánh giá phạm vi và phê duyệt riêng.
- **Sự cố khẩn:** báo đầu mối theo [Reporting](../11-governance/reporting.md) và lưu Issue. Không đưa thông tin cá nhân vào Issue công khai.

## Phân loại và định tuyến

| Loại | Người tiếp nhận và định tuyến | Hồ sơ và cách xử lý |
| --- | --- | --- |
| Sai lệch so với AC đã chốt | QA xác minh, Tech Lead chốt mức và phân công, PM chốt ưu tiên và hạn | [Bug Issue](../../.github/ISSUE_TEMPLATE/2-bug.md). Hạn theo severity và kết thúc tại QA Verify theo [Quality Plan](../09-quality/quality-plan.md#mức-độ-lỗi-và-cách-xử-lý). |
| Sự cố vận hành nghiêm trọng | DevOps và Tech Lead xử lý kỹ thuật; PM điều phối và thông báo đầu mối trường | Báo ngay khi phát hiện theo Reporting. Ghi riêng thời điểm tiếp nhận, cô lập hoặc khôi phục tạm và thời điểm Verify. Hạn khắc phục theo Quality Plan. |
| Khiếu nại dịch vụ hoặc CSAT thấp | PM/BA hoặc đầu mối trường chuyển thủ công cho trưởng phòng phụ trách | Ghi phản hồi và người xử lý; nếu phát hiện lỗi sản phẩm, mở Bug riêng. |
| Cải tiến UI/UX hoặc tính năng | PM/BA phối hợp UI/UX và Tech Lead đánh giá | Ghi backlog theo [Roadmap](roadmap.md). Đề xuất làm đổi cam kết chuyển [Change Request](../11-governance/change-control.md). |

## Ưu tiên

PM/BA đối chiếu giá trị, nhóm người dùng bị ảnh hưởng, rủi ro, effort và phụ thuộc. Ưu tiên trước phản hồi chặn luồng chính hoặc ảnh hưởng nghiệm thu. Cải tiến có phương án tạm được xếp sau việc chặn. Ghi quyết định, owner, hạn hoặc lý do hoãn trên Issue. Priority của backlog cải tiến và Severity của lỗi phục vụ hai quyết định riêng.

## Ai quyết định sau bàn giao

Theo mục 8 [Proposal](../08-project/proposal.docx), bảo hành kéo dài **30 ngày lịch từ ngày liền sau ngày ký nghiệm thu và bàn giao**. PM và Tech Lead điều phối khắc phục lỗi thuộc phạm vi bảo hành theo Quality Plan. Sau bảo hành, Aurora University quyết định vận hành. Tính năng mới và hỗ trợ dài hạn theo thỏa thuận riêng.
