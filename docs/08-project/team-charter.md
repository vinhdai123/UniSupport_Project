# Team Charter UniSupport

Phiên bản dự thảo 2.1 — ngày 17/11/2026

Dự án mô phỏng môn Software Project Management, phục vụ tình huống Aurora University với khoảng 3.000 sinh viên. Charter quy định trách nhiệm, phối hợp, quyết định, xử lý bất đồng và quản lý thay đổi trong quá trình xây dựng tài liệu, kế hoạch và quy trình dự án UniSupport.

**Trạng thái xác nhận.** Danh sách bốn thành viên và thông tin trưởng nhóm lấy từ feedback R1. MSSV và mảng phụ trách kế thừa README được nhóm cập nhật tại commit dfe998d. Reviewer, người dự phòng, quyền merge và các thời hạn bổ sung là phương án đề xuất để nhóm xác nhận. Lịch họp kế thừa tài liệu quản trị đã đọc. Các quy định có hiệu lực sau khi nhóm xác nhận phiên bản qua PR hoặc biên bản quyết định.

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

Danh sách theo feedback R1 gồm Trần Vĩnh Đại, Nguyễn Thành An, Phùng Ngô Huy Bảo và Huỳnh Hữu Như Mẫn. Trần Vĩnh Đại được ghi là trưởng nhóm. Mảng phụ trách trong bảng theo README cập nhật tại dfe998d. Người dự phòng là đề xuất cần nhóm xác nhận.

| Thành viên | Mảng phụ trách đề xuất | Trách nhiệm chính | Người dự phòng đề xuất |
| --- | --- | --- | --- |
| Trần Vĩnh Đại | Proposal, quản lý chất lượng và quản lý sản phẩm | Điều phối với vai trò trưởng nhóm, duy trì Proposal, Quality Plan, test/RTM và tài liệu quản lý sản phẩm | Huỳnh Hữu Như Mẫn |
| Nguyễn Thành An | Team Charter và Git | Duy trì Charter, tổ chức repo và quy trình Issue, branch, PR, review và merge theo quyền được nhóm xác nhận | Phùng Ngô Huy Bảo |
| Phùng Ngô Huy Bảo | Master Plan, quản trị và giám sát, báo giá | Duy trì kế hoạch, nguồn lực, rủi ro, Change Log, báo giá và số liệu quản trị, đối chiếu phạm vi–effort–lịch–giá | Nguyễn Thành An |
| Huỳnh Hữu Như Mẫn | PRD và review | Duy trì PRD/NFR/domain, kiểm bao phủ yêu cầu và tham gia review độc lập các tài liệu thuộc phạm vi được phân công | Trần Vĩnh Đại |

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

Khi reviewer tiếp nhận vai trò tác giả thay thế, nhóm chỉ định reviewer khác trước khi duyệt. File Word/Excel được chỉnh bởi một người tại một thời điểm, việc tiếp nhận chỉnh sửa được ghi vào Issue để tránh ghi đè phiên bản.

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

Vị trí đề xuất khi đưa Charter vào repo là `docs/08-project/team-charter.md`. Nhóm cập nhật `docs/README.md` và README gốc để người đọc tìm được bản này. Các đường dẫn trong bảng dưới là vị trí làm việc tại thư mục SPM hiện tại.

| Nội dung gốc | Vị trí để đối chiếu |
| --- | --- |
| Phạm vi, assumptions và nghiệm thu | [Proposal](proposal.docx) |
| Giá và khối lượng bán | [Báo giá](quotation.xlsx) |
| Ngày, WBS, MS-xx, nguồn lực, rủi ro và lịch sử kế hoạch | [Master Plan](master-plan.xlsx) |
| Lịch họp, báo cáo, cảnh báo và CR | Tài liệu Quản trị và giám sát của nhóm, mục Quy trình báo cáo và Quản lý thay đổi |
| FR, AC và NFR đang được review | PRD theo module trên nhánh làm việc, được nhận diện bằng commit trong Issue review |
| Quy trình QA/QC, DoD và điều kiện phát hành | Quality Plan được nhóm xác nhận |

Khi đưa bản này vào repo, người phụ trách mục lục cập nhật các liên kết theo vị trí file thật trong cùng PR. Kế hoạch chi phí và lợi nhuận nội bộ được lưu trong vùng hạn chế của nhóm, quyền truy cập được PM rà soát trước khi chia sẻ tài liệu.

## 4. Ra quyết định và kiểm soát thay đổi

### 4.1. Thẩm quyền theo loại quyết định

| Loại quyết định | Người chuẩn bị | Người quyết định hoặc xác nhận |
| --- | --- | --- |
| Phân công và ưu tiên bài làm trong cam kết hiện tại | Người phụ trách mảng | Trưởng nhóm hoặc người dự phòng đã tiếp nhận |
| Cách diễn đạt và cấu trúc PRD trong phạm vi đã thống nhất | Người phụ trách yêu cầu, reviewer chất lượng | Người phụ trách yêu cầu chốt sau review, trưởng nhóm xử lý bất đồng liên mảng |
| Lựa chọn kỹ thuật trong dự án Mô phỏng | Tech Lead tham vấn các vai trò bị ảnh hưởng | Tech Lead trong giới hạn phạm vi, lịch và ngân sách đã được xác nhận |
| Kế hoạch chất lượng và tiêu chí kiểm | Người phụ trách chất lượng hoặc QA Mô phỏng | Ban quản lý xác nhận tài liệu nội bộ, khách hàng xác nhận điều kiện nghiệm thu liên quan theo Proposal |
| Thay đổi effort, capacity và thứ tự công việc | Người phụ trách kế hoạch | Trưởng nhóm quyết định điều phối nội bộ, thay đổi cam kết được trình theo CR |
| Thay đổi phạm vi, giá, hạn hoặc điều kiện nghiệm thu đã cam kết | PM tổng hợp đánh giá tác động | Đại diện có thẩm quyền của Project Team và Aurora University xác nhận bằng văn bản |
| Thông qua hoặc thay đổi Charter | Trưởng nhóm tổng hợp ý kiến | Đề xuất cần ít nhất 3 trong 4 thành viên đồng ý, ghi rõ ý kiến và ngày áp dụng |

Quy tắc 3 trong 4 là đề xuất cần nhóm xác nhận. Thành viên vắng được gửi ý kiến bằng văn bản. Khi chưa đủ xác nhận, người điều phối ghi phần chưa thống nhất và tổ chức trao đổi tiếp. Trường hợp trưởng nhóm là một bên tranh chấp về tài liệu, người dự phòng chủ trì và lấy ý kiến hai thành viên còn lại.

### 4.2. Ghi nhận quyết định

Mỗi quyết định được lưu tại Issue hoặc biên bản được liên kết từ Issue, gồm mã theo dõi, nội dung, căn cứ, các phương án, người tham gia, người quyết định, ngày, tài liệu chịu ảnh hưởng và hành động tiếp theo. Các dữ kiện đang chờ xác nhận được ghi `TBD / Pending Confirmation`, cùng người cần xác nhận và hạn dự kiến.

Với các điểm PRD đã được review như trạng thái mở lại Ticket, giới hạn tệp, thời hạn mở lại và quyền dữ liệu, người phụ trách yêu cầu dẫn tới rule gốc và quyết định xác nhận. Người phụ trách chất lượng kiểm lại AC và kịch bản test sau khi quyết định được cập nhật.

### 4.3. Change Request

1. Người đề xuất tạo Issue CR theo mẫu, nêu lý do và tài liệu liên quan.
2. PM phối hợp người phụ trách yêu cầu, kế hoạch và chất lượng đánh giá phạm vi, effort, giá, ngày, nguồn lực, rủi ro và kiểm thử.
3. Người có thẩm quyền theo mục 4.1 xác nhận chấp thuận, từ chối hoặc hoãn và lưu căn cứ.
4. Với thay đổi được duyệt, chủ tài liệu cập nhật Proposal, PRD/AC/NFR, báo giá, WBS, Resources, rủi ro, test và Issue/Milestone bị ảnh hưởng.
5. Người phụ trách kế hoạch lưu phiên bản trước và thêm Change Log. Reviewer đối chiếu các nguồn trước khi merge.
6. PM thông báo quyết định, phạm vi áp dụng và ngày thực hiện cho các bên liên quan.

## 5. Lịch phối hợp và báo cáo

Lịch dưới đây kế thừa mục 2.1 và 2.2 của tài liệu Quản trị và giám sát đã được review. Nhóm xác nhận khả năng tham gia khi thông qua Charter. Thay đổi lịch sau đó được cập nhật ở tài liệu quản trị và dẫn chiếu từ Charter.

| Hoạt động | Lịch hiện được ghi trong tài liệu quản trị | Chủ trì và đầu ra |
| --- | --- | --- |
| Cập nhật trước họp ngày | Trước 08:40 mỗi ngày làm việc | Người thực hiện cập nhật Issue về kết quả, giờ công, ETA và blocker |
| Họp điều phối ngày | 08:45–09:00 trên Google Meet | PM điều phối, ghi người xử lý và thời hạn cho vấn đề phát sinh |
| Họp tuần | Thứ Sáu 15:00–15:45 trên Google Meet | PM tổng hợp tiến độ, nguồn lực, chất lượng, rủi ro và kế hoạch tuần sau |
| Review tài liệu | Theo hạn trong Issue và trước lần bàn giao liên quan | Chủ tài liệu gửi phiên bản, reviewer ghi nhận xét và kết quả xử lý |
| Họp xử lý bất đồng hoặc blocker | Khi phát sinh ảnh hưởng công việc phụ thuộc | Đầu mối theo mục 4 và 7 lưu quyết định, owner và hạn |
| Review trước bàn giao | Theo mốc MS-xx của Master Plan hiện hành | PM tổng hợp hồ sơ và điều kiện để trình xác nhận |

Giờ trong lịch dùng múi giờ Việt Nam, UTC+7. Khả dụng thực tế và giờ vắng được ghi ở Resources. Trưởng nhóm cùng từng thành viên xác nhận khung giờ phối hợp chung khi duyệt Charter.

Vấn đề thông thường được phản hồi trong ngày làm việc. Sự cố nghiêm trọng trong khung giờ phối hợp được xác nhận tiếp nhận và giao hướng xử lý ban đầu trong 30 phút theo tài liệu quản trị. Ngoài khung giờ đó, đầu mối xác nhận khi tiếp nhận cuộc gọi và ghi thời điểm cập nhật tiếp theo.

Người vắng họp báo đầu mối, gửi cập nhật trước cuộc họp khi có thể và đọc biên bản sau đó. Các quyết định ảnh hưởng công việc của người vắng phải được gửi trực tiếp để người đó xác nhận đã nhận thông tin.

## 6. Vắng dài ngày và bàn giao công việc

Ngưỡng kích hoạt đề xuất là vắng dự kiến từ một ngày làm việc trở lên, hoặc vắng trong thời điểm cần quyết định quan trọng, review hay bàn giao. Với tình huống đột xuất, trưởng nhóm kích hoạt phương án dự phòng ngay khi biết công việc có nguy cơ bị gián đoạn.

1. Người vắng hoặc người phát hiện báo trưởng nhóm, nêu thời gian dự kiến và các Issue bị ảnh hưởng.
2. Trưởng nhóm xác nhận người dự phòng theo mục 2.1, hoặc chỉ định người khác phù hợp khi người dự phòng cũng vắng.
3. Nội dung bàn giao gồm phiên bản file/commit, công việc đã thực hiện, việc còn lại, hạn, phụ thuộc, quyết định đang chờ và quyền truy cập cần dùng.
4. Người tiếp nhận xác nhận trong Issue, kiểm quyền truy cập và khả năng hoàn thành. PM hoặc trưởng nhóm cập nhật owner, người review và ETA.
5. Người phụ trách kế hoạch kiểm tác động tới capacity, lịch, rủi ro và mốc. Nếu cần thay đổi cam kết, thực hiện CR theo mục 4.3.
6. Khi thành viên quay lại, hai người đối chiếu các thay đổi và trưởng nhóm xác nhận việc chuyển lại trách nhiệm.

Nếu người giữ báo giá vắng, người dự phòng tiếp nhận file nguồn đã xác định, đối chiếu tổng và công thức, cập nhật theo CR được duyệt và yêu cầu một thành viên độc lập kiểm lại trước khi phát hành. Quyền truy cập được cấp theo tài khoản riêng và phạm vi cần thiết.

## 7. Bất đồng, blocker và escalation

### 7.1. Bất đồng giữa thành viên

Hai bên ghi rõ nội dung đang tranh luận, nguồn yêu cầu, bằng chứng và phương án cùng tác động trong Issue. Đầu mối phụ trách tổ chức trao đổi để thống nhất cách xử lý. Mốc xử lý nội bộ đề xuất là trong một ngày làm việc từ khi đủ thông tin, hoặc sớm hơn theo hạn của công việc phụ thuộc.

Nếu vẫn bất đồng, xử lý theo mục 4.1. Người chủ trì ghi kết luận, căn cứ và ý kiến còn khác biệt. Khi quyết định làm thay đổi cam kết với khách hàng, PM trình theo CR và lưu xác nhận của hai bên.

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

Khi trễ hạn, owner ghi nguyên nhân, mức ảnh hưởng, ETA mới và đề xuất xử lý. Người phụ trách kế hoạch kiểm việc phụ thuộc, trưởng nhóm chốt điều phối hoặc trình CR. Mỗi lần thay đổi kế hoạch được lưu theo quy trình phiên bản trong Master Plan.

## 9. Branch, PR, review và merge

Các quy tắc chi tiết dưới đây là phương án đề xuất cho nhóm thông qua và cấu hình quyền tương ứng.

### 9.1. Branch và commit

- Thay đổi tài liệu dùng `docs/<issue>-<noi-dung>`, tạo từ `main` và mở PR về `main`. Nhánh `docs/issue-98-refactor-prd` là một ví dụ đang dùng trong repo.
- Khi triển khai phần mềm theo kế hoạch, `feature/<issue>-<noi-dung>` và `bugfix/<issue>-<noi-dung>` được tạo từ `develop`, mở PR về `develop`. Người quản lý repo xác nhận nhánh và quyền trước khi áp dụng luồng này.
- `hotfix/<issue>-<noi-dung>` phục vụ sửa sự cố khẩn của bản phát hành, tạo từ `main`, PR về `main` rồi đưa thay đổi tương ứng vào `develop` theo điều phối Tech Lead.
- Commit mô tả đúng thay đổi, tập trung vào một nội dung. Với tài liệu có thể dùng `docs: clarify ticket reopen criteria`.
- Mọi thay đổi vào `main` được thực hiện qua PR và có lịch sử review.

### 9.2. Nội dung PR
PR ghi vấn đề và Issue liên quan, quyết định được đề xuất, file/mục thay đổi, tác động liên tài liệu, cách kiểm và các điểm chờ xác nhận. Với feedback R1, ghi rõ mã feedback và đối chiếu dòng Hoàn thành khi.

Word/Excel phải có mô tả thay đổi bằng chữ trong PR. Báo giá hoặc Master Plan thay đổi phải kèm kiểm tổng, công thức, ngày, capacity và các liên kết liên quan. Tác giả lưu bản trước theo quy trình phiên bản trước khi chỉnh file.

### 9.3. Review và phê duyệt

Mỗi PR cần ít nhất một người khác tác giả approve. Dùng reviewer chính tại mục 2.3. Khi reviewer trở thành người sửa nội dung, chỉ định người review độc lập thay thế.

Reviewer kiểm nội dung theo chuẩn môn và yêu cầu của Issue, mã/liên kết còn dùng được, sự nhất quán với phạm vi và tài liệu phụ thuộc, nguồn và trạng thái xác nhận của thông số. Với PRD, kiểm đủ nội dung mẫu FR, quan hệ rule/error–AC, NFR và kịch bản test chịu ảnh hưởng. Với tài liệu kế hoạch, kiểm ngày, effort và cơ sở huy động.

Các nhận xét cần sửa phải được xử lý hoặc có kết luận được ghi nhận. Thay đổi nội dung sau approve phải được reviewer kiểm lại phần bị ảnh hưởng trước khi merge. Phần mã nguồn, nếu được thực hiện, áp dụng thêm kiểm thử và review kỹ thuật phù hợp với thay đổi.

### 9.4. Thẩm quyền merge

Đề xuất Trần Vĩnh Đại thực hiện merge PR tài liệu đã được approve. Huỳnh Hữu Như Mẫn là người thay thế khi Đại vắng hoặc cần chuyển quyền điều phối. Cả hai chỉ thực hiện khi được người quản lý repo cấp quyền và nhóm xác nhận phân công. Nếu cả hai vắng, các thành viên còn lại ghi quyết định chỉ định người thay thế và nhờ người quản lý repo cấp quyền cần thiết.

Trước merge, người thực hiện kiểm nhánh đích, phiên bản cuối, approve độc lập, nhận xét còn mở, conflict, liên kết và các kiểm tra áp dụng. Khi có conflict ở file Word/Excel, chủ tài liệu và reviewer đối chiếu hai bản để tạo một bản hợp nhất được kiểm lại.

Nếu phát hiện sai sau merge, tạo Issue ghi ảnh hưởng và dùng PR sửa hoặc revert có căn cứ. Trưởng nhóm điều phối thông báo, bản được thay thế và các tài liệu cần cập nhật.

## 10. Onboarding, quyền truy cập và bàn giao

Trưởng nhóm giới thiệu phạm vi, vai trò, người dự phòng và công cụ. Thành viên đọc Charter, Proposal, Master Plan, phần PRD liên quan và kế hoạch chất lượng. Người phụ trách mảng hướng dẫn cách tìm file gốc, Issue, nhánh, PR và bằng chứng cần lưu.
Thành viên nhận một công việc đầu tiên có phạm vi và tiêu chí rõ, được reviewer phản hồi trước khi tiếp nhận phần lớn hơn. Khi tham gia vai trò kỹ thuật trong kế hoạch dự án, bổ sung hướng dẫn kiến trúc, môi trường và API contract.

Quyền chỉnh sửa được cấp theo nhiệm vụ. Quyền với dữ liệu nội bộ, tài khoản dịch vụ và môi trường được ghi nhận theo người phụ trách. Khi đổi trách nhiệm hoặc rời dự án, trưởng nhóm kiểm việc bàn giao, cập nhật owner và yêu cầu người quản lý dịch vụ thu hồi quyền phù hợp. Bí mật truy cập được lưu qua cơ chế quản lý bí mật có quyền hạn, tệp cấu hình cục bộ được loại khỏi Git.

## 11. Xác nhận và duy trì Charter

Trưởng nhóm tổng hợp ý kiến bốn thành viên và lưu quyết định thông qua, phiên bản, ngày hiệu lực cùng các nội dung còn mở trong PR hoặc biên bản. Tài liệu được review khi có thay đổi thành viên, trách nhiệm, công cụ, lịch phối hợp hoặc vấn đề cho thấy quy tắc cần điều chỉnh.

Các nội dung cần nhóm xác nhận trước khi áp dụng bản dự thảo này gồm

1. Phân công, reviewer và người dự phòng tại mục 2.
2. Kênh trao đổi mặc định, lịch họp kế thừa và khung giờ phối hợp chung.
3. Ngưỡng vắng một ngày, thời hạn xử lý bất đồng một ngày và phương án tiếp nhận đột xuất.
4. Cơ chế ít nhất 3 trong 4 người đồng ý khi thông qua hoặc thay đổi Charter.
5. Quy ước nhánh đích, approve độc lập, người merge và quyền repo thực tế.
6. Vị trí gốc trong repo và cách cập nhật mục lục, các liên kết đang dùng tại thư mục SPM.

Sau khi nhóm xác nhận, người phụ trách ghi ngày áp dụng và dẫn tới bằng chứng quyết định. Các thay đổi tiếp theo có PR, người review và lịch sử phiên bản.

## 12. Căn cứ và đối chiếu feedback

Bản này được viết từ Charter gốc của nhóm, review hiện tại, chuẩn môn và feedback R1. Nguồn đọc gồm

- Chuẩn môn, phần Nội dung tối thiểu, Format repo, Quy ước mã và Công bằng và dùng AI. [spm-standard.md](https://github.com/vinhdai123/UniSupport_Project/blob/e5beb485a45a2dc2962c768f66200d3c11bd651e/.claude/spm-standard.md).
- Feedback R1-08 trang 6 và R1-10 trang 7, bản đánh giá commit `7c1534ae93` ngày 04/11/2026. Bản PDF do nhóm cung cấp có tên `feedback-r1-nhom-1.pdf`.
- Cơ cấu, tuyến báo cáo, lịch họp và thẩm quyền phê duyệt trong tài liệu quản trị. [Nguồn quản trị đã đối chiếu](../11-governance/reporting.md).

| Nội dung feedback cần xử lý | Vị trí trong Charter mới | Bằng chứng cần bổ sung khi nhóm áp dụng |
| --- | --- | --- |
| Nơi gốc của Team Charter và mục lục | Mục 3 và 11 | File trong repo, link từ mục lục và PR liên kết issue feedback |
| Thành viên, vai trò và trách nhiệm tài liệu | Mục 2 | Xác nhận phân công của nhóm |
| Quy ước nhánh, PR, review và merge | Mục 9 | Quyết định thông qua và quyền thực tế của người phụ trách repo |
| Xử lý bất đồng | Mục 4 và 7 | Quy tắc được nhóm xác nhận, quyết định được lưu khi phát sinh |
| Khi thiếu người | Mục 6 | Người dự phòng được xác nhận, bản ghi bàn giao khi kích hoạt |
| Công cụ và lịch phối hợp thống nhất | Mục 3 và 5 | Liên kết tới nguồn lịch áp dụng và quyết định khi có thay đổi |

Bảng này mô tả phần nội dung đã soạn và bằng chứng cần có khi áp dụng. Nhóm dùng điều kiện Hoàn thành khi trong feedback để xác nhận xử lý xong R1-08 sau khi hoàn tất cập nhật repo và liên kết PR.
