# Master Plan

[Workbook Master Plan](master-plan.xlsx) là nguồn tra ngày, effort, nguồn lực và lịch sử phiên bản của kế hoạch **Mô phỏng**. Sheet **Hướng dẫn** ở đầu workbook chỉ sheet nào là baseline và sheet nào là phương án chưa áp dụng.

## Baseline đang áp dụng

| Nội dung | Giá trị |
| --- | --- |
| Phiên bản | **Baseline 3.2**, duyệt ngày 23/11/2026. Bản 3.0 được duyệt khi ký thỏa thuận ngày 28/09/2026; 3.1 và 3.2 là điều chỉnh nội bộ không đổi ngày, giá hay phạm vi. |
| Người duyệt | Bản 3.0: PM (Trần Vĩnh Đại) và đại diện Aurora University — Mô phỏng. Bản 3.1 và 3.2 chỉ đổi phân bổ nội bộ, PM duyệt theo [Change Control](../11-governance/change-control.md#người-duyệt). |
| Ngày khởi động | **05/10/2026**, thứ Hai sau khi ký thỏa thuận và nhận tạm ứng 30% ngày 28/09/2026. |
| Thời gian và mốc cuối | 23 tuần, MS-08 ngày **12/03/2027**, bảo hành đến 11/04/2027. |
| Sheet baseline | Hướng dẫn, Master Schedule (Gantt) chứa WBS, Milestone Matrix, Resources, RACI & Governance, SLA & Project Metrics, Risk Register, Change Log. |
| Sheet phương án | Nghiệm thu, Kịch bản, Lịch liên mốc, Tải liên mốc, Lịch phản hồi 3 ngày, Tải phản hồi 3 ngày. Các sheet này là phương án P-01 đến P-04 chờ [OQ-08](open-questions.md), chưa thay baseline. |

**Trình tự trước khởi động.** Proposal v2.1 và báo giá lập ngày 14/09/2026 và gửi đầu mối nhà trường cùng ngày. Aurora University xác nhận phương án và ký thỏa thuận ngày 28/09/2026. Việc soạn và trình bày Proposal là hoạt động trước hợp đồng, nằm ngoài 23 tuần và không tính vào giá. 23 tuần bắt đầu từ WBS 1.1. Bằng chứng gửi tại [Bản đã gửi khách](sent/README.md).

GitHub milestone MS-01 đến MS-08 và parent task dẫn tới baseline 3.2 trên nhánh `main`.

## Cách chia milestone

MS-01 giao đăng nhập xuyên suốt từ giao diện đến dữ liệu trên Staging để khách có thể thử sớm. MS-02 mở rộng sang tài khoản và phân quyền. MS-03 và MS-04 nối thành vòng đời Ticket từ phía sinh viên đến cán bộ và quản lý. MS-05 giao Dashboard và CSV sau khi có nghiệp vụ tạo dữ liệu. MS-06 kiểm toàn bộ luồng tích hợp, MS-07 xác nhận UAT và sẵn sàng phát hành, MS-08 giao hệ thống trên Production. Thao tác dùng thử và điều kiện nghiệm thu của từng mốc nằm trong **Milestone Matrix**.

**Phân kỳ phân luồng (từ baseline 3.1).** Tech Lead đề xuất tách phần lưu phòng nhận khỏi Staff Desk để MS-03 không phụ thuộc danh sách Ticket của cán bộ. Tại MS-03, #60 bàn giao API tạo Ticket có lưu phòng đích từ danh mục đã cấu hình sẵn. #93 kiểm chứng TS-021 trước xác nhận mốc và không chờ danh sách Staff Desk #67. Tại MS-04, #63 hoàn thiện hàng đợi theo quyền và nhánh dự phòng khi thiếu quy tắc trên kết quả đã có ở #60; việc phân công và chuyển cấp theo WBS 4.4/FR-STF-02/04. FAQ ở MS-03 dùng bộ FAQ giả lập nạp sẵn và màn hình tra cứu của #14 (FR-STU-06); quản trị FAQ (FR-ADM-05, #72) giao ở MS-04.

## Phụ thuộc giữa các milestone

Luồng đăng nhập trên Staging cần xong WBS 3.6 trước khi khách dùng thử ở WBS 3.9. Theo dõi môi trường [#52](https://github.com/vinhdai123/UniSupport_Project/issues/52), API [#53](https://github.com/vinhdai123/UniSupport_Project/issues/53), phiên [#54](https://github.com/vinhdai123/UniSupport_Project/issues/54) và ca kiểm [#58](https://github.com/vinhdai123/UniSupport_Project/issues/58) trước khi chốt [#101](https://github.com/vinhdai123/UniSupport_Project/issues/101). Issue ghi hạn nội bộ theo WBS và đầu ra trung gian. MS-01 dùng tài khoản giả lập tạo sẵn. QA nhận UI tối thiểu của #101 trước khi kiểm vòng đầu ở #58. #101 chốt sau hồi quy, quản trị tài khoản và đặt lại mật khẩu được giao tại MS-02.

MS-04 cung cấp dữ liệu và quyền cho phần tích hợp ở MS-05. Trong lúc chờ xác nhận, WBS 6.4 có thể chuẩn bị cấu trúc CSV, dữ liệu giả lập và ca kiểm. Bước tích hợp với dữ liệu và quyền của bản MS-04 cùng WBS 6.1 phải chờ xác nhận. MS-07 phải hoàn tất trước triển khai Production. Tại MS-08, ký bàn giao và kích hoạt bảo hành chờ khách xác nhận, còn bảo hành tính từ ngày liền sau ngày ký. Tra **Nghiệm thu** để xem việc được chuẩn bị và việc bị chặn theo từng mốc.

## Effort cho test, regression và sửa lỗi

Các việc kiểm và sửa dự kiến nằm trong WBS và [Báo giá](quotation.xlsx). WBS 3.6/3.5 dùng Q-03, 4.2 dùng Q-04, 4.6 dùng Q-05 và 5.3 dùng Q-06. WBS 6.3–6.4 dùng Q-07/Q-08, 7.2–7.4 dùng Q-08, 8.3–8.4 dùng Q-09/Q-10 và 9.2 dùng Q-10. **Resources** đối chiếu effort theo vai trò, tuần và mốc. Dùng định mức QA ở phần cuối sheet để kiểm sức chứa khi thêm một vòng hồi quy.

MS-05 cần bằng chứng Dashboard theo WBS 6.1 và CSV theo WBS 6.4. Dùng [TS-083/095](../06-acceptance/test-scenarios.md) để đối chiếu cùng kỳ/bộ lọc, số đếm và tập mã được phép xuất theo OQ-05. Phạm vi kiểm lần đầu được ghi tại [#22](https://github.com/vinhdai123/UniSupport_Project/issues/22) và đối chiếu với [#90](https://github.com/vinhdai123/UniSupport_Project/issues/90). MS-06 hồi quy CSV trên bản tích hợp và tổng hợp các ngưỡng NFR thuộc mốc đó.

Đề xuất phân bổ trong Q-04 cho tuần bắt đầu 07/12/2026. Tech Lead và QA cần đối chiếu cả phần phân luồng lẫn các đầu việc còn lại trong cùng hai dòng **Resources**.

| Vai trò và WBS | Giờ đã phân bổ | Phần phân luồng MS-03 | Giờ cho phần việc còn lại trong dòng |
| --- | ---: | ---: | ---: |
| DG04 Junior Backend, WBS 4.1, dòng 411 | 40 | 6 giờ đề xuất cho lưu phòng tiếp nhận theo danh mục khi tạo Ticket | 34 |
| DG08 QA Tester, WBS 4.2, dòng 429 | 9 | 2 giờ đề xuất cho bằng chứng TS-021 | 7 |

**Chờ xác nhận khả dụng MS-03.** Tuần 07/12, Junior Backend (DG04) dùng 40/40 giờ và QA Tester (DG08) dùng 18/40 giờ, gồm 9 giờ WBS 4.1 ở **Resources!F417** và 9 giờ WBS 4.2 ở **F429**. Nếu toàn bộ 18 giờ QA dồn vào 10–11/12, hai ngày theo trần mô phỏng 8 giờ/ngày thiếu ít nhất 2 giờ, trước khi tính thời gian chờ bản sửa.

| Nơi ghi | Điều kiện cần kiểm | Bằng chứng chờ ghi nhận |
| --- | --- | --- |
| [#60](https://github.com/vinhdai123/UniSupport_Project/issues/60) | 6 giờ phân luồng và 18 giờ cho lõi API tạo Ticket đủ để bàn giao bản Staging tối thiểu cuối 09/12 theo đề xuất. 16 giờ còn lại đủ cho phần phát triển và hỗ trợ kiểm lại. | Tech Lead ghi việc, số giờ, phiên bản và thời điểm QA có thể dùng UI, API, tệp, hai danh mục đã ánh xạ và quyền đối chiếu bản ghi. |
| [#93](https://github.com/vinhdai123/UniSupport_Project/issues/93) | Dòng F417 đề xuất 3 giờ chuẩn bị dữ liệu/kịch bản và 6 giờ kiểm sớm theo đầu ra UI, API, tệp. Dòng F429 đề xuất 2 giờ TS-021, 4 giờ tích hợp/tra cứu/quyền và 3 giờ kiểm lại/hồi quy. | QA ghi ca có thể làm trước 10/12, ca còn chờ đầu vào, giờ nhận bản tích hợp và số giờ kiểm còn lại. Khi bản sửa trượt mục tiêu 12:00 ngày 11/12, tính lại cửa sổ từ giờ nhận bản mới. |

Tech Lead và QA ghi kết luận khả thi, người xác nhận và ngày quyết định tại hai Issue. PM đánh giá lại phân bổ hoặc lịch khi một phần việc vượt định mức hoặc cửa sổ kiểm. Các ngày trên theo baseline 11/12. Nếu OQ-08 đổi lịch áp dụng, lập lại cửa sổ bàn giao và kiểm từ ngày mới. Cửa sổ phản hồi của khách được kiểm riêng từ lúc nhận đủ hồ sơ theo Proposal.

## Dự phòng cho thay đổi và rủi ro

Tra tổng giờ dự phòng ở **Resources** và WBS `CR.01`. Đây là năng lực đề xuất huy động cho thay đổi hoặc rủi ro, được theo dõi riêng với effort đã báo giá cho test, sửa lỗi và bảo hành. PM kiểm khả dụng theo đúng vai trò và tuần. Phần việc phát sinh ngoài phạm vi được định giá trong CR để hai bên xác nhận.

[CR-01](https://github.com/vinhdai123/UniSupport_Project/issues/102) thử thêm XLSX. Sheet **Kịch bản** cho thấy Junior Backend và Junior Frontend kín tải trong ba tuần cuối trước MS-05. QA cũng kín tải ở tuần chốt MS-05 và MS-06 và thiếu giờ nếu vừa vắng vừa cần kiểm lại. PM chỉ trình đưa XLSX vào mốc khi có phương án tái phân bổ và kiểm hồi quy khả thi. CR hiện chờ quyết định, baseline tiếp tục dùng CSV.

## Cách nhận feedback của client sau mỗi milestone

PM gửi phiên bản, quyền truy cập, kịch bản và hồ sơ kiểm. Ghi thời điểm khách nhận đủ hồ sơ và hạn phản hồi theo mục 8 [Proposal](proposal.docx). Mỗi phản hồi có Issue, phiên bản, người chịu trách nhiệm, bằng chứng và kết quả kiểm lại. Khi hồ sơ thay đổi sau sửa, PM thống nhất hạn của lần gửi lại. Xác nhận mốc cần bằng chứng bằng văn bản.

**Phương án P-01 (chưa áp dụng).** Sheet **Nghiệm thu** mô phỏng riêng từng mốc khi khách dùng hết hạn phản hồi 5 ngày làm việc. Các dòng MS-02 đến MS-07 cho ngày xác nhận muộn hơn baseline 5 ngày làm việc mỗi mốc; MS-08 muộn hơn 3 ngày. Đây là so sánh từng mốc độc lập, chưa cộng dồn việc chờ xác nhận và không phải lịch thay thế đã được kiểm khả thi.

Kết quả từng dòng cũng làm lộ xung đột với phụ thuộc trong Gantt. WBS 4.1 bắt đầu **30/11/2026** theo baseline, phụ thuộc **MS-02 FS**, trong khi sheet **Nghiệm thu!E7** cho ngày xác nhận muộn nhất theo kịch bản là **04/12/2026**. Vì vậy, WBS 4.1 không thể vừa bắt đầu theo baseline vừa đợi MS-02 được xác nhận theo kịch bản này. Các mốc sau cũng có thể dời qua phụ thuộc khi ngày xác nhận trước đó muộn hơn ngày bắt đầu WBS. PM cần lập lại đường găng và phân bổ sau khi xác định được ngày bắt đầu thực tế của từng công việc phụ thuộc.

Không cộng cơ học số ngày trễ từng dòng thành lịch dự án: các lần gửi, phụ thuộc, công việc chạy song song, ngày nghỉ, lần gửi lại và nguồn lực theo ngày phải được tính lại cùng nhau. Trước khi OQ-08 được quyết định, baseline **23 tuần/MS-08 ngày 12/03/2027** vẫn là lịch gốc để đối chiếu. Kịch bản 5 ngày chỉ là phép thử. Phương án ba ngày cho kết quả khác và cũng chỉ là đề xuất thương lượng. PM ghi lịch áp dụng sau khi xác nhận điều kiện phản hồi, khả dụng, tác động thương mại và phê duyệt bằng văn bản tại [OQ-08](open-questions.md).

## Phương án P-02: lịch liên mốc (chưa áp dụng)

Tra **Lịch liên mốc** để xem ngày gửi đủ hồ sơ, phản hồi, xác nhận từng mốc và các WBS đã dời. Tra **Tải liên mốc** để đối chiếu từng phân bổ với Resources và xem tải theo vai trò/tuần đến hết bảo hành. Phép thử dùng đủ hạn phản hồi ở mỗi mốc, giả định khách đồng ý khi hết hạn, chưa tính ngày nghỉ hay vòng sửa bổ sung.

Phương án giữ WBS 3.8 độc lập với xác nhận MS-02, dời toàn bộ WBS 6.4 sau xác nhận MS-04 và giữ các việc còn lại theo tuần trọn để chuyển phân bổ nguồn lực. MS-08 dành thời gian phản hồi sau khi có kết quả Production và giữ thời lượng ký bàn giao của WBS 9.3. Bảo hành tính từ ngày liền sau ký theo Proposal.

Tải thử gồm giờ triển khai và bảo hành gốc, dự phòng ở tuần gốc và giờ PM/BA bổ sung đề xuất cho các cửa sổ phản hồi. Các tuần ngoài baseline dùng trần nguồn lực mô phỏng. Trước khi duyệt, PM kiểm ngày nghỉ, khả dụng và tác động tới cam kết/giá tại [OQ-08](open-questions.md). Bảng phương án trong sheet **Change Log** ghi P-02 là phương án chưa áp dụng; bảng milestone và báo giá tiếp tục theo baseline 3.2.

## Phương án P-03: phản hồi 3 ngày (đề xuất thương lượng OQ-08)

P-03 chưa thay baseline. Đây là phương án ban quản lý chọn để thương lượng tại OQ-08: khách phản hồi trong 3 ngày làm việc sau khi nhận đủ hồ sơ. Sheet **Lịch phản hồi 3 ngày** tính lại WBS theo ngày làm việc qua toàn chuỗi và giữ hai ngày ký MS-08 sau khi hết hạn phản hồi. WBS 3.8 tiếp tục chạy độc lập với xác nhận MS-02, WBS 6.4 bắt đầu sau xác nhận MS-04.

Nếu khách đồng ý ở cuối mỗi cửa sổ, lịch chưa tính ngày nghỉ hoặc lần gửi lại, MS-08 dự kiến ký **19/04/2027**, tuần **29**. Bảo hành bắt đầu **20/04/2027** và kết thúc **19/05/2027** theo giả định ngày ký này. Sheet **Tải phản hồi 3 ngày** phân bổ lại giờ WBS theo tuần/vai trò và cộng 14 giờ PM/BA đề xuất. Mô phỏng không có dòng tuần/vai trò vượt khả dụng. PM cần kiểm khả dụng theo ngày, lịch nghỉ, chi phí thực tế và xác nhận của khách trước khi đổi baseline.

### Kiểm tải ngày và cảnh báo khi giả định thay đổi

Phương án P-04 (bổ sung cho P-03) chuyển 3 giờ DevOps của WBS 9.2 từ 09/04 sang 12/04. Dự kiến DevOps làm 8 giờ triển khai ngày 08/04, 6 giờ triển khai và 2 giờ smoke sau bàn giao phiên bản ngày 09/04, rồi 8 giờ smoke/hồi quy ngày 12/04. Lịch dùng giả định tối đa 8 giờ/ngày và cần DevOps/PM xác nhận. QA chuẩn bị trước, thực thi kiểm Production sau khi 9.1 hoàn tất. Tổng effort và ngày dự kiến MS-08 giữ theo phương án 3 ngày. Tra bảng DevOps tại **Tải phản hồi 3 ngày**, cột H–O.

Ô I6:I13 trên **Lịch phản hồi 3 ngày** cho phép thử thay đổi thời hạn phản hồi. Bảng kiểm so với snapshot và đánh dấu WBS bắt đầu trước hoặc cùng ngày mốc phải chờ. Ví dụ, tăng MS-02 lên 5 ngày làm việc làm WBS 4.1 vướng phụ thuộc và kích hoạt cảnh báo ở I15. Tính lại cả lịch và phân bổ theo ngày/tuần khi cảnh báo xuất hiện.

### Xác nhận lịch và tác động thương mại OQ-08

| Nội dung cần quyết định | Căn cứ để xác nhận |
| --- | --- |
| **Lịch áp dụng và phản hồi** | Baseline 23 tuần, MS-08 ngày **12/03/2027**. Phương án thương lượng dự kiến MS-08 ngày **19/04/2027**, chênh **38 ngày lịch** theo ô **Lịch phản hồi 3 ngày!F13**. PM ghi lịch làm việc, ngày nghỉ, thời điểm bắt đầu tính ba ngày và cách xử lý khi gửi lại hồ sơ. Lưu văn bản xác nhận của Aurora University. |
| **Khả dụng thực hiện** | DevOps và PM xác nhận các cửa sổ 08, 09 và 12/04. Mỗi ngày dùng 8/8 giờ theo **Tải phản hồi 3 ngày!H6:O8**. Kiểm thứ tự 9.1 → 9.2, khả dụng QA sau bàn giao và mốc gửi đủ hồ sơ nếu một cửa sổ bị hụt. |
| **Tác động thương mại** | PM tính chi phí 14 giờ PM/BA tăng thêm theo định mức nội bộ được phê duyệt, cộng chi phí môi trường/dịch vụ và chi phí giữ người phát sinh theo lịch mới. Đối chiếu cả thời hạn bảo hành được dời và giá bán 700 triệu để ghi quyết định giữ giá hay trình điều chỉnh. Lưu căn cứ chi phí trong hồ sơ nội bộ. |

Khi có đủ quyết định thương mại và xác nhận lịch, PM đồng bộ [Proposal](proposal.docx), [báo giá](quotation.xlsx), Master Plan, [roadmap](../10-product-management/roadmap.md) và milestone GitHub. Nếu lịch hoặc giá đã cam kết cần đổi, áp dụng [Change Control](../11-governance/change-control.md).

## Thay đổi kế hoạch

**Change Log** có hai bảng: phiên bản baseline (đã duyệt, có người duyệt) và phương án chưa áp dụng (P-xx). Mỗi dòng ghi lý do thuộc dự án như rủi ro, phản hồi của khách, CR hoặc điều chỉnh nội bộ. Điều chỉnh phân bổ nội bộ không đổi mốc, giá hay phạm vi do PM duyệt. Sau khi khách ký thỏa thuận ngày 28/09/2026, đề nghị đổi phạm vi, giá hoặc mốc được xử lý theo [Change Control](../11-governance/change-control.md). Khi CR được duyệt, lưu bản trước, thêm phiên bản, ngày, mã CR và tác động vào **Change Log**. Cập nhật các nguồn liên quan, gồm báo giá, WBS, Resources, PRD, test và các mốc trên GitHub. Tra bằng chứng gửi tại [Bản đã gửi khách](sent/README.md).
