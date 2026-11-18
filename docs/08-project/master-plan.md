# Master Plan

[Workbook Master Plan](master-plan.xlsx) là nguồn tra ngày, effort, nguồn lực, các kịch bản và lịch sử phiên bản của kế hoạch **Mô phỏng**. Dùng sheet **Milestone Matrix** và **Master Schedule (Gantt)** cho baseline, **Nghiệm thu** và **Kịch bản** cho phép thử 2.2.

## Cách chia milestone

MS-01 giao đăng nhập xuyên suốt từ giao diện đến dữ liệu trên Staging để khách có thể thử sớm. MS-02 mở rộng sang tài khoản và phân quyền. MS-03 và MS-04 nối thành vòng đời Ticket từ phía sinh viên đến cán bộ và quản lý. MS-05 giao Dashboard và CSV sau khi có nghiệp vụ tạo dữ liệu. MS-06 kiểm toàn bộ luồng tích hợp, MS-07 xác nhận UAT và sẵn sàng phát hành, MS-08 giao hệ thống trên Production. Thao tác dùng thử và điều kiện nghiệm thu của từng mốc nằm trong **Milestone Matrix**.

## Phụ thuộc giữa các milestone

Luồng đăng nhập trên Staging cần xong WBS 3.6 trước khi khách dùng thử ở WBS 3.9. Theo dõi môi trường [#52](https://github.com/vinhdai123/UniSupport_Project/issues/52), API [#53](https://github.com/vinhdai123/UniSupport_Project/issues/53), phiên [#54](https://github.com/vinhdai123/UniSupport_Project/issues/54) và ca kiểm [#58](https://github.com/vinhdai123/UniSupport_Project/issues/58) trước khi chốt [#101](https://github.com/vinhdai123/UniSupport_Project/issues/101). Tech Lead chốt hạn nội bộ từ WBS trước khi cập nhật Issue.

MS-04 cung cấp dữ liệu và quyền cho phần tích hợp ở MS-05. Trong lúc chờ xác nhận, WBS 6.4 có thể chuẩn bị cấu trúc CSV, dữ liệu giả lập và ca kiểm. Bước tích hợp với dữ liệu và quyền của bản MS-04 cùng WBS 6.1 phải chờ xác nhận. MS-07 phải hoàn tất trước triển khai Production. Tại MS-08, ký bàn giao và kích hoạt bảo hành chờ khách xác nhận, còn bảo hành tính từ ngày liền sau ngày ký. Tra **Nghiệm thu** để xem việc được chuẩn bị và việc bị chặn theo từng mốc.

## Effort cho test, regression và sửa lỗi

Các việc kiểm và sửa dự kiến nằm trong WBS và [Báo giá](quotation.xlsx). WBS 3.6/3.5 dùng Q-03, 4.2 dùng Q-04, 4.6 dùng Q-05 và 5.3 dùng Q-06. WBS 6.3–6.4 dùng Q-07/Q-08, 7.2–7.4 dùng Q-08, 8.3–8.4 dùng Q-09/Q-10 và 9.2 dùng Q-10. **Resources** đối chiếu effort theo vai trò, tuần và mốc. Dùng định mức QA ở phần cuối sheet để kiểm sức chứa khi thêm một vòng hồi quy.

MS-05 cần bằng chứng kiểm CSV theo WBS 6.4 và [TS-095](../06-acceptance/test-scenarios.md), gồm bộ lọc, quyền dữ liệu và đối chiếu kết quả với Dashboard. Đề xuất cập nhật [#22](https://github.com/vinhdai123/UniSupport_Project/issues/22) và đối chiếu với [#90](https://github.com/vinhdai123/UniSupport_Project/issues/90). MS-06 hồi quy CSV trên bản tích hợp và tổng hợp các ngưỡng NFR thuộc mốc đó.

## Dự phòng cho thay đổi và rủi ro

Tra tổng giờ dự phòng ở **Resources** và WBS `CR.01`. Đây là năng lực đề xuất huy động cho thay đổi hoặc rủi ro, được theo dõi riêng với effort đã báo giá cho test, sửa lỗi và bảo hành. PM kiểm khả dụng theo đúng vai trò và tuần. Phần việc phát sinh ngoài phạm vi được định giá trong CR để hai bên xác nhận.

[CR-01](https://github.com/vinhdai123/UniSupport_Project/issues/102) thử thêm XLSX. Sheet **Kịch bản** cho thấy Junior Backend và Junior Frontend kín tải trong ba tuần cuối trước MS-05. QA cũng kín tải ở tuần chốt MS-05 và MS-06 và thiếu giờ nếu vừa vắng vừa cần kiểm lại. PM chỉ trình đưa XLSX vào mốc khi có phương án tái phân bổ và kiểm hồi quy khả thi. CR hiện chờ quyết định, baseline tiếp tục dùng CSV.

## Cách nhận feedback của client sau mỗi milestone

PM gửi phiên bản, quyền truy cập, kịch bản và hồ sơ kiểm. Ghi thời điểm khách nhận đủ hồ sơ và hạn phản hồi theo mục 8 [Proposal](proposal.docx). Mỗi phản hồi có Issue, phiên bản, người chịu trách nhiệm, bằng chứng và kết quả kiểm lại. Khi hồ sơ thay đổi sau sửa, PM thống nhất hạn của lần gửi lại. Xác nhận mốc cần bằng chứng bằng văn bản.

Sheet **Nghiệm thu** mô phỏng khách dùng hết hạn phản hồi theo lịch làm việc. MS-04 và MS-08 lệch baseline nếu gửi đủ hồ sơ theo ngày sẵn sàng hiện tại. Kết quả ở từng dòng tính riêng, chưa cộng dồn phụ thuộc. Dùng phần phép thử ở cuối sheet để xem tác động của vòng sửa và kiểm bổ sung.

## Thay đổi kế hoạch

Khi chỉnh kế hoạch theo feedback nội bộ hoặc của giảng viên, ghi căn cứ và phiên bản trong **Change Log** và lịch sử PR. Bản 2.2 là dự thảo rà soát. Sau khi khách nhận Proposal, đề nghị đổi phạm vi, giá hoặc mốc được xử lý theo [Change Control](../11-governance/change-control.md). Khi CR được duyệt, lưu bản trước, thêm phiên bản, ngày, mã CR và tác động vào **Change Log**. Cập nhật các nguồn liên quan, gồm báo giá, WBS, Resources, PRD, test và các mốc trên GitHub. Tra bằng chứng gửi tại [Bản đã gửi khách](sent/README.md).
