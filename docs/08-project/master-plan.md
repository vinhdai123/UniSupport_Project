# Master Plan

[Workbook Master Plan](master-plan.xlsx) là nguồn tra ngày, effort, nguồn lực, các kịch bản và lịch sử phiên bản của kế hoạch **Mô phỏng**. Dùng sheet **Milestone Matrix** và **Master Schedule (Gantt)** cho baseline, **Nghiệm thu** và **Kịch bản** cho phép thử 2.2.

## Cách chia milestone

MS-01 giao đăng nhập xuyên suốt từ giao diện đến dữ liệu trên Staging để khách có thể thử sớm. MS-02 mở rộng sang tài khoản và phân quyền. MS-03 và MS-04 nối thành vòng đời Ticket từ phía sinh viên đến cán bộ và quản lý. MS-05 giao Dashboard và CSV sau khi có nghiệp vụ tạo dữ liệu. MS-06 kiểm toàn bộ luồng tích hợp, MS-07 xác nhận UAT và sẵn sàng phát hành, MS-08 giao hệ thống trên Production. Thao tác dùng thử và điều kiện nghiệm thu của từng mốc nằm trong **Milestone Matrix**.

**Phân kỳ routing R2.** Tại MS-03, #60 bàn giao API tạo Ticket có lưu phòng đích từ danh mục đã cấu hình sẵn. #93 kiểm chứng TS-021 trước xác nhận mốc và không chờ danh sách Staff Desk #67. Tại MS-04, #63 hoàn thiện hàng đợi theo quyền và nhánh dự phòng khi thiếu quy tắc trên kết quả đã có ở #60; việc phân công và chuyển cấp theo WBS 4.4/FR-STF-02/04.

## Phụ thuộc giữa các milestone

Luồng đăng nhập trên Staging cần xong WBS 3.6 trước khi khách dùng thử ở WBS 3.9. Theo dõi môi trường [#52](https://github.com/vinhdai123/UniSupport_Project/issues/52), API [#53](https://github.com/vinhdai123/UniSupport_Project/issues/53), phiên [#54](https://github.com/vinhdai123/UniSupport_Project/issues/54) và ca kiểm [#58](https://github.com/vinhdai123/UniSupport_Project/issues/58) trước khi chốt [#101](https://github.com/vinhdai123/UniSupport_Project/issues/101). Issue ghi hạn nội bộ theo WBS và đầu ra trung gian. MS-01 dùng tài khoản giả lập tạo sẵn. QA nhận UI tối thiểu của #101 trước khi kiểm vòng đầu ở #58. #101 chốt sau hồi quy, quản trị tài khoản và đặt lại mật khẩu được giao tại MS-02.

MS-04 cung cấp dữ liệu và quyền cho phần tích hợp ở MS-05. Trong lúc chờ xác nhận, WBS 6.4 có thể chuẩn bị cấu trúc CSV, dữ liệu giả lập và ca kiểm. Bước tích hợp với dữ liệu và quyền của bản MS-04 cùng WBS 6.1 phải chờ xác nhận. MS-07 phải hoàn tất trước triển khai Production. Tại MS-08, ký bàn giao và kích hoạt bảo hành chờ khách xác nhận, còn bảo hành tính từ ngày liền sau ngày ký. Tra **Nghiệm thu** để xem việc được chuẩn bị và việc bị chặn theo từng mốc.

## Effort cho test, regression và sửa lỗi

Các việc kiểm và sửa dự kiến nằm trong WBS và [Báo giá](quotation.xlsx). WBS 3.6/3.5 dùng Q-03, 4.2 dùng Q-04, 4.6 dùng Q-05 và 5.3 dùng Q-06. WBS 6.3–6.4 dùng Q-07/Q-08, 7.2–7.4 dùng Q-08, 8.3–8.4 dùng Q-09/Q-10 và 9.2 dùng Q-10. **Resources** đối chiếu effort theo vai trò, tuần và mốc. Dùng định mức QA ở phần cuối sheet để kiểm sức chứa khi thêm một vòng hồi quy.

MS-05 cần bằng chứng kiểm CSV theo WBS 6.4 và [TS-095](../06-acceptance/test-scenarios.md), gồm bộ lọc, quyền dữ liệu và đối chiếu kết quả với Dashboard. Phạm vi kiểm lần đầu được ghi tại [#22](https://github.com/vinhdai123/UniSupport_Project/issues/22) và đối chiếu với [#90](https://github.com/vinhdai123/UniSupport_Project/issues/90). MS-06 hồi quy CSV trên bản tích hợp và tổng hợp các ngưỡng NFR thuộc mốc đó.

Đề xuất phân bổ trong Q-04 cho tuần bắt đầu 07/12/2026. Tech Lead và QA cần đối chiếu cả phần phân luồng lẫn các đầu việc còn lại trong cùng hai dòng **Resources**.

| Vai trò và WBS | Giờ đã phân bổ | Phần phân luồng MS-03 | Giờ cho phần việc còn lại trong dòng |
| --- | ---: | ---: | ---: |
| R04 Backend, WBS 4.1, dòng 411 | 40 | 6 giờ đề xuất cho lưu phòng tiếp nhận theo danh mục khi tạo Ticket | 34 |
| R08 QA, WBS 4.2, dòng 429 | 9 | 2 giờ đề xuất cho bằng chứng TS-021 | 7 |

**Chờ xác nhận định mức.** Tech Lead kiểm tổng giờ phát triển của dòng 411 và khả năng bàn giao đầu ra #60 trước lượt kiểm cuối. QA kiểm tổng giờ của dòng 429, gồm TS-021, các ca chức năng/quyền còn lại và thời gian kiểm lại. Ghi kết luận ở #60 và #93, gồm phạm vi đã ước lượng, giờ cho từng phần, hạn bàn giao nội bộ, người xác nhận và ngày quyết định. Nếu phần việc vượt số giờ trong bảng hoặc không kịp cửa sổ kiểm, PM đánh giá lại phân bổ và lịch trước khi cam kết MS-03.

## Dự phòng cho thay đổi và rủi ro

Tra tổng giờ dự phòng ở **Resources** và WBS `CR.01`. Đây là năng lực đề xuất huy động cho thay đổi hoặc rủi ro, được theo dõi riêng với effort đã báo giá cho test, sửa lỗi và bảo hành. PM kiểm khả dụng theo đúng vai trò và tuần. Phần việc phát sinh ngoài phạm vi được định giá trong CR để hai bên xác nhận.

[CR-01](https://github.com/vinhdai123/UniSupport_Project/issues/102) thử thêm XLSX. Sheet **Kịch bản** cho thấy Junior Backend và Junior Frontend kín tải trong ba tuần cuối trước MS-05. QA cũng kín tải ở tuần chốt MS-05 và MS-06 và thiếu giờ nếu vừa vắng vừa cần kiểm lại. PM chỉ trình đưa XLSX vào mốc khi có phương án tái phân bổ và kiểm hồi quy khả thi. CR hiện chờ quyết định, baseline tiếp tục dùng CSV.

## Cách nhận feedback của client sau mỗi milestone

PM gửi phiên bản, quyền truy cập, kịch bản và hồ sơ kiểm. Ghi thời điểm khách nhận đủ hồ sơ và hạn phản hồi theo mục 8 [Proposal](proposal.docx). Mỗi phản hồi có Issue, phiên bản, người chịu trách nhiệm, bằng chứng và kết quả kiểm lại. Khi hồ sơ thay đổi sau sửa, PM thống nhất hạn của lần gửi lại. Xác nhận mốc cần bằng chứng bằng văn bản.

Sheet **Nghiệm thu** mô phỏng khách dùng hết hạn phản hồi theo lịch làm việc. MS-04 và MS-08 lệch baseline nếu gửi đủ hồ sơ theo ngày sẵn sàng hiện tại. Kết quả ở từng dòng tính riêng, chưa cộng dồn phụ thuộc. Dùng phần phép thử ở cuối sheet để xem tác động của vòng sửa và kiểm bổ sung.

## Phương án lịch liên mốc 2.3

Tra **Lịch liên mốc** để xem ngày gửi đủ hồ sơ, phản hồi, xác nhận từng mốc và các WBS đã dời. Tra **Tải liên mốc** để đối chiếu từng phân bổ với Resources và xem tải theo vai trò/tuần đến hết bảo hành. Phép thử dùng đủ hạn phản hồi ở mỗi mốc, giả định khách đồng ý khi hết hạn, chưa tính ngày nghỉ hay vòng sửa bổ sung.

Phương án giữ WBS 3.8 độc lập với xác nhận MS-02, dời toàn bộ WBS 6.4 sau xác nhận MS-04 và giữ các việc còn lại theo tuần trọn để chuyển phân bổ nguồn lực. MS-08 dành thời gian phản hồi sau khi có kết quả Production và giữ thời lượng ký bàn giao của WBS 9.3. Bảo hành tính từ ngày liền sau ký theo Proposal.

Tải thử gồm giờ triển khai và bảo hành gốc, dự phòng ở tuần gốc và giờ PM/BA bổ sung đề xuất cho các cửa sổ phản hồi. Các tuần ngoài baseline dùng trần nguồn lực mô phỏng. Trước khi duyệt, PM kiểm ngày nghỉ, khả dụng và tác động tới cam kết/giá tại [OQ-08](open-questions.md). Sheet **Change Log** ghi 2.3 là phương án, bảng milestone và báo giá tiếp tục theo baseline.

## Phương án phản hồi 3 ngày 2.4

Phương án được chọn để thương lượng tại OQ-08 là khách phản hồi trong 3 ngày làm việc sau khi nhận đủ hồ sơ. Sheet **Lịch phản hồi 3 ngày** tính lại WBS theo ngày làm việc qua toàn chuỗi và giữ hai ngày ký MS-08 sau khi hết hạn phản hồi. WBS 3.8 tiếp tục chạy độc lập với xác nhận MS-02, WBS 6.4 bắt đầu sau xác nhận MS-04.

Nếu khách đồng ý ở cuối mỗi cửa sổ, lịch chưa tính ngày nghỉ hoặc lần gửi lại, MS-08 dự kiến ký **19/04/2027**, tuần **29**. Bảo hành bắt đầu **20/04/2027** và kết thúc **19/05/2027** theo giả định ngày ký này. Sheet **Tải phản hồi 3 ngày** phân bổ lại giờ WBS theo tuần/vai trò và cộng 14 giờ PM/BA đề xuất. Mô phỏng không có dòng tuần/vai trò vượt khả dụng. PM cần kiểm khả dụng theo ngày, lịch nghỉ, chi phí thực tế và xác nhận của khách trước khi đổi baseline.

### Kiểm tải ngày và cảnh báo khi giả định thay đổi

Bản rà soát 2.5 chuyển 3 giờ DevOps của WBS 9.2 từ 09/04 sang 12/04. Dự kiến DevOps làm 8 giờ triển khai ngày 08/04, 6 giờ triển khai và 2 giờ smoke sau bàn giao phiên bản ngày 09/04, rồi 8 giờ smoke/hồi quy ngày 12/04. Lịch dùng giả định tối đa 8 giờ/ngày và cần DevOps/PM xác nhận. QA chuẩn bị trước, thực thi kiểm Production sau khi 9.1 hoàn tất. Tổng effort và ngày dự kiến MS-08 giữ theo phương án 3 ngày. Tra bảng DevOps tại **Tải phản hồi 3 ngày**, cột H–O.

Ô I6:I13 trên **Lịch phản hồi 3 ngày** cho phép thử thay đổi thời hạn phản hồi. Bảng kiểm so với snapshot và đánh dấu WBS bắt đầu trước hoặc cùng ngày mốc phải chờ. Ví dụ, tăng MS-02 lên 5 ngày làm việc làm WBS 4.1 vướng phụ thuộc và kích hoạt cảnh báo ở I15. Tính lại cả lịch và phân bổ theo ngày/tuần khi cảnh báo xuất hiện.

## Thay đổi kế hoạch

Khi chỉnh kế hoạch theo feedback nội bộ hoặc của giảng viên, ghi căn cứ và phiên bản trong **Change Log** và lịch sử PR. Bản 2.2 là dự thảo rà soát. Sau khi khách nhận Proposal, đề nghị đổi phạm vi, giá hoặc mốc được xử lý theo [Change Control](../11-governance/change-control.md). Khi CR được duyệt, lưu bản trước, thêm phiên bản, ngày, mã CR và tác động vào **Change Log**. Cập nhật các nguồn liên quan, gồm báo giá, WBS, Resources, PRD, test và các mốc trên GitHub. Tra bằng chứng gửi tại [Bản đã gửi khách](sent/README.md).
