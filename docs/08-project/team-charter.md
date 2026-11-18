# Team Charter UniSupport

Phiên bản 2.4 — dự thảo ngày 18/11/2026

Dự án mô phỏng môn Software Project Management, phục vụ tình huống Aurora University với khoảng 3.000 sinh viên. Charter quy định trách nhiệm, phối hợp, quyết định, xử lý bất đồng và quản lý thay đổi trong quá trình xây dựng tài liệu, kế hoạch và quy trình dự án UniSupport.

**Trạng thái.** Bản 2.4 đang chờ nhóm thông qua. Danh sách thành viên và trưởng nhóm được đối chiếu với feedback R1. Mảng phụ trách theo README tại commit `dfe998d`. Lịch họp hiện được ghi ở tài liệu Reporting. Các quy tắc phối hợp, dự phòng và thẩm quyền mới trong bản này là đề xuất. Xem mục 11 để kiểm tra bằng chứng xác nhận và ngày hiệu lực.

## 1. Mục tiêu và nguyên tắc phối hợp

Nhóm chịu trách nhiệm xây dựng bộ tài liệu nhất quán từ phạm vi và giá, yêu cầu sản phẩm, kế hoạch thực hiện đến công việc, kịch bản kiểm thử và quản trị. Mỗi thành viên phải giải thích được quyết định và bằng chứng thuộc phần mình phụ trách khi bảo vệ.

- Mỗi đầu việc có một người chịu trách nhiệm chính, hạn và đầu ra có thể kiểm tra.
- Nhận xét dựa vào yêu cầu, dữ liệu và tiêu chí đã thống nhất. Người đưa ra ý kiến chỉ rõ vị trí và tác động.
- Thành viên báo sớm trở ngại, rủi ro và thay đổi khả dụng để nhóm điều phối.
- Dữ liệu khách hàng, phản hồi, báo cáo, CR và đội thực thi trong tình huống học tập được ghi rõ Mô phỏng khi sử dụng.
- Quyết định phải lần được tới người quyết định, ngày, căn cứ và tài liệu bị ảnh hưởng.
- Những hoạt động phát triển, kiểm thử thực thi và triển khai được mô tả ở mức kế hoạch của tình huống mô phỏng. Trạng thái hoàn thành của bài làm gắn với đầu ra tài liệu thực tế và bằng chứng review.

## 2. Thành viên và trách nhiệm

### 2.1. Ban quản lý dự án

Danh sách theo feedback R1 gồm Trần Vĩnh Đại, Nguyễn Thành An, Phùng Ngô Huy Bảo và Huỳnh Hữu Như Mẫn. Trần Vĩnh Đại được ghi là trưởng nhóm. Mảng phụ trách trong bảng theo README cập nhật tại `dfe998d`. Tra người dự phòng theo từng đầu ra tại mục 2.3.

| Thành viên | Mảng phụ trách đề xuất | Trách nhiệm chính |
| --- | --- | --- |
| Trần Vĩnh Đại | Proposal, quản lý chất lượng và quản lý sản phẩm | Điều phối với vai trò trưởng nhóm, duy trì Proposal, Quality Plan, test/RTM và tài liệu quản lý sản phẩm |
| Nguyễn Thành An | Team Charter và Git | Duy trì Charter, tổ chức repo và quy trình Issue, branch, PR, review và merge theo quyền được nhóm xác nhận |
| Phùng Ngô Huy Bảo | Master Plan, quản trị và giám sát, báo giá | Duy trì kế hoạch, nguồn lực, rủi ro, Change Log, báo giá và số liệu quản trị, đối chiếu phạm vi–effort–lịch–giá |
| Huỳnh Hữu Như Mẫn | PRD và review | Duy trì PRD/NFR/domain, kiểm bao phủ yêu cầu và tham gia review độc lập các tài liệu thuộc phạm vi được phân công |

Người chịu trách nhiệm chính tổng hợp ý kiến và duy trì bản gốc. Reviewer kiểm nội dung độc lập. Người dự phòng tiếp nhận công việc theo mục 6 khi có quyết định bàn giao.

### 2.2. Đội thực thi Mô phỏng

Cơ cấu chín người dưới đây phục vụ lập kế hoạch thực hiện dự án phần mềm. Phân công ban quản lý ở mục 2.1 xác định trách nhiệm đối với bài làm và tài liệu.

| Vai trò Mô phỏng | Số người | Trách nhiệm trong kế hoạch dự án | Báo cáo cho |
| --- | ---: | --- | --- |
| PM kiêm BA | 1 | Phạm vi, yêu cầu, stakeholder, lịch, CR, rủi ro và điều phối UAT | Đại diện Aurora University Mô phỏng |
| Tech Lead / Solution Architect | 1 | Kiến trúc, phương án kỹ thuật, tích hợp và review chuyên môn | PM |
| Senior Backend Developer | 1 | API, dữ liệu và logic nghiệp vụ, hướng dẫn Backend | Tech Lead |
| Junior Backend Developer | 1 | Phát triển và sửa lỗi Backend theo phân công | Tech Lead |
| Senior Frontend Developer | 1 | Giao diện, tích hợp API và hướng dẫn Frontend | Tech Lead |
| Junior Frontend Developer | 1 | Phát triển và sửa lỗi Frontend theo phân công | Tech Lead |
| UI/UX Designer | 1 | Wireframe, prototype, giao diện và phản hồi thiết kế | PM, phối hợp Tech Lead |
| QA / Tester | 1 | Kế hoạch test, testcase, kiểm thử và hồi quy, hỗ trợ UAT | PM, phối hợp Tech Lead |
| DevOps Engineer | 1 | Môi trường, CI/CD, triển khai, giám sát và khôi phục | Tech Lead |

Giờ huy động, effort và dự phòng theo vai trò được quản lý tại sheet Resources của Master Plan. Khi thay đổi nhân sự hoặc khả dụng, người phụ trách kế hoạch kiểm lại capacity, lịch và rủi ro trước khi đề xuất điều chỉnh.

### 2.3. Trách nhiệm đối với từng tài liệu

Người chịu trách nhiệm chính theo mảng trong README. Reviewer và người dự phòng dưới đây là đề xuất cần nhóm xác nhận.

| Tài liệu | Người chịu trách nhiệm chính | Reviewer chính | Người dự phòng |
| --- | --- | --- | --- |
| Proposal | Trần Vĩnh Đại | Huỳnh Hữu Như Mẫn | Huỳnh Hữu Như Mẫn |
| Báo giá và kế hoạch chi phí nội bộ | Phùng Ngô Huy Bảo | Trần Vĩnh Đại | Trần Vĩnh Đại |
| Master Plan, Resources và Change Log | Phùng Ngô Huy Bảo | Nguyễn Thành An | Trần Vĩnh Đại |
| Risk Register | Phùng Ngô Huy Bảo | Huỳnh Hữu Như Mẫn | Trần Vĩnh Đại |
| PRD, NFR và tài liệu domain | Huỳnh Hữu Như Mẫn | Phùng Ngô Huy Bảo | Nguyễn Thành An |
| Quality Plan, test scenarios và traceability matrix | Trần Vĩnh Đại | Huỳnh Hữu Như Mẫn | Nguyễn Thành An |
| Quản lý sản phẩm | Trần Vĩnh Đại | Huỳnh Hữu Như Mẫn | Phùng Ngô Huy Bảo |
| Quản trị và giám sát | Phùng Ngô Huy Bảo | Huỳnh Hữu Như Mẫn | Trần Vĩnh Đại |
| Team Charter, Git và mục lục tài liệu | Nguyễn Thành An | Huỳnh Hữu Như Mẫn | Trần Vĩnh Đại |

Bảng này là nguồn duy nhất để xác định người dự phòng của từng tài liệu. Khi người dự phòng tham gia viết hoặc chỉnh sửa, chọn reviewer khác độc lập theo mục 9.3. File Word/Excel được chỉnh bởi một người tại một thời điểm, việc tiếp nhận chỉnh sửa được ghi vào Issue để tránh ghi đè phiên bản.

## 3. Công cụ và nơi lưu thông tin

| Công cụ | Nội dung quản lý | Cách lưu và cập nhật |
| --- | --- | --- |
| GitHub repository | Tài liệu nộp bài, PRD Markdown, Proposal, báo giá, Master Plan và các kế hoạch | Bản dùng review được quản lý qua PR, có tên file cố định và lịch sử Git |
| GitHub Issues | Task, bug, feedback, CR và quyết định cần theo dõi | Ghi owner, hạn, liên kết tài liệu và bằng chứng |
| GitHub Projects | Trạng thái, owner, lịch và phụ thuộc công việc | Cập nhật từ các Issue tương ứng và đối chiếu Master Plan |
| Google Drive | Hồ sơ gửi khách hàng, biên bản, bản xuất báo cáo, file tài chính nội bộ có quyền hạn phù hợp | Người phụ trách ghi phiên bản, ngày và liên kết tới bản nguồn khi chia sẻ |
| Google Meet | Họp điều phối, review và xử lý bất đồng | PM quản lý lịch, đường dẫn và biên bản |
| GitHub Issue và đề cập người liên quan | Trao đổi công việc có lưu vết | Ghi yêu cầu, người phản hồi và thời điểm cần quyết định |
| Email | Trao đổi và xác nhận chính thức với khách hàng trong tình huống dự án | PM tổng hợp và lưu xác nhận theo quyền truy cập |
| Figma | Wireframe, prototype và thiết kế | Ghi phiên bản, phạm vi review và trạng thái xác nhận |
| Postman / Swagger trong kế hoạch kỹ thuật | API contract, mock và mô tả request/response | Gắn phiên bản yêu cầu và công việc liên quan |
Việc chọn GitHub Issue làm kênh trao đổi có lưu vết mặc định là đề xuất của bản Charter này. Khi nhóm bổ sung kênh chat, ghi tên kênh và cách liên hệ khẩn trong quyết định thông qua Charter. Sự cố khẩn được báo bằng cuộc gọi trực tiếp tới đầu mối phụ trách, sau đó lưu nội dung vào Issue.

Bản gốc của Charter nằm tại `docs/08-project/team-charter.md` và được dẫn từ [README gốc](../../README.md) và [mục lục tài liệu](../README.md).

| Nội dung gốc | Vị trí để đối chiếu |
| --- | --- |
| Phạm vi, assumptions và nghiệm thu | [Proposal](proposal.docx) |
| Giá và khối lượng bán | [Báo giá](quotation.xlsx) |
| Ngày, WBS, MS-xx, nguồn lực, rủi ro và lịch sử kế hoạch | [Master Plan](master-plan.xlsx) |
| Lịch họp, báo cáo, cảnh báo và CR | [Reporting](../11-governance/reporting.md), [Monitoring](../11-governance/monitoring.md) và [Change Control](../11-governance/change-control.md) |
| FR, AC và NFR đang được review | [PRD theo module](../03-modules/README.md) và [NFR](../05-non-functional-requirements/README.md). Issue review ghi commit được đối chiếu |
| Quy trình QA/QC, DoD và điều kiện phát hành | [Quality Plan](../09-quality/quality-plan.md) |

Kế hoạch chi phí và lợi nhuận nội bộ được lưu trong vùng hạn chế của nhóm, quyền truy cập được PM rà soát trước khi chia sẻ tài liệu.

## 4. Ra quyết định và kiểm soát thay đổi

### 4.1. Thẩm quyền theo loại quyết định

| Loại quyết định | Người chuẩn bị | Người quyết định hoặc xác nhận |
| --- | --- | --- |
| Phân công, đổi thứ tự, đổi hạn nội bộ và bàn giao việc soạn hoặc review tài liệu của nhóm | Người phụ trách mảng | Trưởng nhóm khi có mặt, điều phối viên tạm thời theo mục 6 khi trưởng nhóm vắng. Áp dụng trong phạm vi công việc nội bộ, giữ các cam kết dự án |
| Cách diễn đạt và cấu trúc PRD trong phạm vi đã thống nhất | Người phụ trách yêu cầu, reviewer chất lượng | Người phụ trách yêu cầu chốt sau review, trưởng nhóm xử lý bất đồng liên mảng |
| Lựa chọn kỹ thuật trong dự án Mô phỏng | Tech Lead tham vấn các vai trò bị ảnh hưởng | Tech Lead trong giới hạn phạm vi, lịch và ngân sách đã được xác nhận |
| Kế hoạch chất lượng và tiêu chí kiểm | Người phụ trách chất lượng hoặc QA Mô phỏng | Ban quản lý xác nhận tài liệu nội bộ, khách hàng xác nhận điều kiện nghiệm thu liên quan theo Proposal |
| Điều chỉnh effort, phân bổ nhân sự hoặc thứ tự task trong kế hoạch thực thi Mô phỏng | Người phụ trách kế hoạch | PM quyết định điều chỉnh nội bộ trong phạm vi thẩm quyền theo [Change Control](../11-governance/change-control.md#người-duyệt). Thay đổi cam kết được trình theo mục 4.3 |
| Thay đổi phạm vi, giá, hạn hoặc điều kiện nghiệm thu đã cam kết | PM tổng hợp đánh giá tác động | Đại diện có thẩm quyền của Project Team và Aurora University xác nhận bằng văn bản |
| Thông qua hoặc thay đổi Charter | Trưởng nhóm tổng hợp ý kiến | Đề xuất cần ít nhất 3 trong 4 thành viên đồng ý, ghi rõ ý kiến và ngày áp dụng |

Quy tắc 3 trong 4 là đề xuất cần nhóm xác nhận. Thành viên vắng được gửi ý kiến bằng văn bản. Khi chưa đủ xác nhận, người điều phối ghi phần chưa thống nhất và tổ chức trao đổi tiếp. Thẩm quyền kết luận khi có xung đột lợi ích và cách xử lý khi quá hạn được quy định tại mục 7.1.

### 4.2. Ghi nhận quyết định

Mỗi quyết định được lưu tại Issue hoặc biên bản được liên kết từ Issue, gồm mã theo dõi, nội dung, căn cứ, các phương án, người tham gia, người quyết định, ngày, tài liệu chịu ảnh hưởng và hành động tiếp theo. Các dữ kiện đang chờ xác nhận được ghi `TBD / Pending Confirmation`, cùng người cần xác nhận và hạn dự kiến.

Với các điểm PRD đã được review như trạng thái mở lại Ticket, giới hạn tệp, thời hạn mở lại và quyền dữ liệu, người phụ trách yêu cầu dẫn tới rule gốc và quyết định xác nhận. Người phụ trách chất lượng kiểm lại AC và kịch bản test sau khi quyết định được cập nhật.

### 4.3. Change Request

[Change Control](../11-governance/change-control.md) là nguồn gốc cho việc mở CR, đánh giá tác động, phê duyệt và cập nhật tài liệu. Khi đề xuất làm thay đổi cam kết với khách hàng, PM trình quyết định theo thẩm quyền tại mục 4.1 và lưu bằng chứng phê duyệt trong hồ sơ CR.

## 5. Lịch phối hợp và báo cáo

[Reporting, mục 2](../11-governance/reporting.md#2-bảng-quy-trình-báo-cáo) là nguồn gốc của lịch họp ngày, họp tuần và yêu cầu báo sự cố nghiêm trọng ngay khi phát hiện. [Master Plan](master-plan.xlsx) là nguồn lịch bàn giao. Nhóm xác nhận khả năng tham gia và khung giờ phối hợp khi thông qua Charter.

| Hoạt động | Lịch hoặc thời điểm | Chủ trì và đầu ra |
| --- | --- | --- |
| Cập nhật trước họp ngày | Trước 08:40 mỗi ngày làm việc · đề xuất tại Charter | Người thực hiện cập nhật Issue về kết quả, giờ công, ETA và blocker |
| Họp điều phối ngày | 08:45–09:00 các ngày làm việc trên Google Meet | PM điều phối, ghi người xử lý và thời hạn cho vấn đề phát sinh |
| Họp tuần | Thứ Sáu 15:00–15:45 trên Google Meet | PM tổng hợp tiến độ, nguồn lực, chất lượng, rủi ro và kế hoạch tuần sau |
| Review tài liệu | Theo hạn trong Issue và trước lần bàn giao liên quan | Chủ tài liệu gửi phiên bản, reviewer ghi nhận xét và kết quả xử lý |
| Họp xử lý bất đồng hoặc blocker | Khi phát sinh ảnh hưởng công việc phụ thuộc | Đầu mối theo mục 4 và 7 lưu quyết định, owner và hạn |
| Review trước bàn giao | Theo mốc MS-xx của Master Plan hiện hành | PM tổng hợp hồ sơ và điều kiện để trình xác nhận |

Giờ trong lịch dùng múi giờ Việt Nam, UTC+7. Khả dụng thực tế và giờ vắng được ghi ở Resources. Trưởng nhóm cùng từng thành viên xác nhận khung giờ phối hợp chung khi duyệt Charter.

Charter đề xuất phản hồi vấn đề thông thường trong ngày làm việc. Với sự cố nghiêm trọng trong khung giờ phối hợp đã thống nhất, Charter đề xuất xác nhận tiếp nhận và giao hướng xử lý ban đầu trong 30 phút kể từ lúc đầu mối nhận báo cáo. Ngoài khung giờ đó, đầu mối xác nhận khi tiếp nhận cuộc gọi và ghi thời điểm cập nhật tiếp theo. Việc báo ngay khi phát hiện tuân theo Reporting.

Người vắng họp báo đầu mối, gửi cập nhật trước cuộc họp khi có thể và đọc biên bản sau đó. Các quyết định ảnh hưởng công việc của người vắng phải được gửi trực tiếp để người đó xác nhận đã nhận thông tin.

## 6. Vắng dài ngày và bàn giao công việc

Ngưỡng kích hoạt đề xuất là vắng dự kiến từ một ngày làm việc trở lên, hoặc vắng khi cần quyết định, review hay bàn giao. Khi công việc có nguy cơ gián đoạn, người phát hiện báo ngay cho trưởng nhóm. Nếu trưởng nhóm vắng, báo các thành viên còn lại trên Issue.

**Đầu mối điều phối nội bộ.** Khi trưởng nhóm có mặt, trưởng nhóm điều phối. Khi trưởng nhóm vắng, các thành viên có mặt chọn một điều phối viên tạm thời và ghi tên, phạm vi, thời hạn ủy quyền trong Issue. Nếu chưa thống nhất được hoặc chỉ còn một người có mặt, người đầu tiên có thể nhận việc theo thứ tự **An → Bảo → Mẫn → Đại** làm điều phối viên tạm thời. Nếu chưa có ai có thể nhận điều phối, người phát hiện ghi `Blocked` trên Issue và hẹn xem xét lại khi có thành viên khả dụng.

Trong phạm vi ghi trên Issue, điều phối viên tạm thời thực hiện quyền nội bộ tại mục 4.1, gồm đổi thứ tự hoặc hạn nội bộ và chỉ định reviewer thay thế theo mục 9.3. Đầu mối ghi quyết định, lý do, owner, reviewer và ETA liên quan trên Issue. Điều chỉnh kế hoạch thực thi Mô phỏng được chuyển PM theo mục 4.1.

1. Đầu mối điều phối xác nhận đúng một người tiếp nhận cho mỗi đầu ra theo mục 2.3. Nếu người dự phòng cũng vắng, quá tải hoặc thiếu quyền, đầu mối chỉ định người có khả năng hoàn thành và có quyền cần thiết. Nếu chưa có người phù hợp, ghi `Blocked`, lý do và lần kiểm tra tiếp theo.
2. Bàn giao phiên bản file hoặc commit, phần đã làm, việc còn lại, hạn, phụ thuộc, quyết định đang chờ và quyền cần dùng. Người tiếp nhận xác nhận khả năng thực hiện và quyền truy cập trên Issue.
3. Đầu mối điều phối cập nhật owner, reviewer độc lập, ETA và lý do thay đổi trên Issue. Người được phân công theo dõi kế hoạch kiểm tác động đến capacity, lịch, rủi ro và mốc. Mọi thay đổi cam kết được trình theo mục 4.3.
4. Khi người phụ trách quay lại, hai người đối chiếu thay đổi. Đầu mối điều phối xác nhận chuyển lại trách nhiệm và cập nhật Issue.

Nếu người giữ báo giá vắng, người được xác nhận tiếp nhận ở bước 1 dùng file nguồn đã xác định, đối chiếu tổng và công thức, cập nhật theo CR được duyệt và yêu cầu một thành viên độc lập kiểm lại trước khi phát hành. Quyền truy cập được cấp theo tài khoản riêng và phạm vi cần thiết.

## 7. Bất đồng, blocker và escalation

### 7.1. Bất đồng giữa thành viên

Hai bên ghi rõ nội dung đang tranh luận, nguồn yêu cầu, bằng chứng và phương án cùng tác động trong Issue. Đầu mối phụ trách tổ chức trao đổi để thống nhất cách xử lý. Mốc xử lý nội bộ đề xuất là trong một ngày làm việc từ khi đủ thông tin, hoặc sớm hơn theo hạn của công việc phụ thuộc.

Nếu trao đổi chưa có đồng thuận, áp dụng cơ chế đề xuất sau.

1. Người có thẩm quyền theo mục 4.1 kết luận trong phạm vi của mình nếu có thể xử lý độc lập. Một người được xem là có liên quan trực tiếp khi là bên tranh chấp hoặc khi kết luận sẽ quyết định trách nhiệm cá nhân của chính họ trong vụ việc.
2. Với bất đồng nội bộ về tài liệu, ghi các đầu ra bị ảnh hưởng vào một Issue. Khi vụ việc liên quan nhiều đầu ra có người phụ trách khác nhau, trưởng nhóm là người có thẩm quyền ở bước 1. Nếu người có thẩm quyền vắng hoặc liên quan trực tiếp, lập danh sách người dự phòng của tất cả đầu ra theo mục 2.3, gộp tên trùng và loại người vắng hoặc liên quan trực tiếp. Chọn đúng một người từ danh sách theo thứ tự đề xuất **An → Bảo → Mẫn → Đại**. Nếu danh sách này rỗng, áp dụng cùng thứ tự cho những thành viên còn lại đủ điều kiện. Người được chọn tham vấn nhóm, kết luận trong phạm vi điều phối nội bộ và ghi căn cứ cùng ý kiến còn khác biệt vào Issue.
3. Khi hết hạn một ngày làm việc mà chưa có kết luận, hoặc không có người đủ điều kiện, đánh dấu các công việc phụ thuộc là `Blocked`, giữ bản đã được xác nhận gần nhất và tiếp tục các việc độc lập. Người ghi nhận Issue cập nhật tác động và hẹn lần xem xét tiếp theo vào ngày làm việc kế tiếp. Nếu tất cả người đủ điều kiện đều vắng, áp dụng lại thứ tự chọn khi có người trở lại. Nếu mọi thành viên đều có liên quan trực tiếp, nhóm có thể thống nhất phương án bằng văn bản hoặc cùng chỉ định người trung lập để kết luận trong phạm vi điều phối nội bộ. Công việc phụ thuộc tiếp tục khi có quyết định được ghi vào Issue.
4. Phạm vi kết luận nội bộ giới hạn ở cam kết hiện hành. Thay đổi Charter theo mục 11. Thay đổi cam kết khách hàng được PM trình theo mục 4.3 và chờ phê duyệt trước khi áp dụng.

### 7.2. Bất đồng kỹ thuật và chất lượng

Tech Lead tổng hợp các phương án kỹ thuật, ảnh hưởng tới effort, khả năng tích hợp, bảo mật, lịch và rủi ro trước khi chốt phần thuộc thẩm quyền. QA hoặc reviewer chất lượng chỉ rõ tiêu chí, dữ liệu và bằng chứng khi phản đối việc hoàn thành hoặc bàn giao.

Khi Tech Lead muốn bàn giao còn QA ghi nhận tiêu chí chưa đáp ứng, PM tổ chức đối chiếu với PRD, AC, DoD và điều kiện phát hành đã được xác nhận. Kết quả được ghi thành việc sửa, kiểm lại, hoặc trình bên có thẩm quyền xem xét thay đổi điều kiện theo CR. Trạng thái và hồ sơ bàn giao phải phản ánh đúng các tiêu chí được kiểm và quyết định đã ghi nhận.

### 7.3. Blocker và sự cố

| Loại vấn đề | Đầu mối xử lý | Khi cần chuyển cấp |
| --- | --- | --- |
| Kỹ thuật, tích hợp hoặc môi trường | Tech Lead trong kế hoạch Mô phỏng, thành viên phụ trách mảng trong bài làm | Ảnh hưởng lịch, nguồn lực hoặc phạm vi được chuyển PM |
| Thiếu đầu vào nghiệp vụ hoặc rule chưa xác nhận | Người phụ trách PRD và PM/BA | Cần quyết định khách hàng hoặc thay đổi cam kết |
| Sai lệch giá, effort hoặc nguồn lực | Người phụ trách kế hoạch và trưởng nhóm | Dự báo vượt giới hạn đã được xác nhận |
| Chất lượng hoặc tiêu chí nghiệm thu | Người phụ trách chất lượng và trưởng nhóm | Có bất đồng về tiêu chí hoặc cần thay đổi điều kiện bàn giao |
| Sự cố dữ liệu, bảo mật hoặc dịch vụ trong tình huống dự án | DevOps/Tech Lead và PM | PM thông báo khách hàng khi cam kết hoặc dữ liệu liên quan bị ảnh hưởng |

Mỗi blocker có owner, thời điểm phát hiện, ảnh hưởng, hành động và lần cập nhật tiếp theo. Người nhận công việc theo dõi đến khi có bằng chứng xử lý và người có trách nhiệm xác nhận kết quả.

## 8. Quản lý task và kiểm soát phiên bản

Task được tạo từ phạm vi và WBS. Parent task ghi mã FR liên quan, mã mốc MS-xx, owner, hạn, phụ thuộc và điều kiện hoàn thành. Công việc tài liệu có thể dẫn trực tiếp tới mục và file chịu ảnh hưởng khi không gắn với một FR riêng.

Trạng thái công việc dùng `To Do → In Progress → Review/Test → Done`, có `Blocked` khi cần ghi trở ngại. Người thực hiện cập nhật kết quả và đường dẫn đầu ra. Reviewer kiểm theo tiêu chí của Issue và quy định chất lượng đang áp dụng trước khi xác nhận hoàn thành.

Khi trễ hạn, owner ghi nguyên nhân, ảnh hưởng và ETA đề xuất. Với việc làm tài liệu, đầu mối điều phối theo mục 6 kiểm các việc phụ thuộc cùng người phụ trách kế hoạch, quyết định thứ tự hoặc hạn nội bộ và cập nhật Issue. Với kế hoạch thực thi Mô phỏng, người phụ trách kế hoạch đánh giá tác động và chuyển PM quyết định theo mục 4.1. Nếu ảnh hưởng cam kết, PM trình CR theo mục 4.3. Thay đổi kế hoạch được lưu theo quy trình phiên bản trong Master Plan.

## 9. Branch, PR, review và merge

Các quy tắc chi tiết dưới đây là phương án đề xuất cho nhóm thông qua và cấu hình quyền tương ứng.

### 9.1. Branch và commit

- Thay đổi tài liệu dùng `docs/<issue>-<noi-dung>`, tạo từ `main` và mở PR về `main`. Nhánh `docs/issue-98-refactor-prd` là một ví dụ đang dùng trong repo.
- Khi triển khai phần mềm theo kế hoạch, `feature/<issue>-<noi-dung>` và `bugfix/<issue>-<noi-dung>` được tạo từ `develop`, mở PR về `develop`. Người quản lý repo xác nhận nhánh và quyền trước khi áp dụng luồng này.
- Phát hành thông thường dùng PR từ `develop` vào `main` theo mục 9.4.
- `hotfix/<issue>-<noi-dung>` phục vụ sửa sự cố khẩn của bản phát hành, tạo từ `main`, PR về `main` rồi đưa thay đổi tương ứng vào `develop` theo điều phối Tech Lead.
- Commit mô tả đúng thay đổi, tập trung vào một nội dung. Với tài liệu có thể dùng `docs: clarify ticket reopen criteria`.
- Mọi thay đổi vào `main` được thực hiện qua PR và có lịch sử review.

### 9.2. Nội dung PR
PR ghi vấn đề và Issue liên quan, quyết định được đề xuất, file/mục thay đổi, tác động liên tài liệu, cách kiểm và các điểm chờ xác nhận. Với feedback R1, ghi rõ mã feedback và đối chiếu dòng Hoàn thành khi.

Word/Excel phải có mô tả thay đổi bằng chữ trong PR. Báo giá hoặc Master Plan thay đổi phải kèm kiểm tổng, công thức, ngày, capacity và các liên kết liên quan. Tác giả lưu bản trước theo quy trình phiên bản trước khi chỉnh file.

### 9.3. Review và phê duyệt

PR tài liệu cần ít nhất một người không tham gia soạn hoặc chỉnh sửa nội dung của PR approve. Dùng reviewer chính tại mục 2.3. Nếu reviewer vắng, không thể review trước hạn hoặc đã tham gia sửa, tác giả báo trên Issue. Trưởng nhóm, hoặc điều phối viên tạm thời theo mục 6 khi trưởng nhóm vắng, chỉ định reviewer độc lập đủ khả năng và ghi tên, hạn review trên Issue cùng liên kết PR. Tác giả tiếp tục phụ trách tài liệu. Nếu chưa có reviewer độc lập, đầu mối ghi `Blocked` và cập nhật ETA. Điều phối viên có thể nhận review nếu đáp ứng yêu cầu độc lập. PR code áp dụng yêu cầu phê duyệt kỹ thuật tại mục 9.4.

Reviewer kiểm nội dung theo chuẩn môn và yêu cầu của Issue, mã/liên kết còn dùng được, sự nhất quán với phạm vi và tài liệu phụ thuộc, nguồn và trạng thái xác nhận của thông số. Với PRD, kiểm đủ nội dung mẫu FR, quan hệ rule/error–AC, NFR và kịch bản test chịu ảnh hưởng. Với tài liệu kế hoạch, kiểm ngày, effort và cơ sở huy động.

Các nhận xét cần sửa phải được xử lý hoặc có kết luận được ghi nhận. Thay đổi nội dung sau approve phải được reviewer kiểm lại phần bị ảnh hưởng trước khi merge. Với mã nguồn trong kế hoạch thực thi, kiểm thử và review kỹ thuật theo [Quality Plan](../09-quality/quality-plan.md).

### 9.4. Thẩm quyền merge

| Loại PR | Nhánh đích | Phê duyệt bắt buộc | Người merge đề xuất |
| --- | --- | --- | --- |
| Tài liệu | `main` | Ít nhất một reviewer độc lập theo mục 9.3 | Trần Vĩnh Đại, Huỳnh Hữu Như Mẫn thay khi Đại vắng hoặc được chuyển quyền |
| Feature hoặc bugfix trong kế hoạch Mô phỏng | `develop` | Technical Lead review và approve PR của Developer theo [Quality Plan, mục Tiêu chuẩn Code Review](../09-quality/quality-plan.md) | Technical Lead hoặc người thực thi được Lead ủy quyền trên PR |
| Phát hành thông thường trong kế hoạch Mô phỏng | `main`, nguồn `develop` | Technical Lead review và approve PR phát hành sau khi kiểm hồ sơ của bản ứng viên | Technical Lead hoặc người thực thi được Lead ủy quyền trên PR |
| Hotfix trong kế hoạch Mô phỏng | `main`, sau đó PR đồng bộ về `develop` | Technical Lead review và approve cả PR hotfix và PR đồng bộ | Technical Lead hoặc người thực thi được Lead ủy quyền trên từng PR |

Với đợt phát hành thông thường, sau khi feature và bugfix đã vào `develop`, Technical Lead mở hoặc phân công mở PR `develop` → `main`. PR ghi commit ứng viên, các Issue hoặc PR đã tích hợp và bằng chứng Staging tương ứng theo [Quality Plan](../09-quality/quality-plan.md#điều-kiện-release-release-criteria). Nếu commit ứng viên thay đổi, cập nhật bằng chứng và duyệt lại trước khi merge. Sau khi merge, DevOps ghi phiên bản triển khai từ `main`, QA ghi kết quả smoke và hồi quy trên Production theo Quality Plan trước khi xác nhận đủ điều kiện đưa vào sử dụng chính thức. Các bước này thuộc kế hoạch Mô phỏng.

Nếu Technical Lead là tác giả PR code, PM chỉ định người có năng lực tương đương làm Technical Lead thay thế cho PR đó để review độc lập. Nếu cả hai đầu mối merge tài liệu vắng, nhóm ghi quyết định chỉ định người thay thế. Với mọi PR, người merge cần có quyền tương ứng được quản lý repo cấp trước khi thực hiện.

Trước merge, người thực hiện kiểm nhánh đích, phiên bản cuối, approve độc lập, nhận xét còn mở, conflict, liên kết và các kiểm tra áp dụng. Khi có conflict ở file Word/Excel, chủ tài liệu và reviewer đối chiếu hai bản để tạo một bản hợp nhất được kiểm lại.

Nếu phát hiện sai sau merge, tạo Issue ghi ảnh hưởng và dùng PR sửa hoặc revert có căn cứ. Trưởng nhóm điều phối thông báo, bản được thay thế và các tài liệu cần cập nhật.

## 10. Onboarding, quyền truy cập và bàn giao

Trưởng nhóm giới thiệu phạm vi, vai trò, người dự phòng và công cụ. Thành viên đọc Charter, Proposal, Master Plan, phần PRD liên quan và kế hoạch chất lượng. Người phụ trách mảng hướng dẫn cách tìm file gốc, Issue, nhánh, PR và bằng chứng cần lưu.
Thành viên nhận một công việc đầu tiên có phạm vi và tiêu chí rõ, được reviewer phản hồi trước khi tiếp nhận phần lớn hơn. Khi tham gia vai trò kỹ thuật trong kế hoạch dự án, bổ sung hướng dẫn kiến trúc, môi trường và API contract.

Quyền chỉnh sửa được cấp theo nhiệm vụ. Quyền với dữ liệu nội bộ, tài khoản dịch vụ và môi trường được ghi nhận theo người phụ trách. Khi đổi trách nhiệm hoặc rời dự án, trưởng nhóm kiểm việc bàn giao, cập nhật owner và yêu cầu người quản lý dịch vụ thu hồi quyền phù hợp. Bí mật truy cập được lưu qua cơ chế quản lý bí mật có quyền hạn, tệp cấu hình cục bộ được loại khỏi Git.

## 11. Xác nhận và duy trì Charter

**Bản 2.4 — chờ thông qua.** Bằng chứng thông qua, phạm vi đã duyệt và ngày hiệu lực đang chờ nhóm ghi nhận. [PR #103](https://github.com/vinhdai123/UniSupport_Project/pull/103) là hồ sơ tích hợp bản 2.1. Quyết định áp dụng bản 2.4 cần có bản ghi biểu quyết riêng.

Nhóm cần xác nhận các nội dung sau.

1. Người dự phòng theo tài liệu, quyền điều phối nội bộ và cơ chế thay reviewer tại mục 2, 4, 6, 8 và 9.3.
2. Người có quyền kết luận khi có xung đột lợi ích, thứ tự thay thế và cách xử lý quá hạn tại mục 4 và 7.
3. Kênh liên hệ khẩn, khung giờ phối hợp và các mốc nội bộ đề xuất tại mục 3 và 5.
4. Quy tắc biểu quyết đề xuất ít nhất 3 trong 4 thành viên đồng ý để thông qua hoặc sửa Charter.
5. Người merge PR tài liệu và code, người phê duyệt, quyền repo và luồng PR phát hành thông thường tại mục 9.

Trưởng nhóm tổng hợp trong Issue, PR hoặc biên bản có liên kết. Bản ghi nêu phiên bản, ý kiến từng thành viên, các điều khoản được thông qua, các điều khoản còn mở, người chịu trách nhiệm và ngày hiệu lực. Sau khi có quyết định, chủ tài liệu cập nhật trạng thái đầu file và dẫn tới bản ghi này. Nếu nhóm duyệt từng phần, ghi phiên bản và ngày hiệu lực cho từng phần, các phần còn mở tiếp tục mang trạng thái đề xuất.

Nhóm xem lại Charter khi đổi thành viên, trách nhiệm, công cụ, lịch phối hợp hoặc khi quy tắc hiện hành gây vướng mắc.

## 12. Căn cứ và đối chiếu feedback

Bản này được viết từ Charter gốc của nhóm, review hiện tại, chuẩn môn và feedback R1. Nguồn đọc gồm

- Chuẩn môn, phần Nội dung tối thiểu, Format repo, Quy ước mã và Công bằng và dùng AI. [spm-standard.md](https://github.com/vinhdai123/UniSupport_Project/blob/e5beb485a45a2dc2962c768f66200d3c11bd651e/.claude/spm-standard.md).
- Feedback R1-08 trang 6 và R1-10 trang 7, bản đánh giá commit `7c1534ae93` ngày 04/11/2026. Bản PDF do nhóm cung cấp có tên `feedback-r1-nhom-1.pdf`.
- Cơ cấu, tuyến báo cáo, lịch họp và thẩm quyền phê duyệt trong tài liệu quản trị. [Nguồn quản trị đã đối chiếu](../11-governance/reporting.md).

| Nội dung feedback cần xử lý | Vị trí trong Charter | Bằng chứng cần bổ sung khi nhóm áp dụng |
| --- | --- | --- |
| Nơi gốc của Team Charter và mục lục | Mục 3 và 11 | Đường dẫn từ README và mục lục đã có. PR xử lý feedback cần dẫn tới issue tương ứng |
| Thành viên, vai trò và trách nhiệm tài liệu | Mục 2 | Xác nhận phân công của nhóm |
| Quy ước nhánh, PR, review và merge | Mục 9 | Quyết định thông qua và quyền thực tế của người phụ trách repo |
| Xử lý bất đồng | Mục 4 và 7 | Quy tắc được nhóm xác nhận, quyết định được lưu khi phát sinh |
| Khi thiếu người | Mục 6 | Người dự phòng được xác nhận, bản ghi bàn giao khi kích hoạt |
| Công cụ và lịch phối hợp thống nhất | Mục 3 và 5 | Liên kết tới nguồn lịch áp dụng và quyết định khi có thay đổi |

Đối chiếu điều kiện hoàn thành của R1-08 khi có PR dẫn tới issue feedback tương ứng. Bằng chứng thông qua quy tắc và ngày hiệu lực được ghi theo mục 11.
