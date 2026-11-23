# Yêu cầu phi chức năng (Non-Functional Requirements)

Chính sách chỉ dùng dữ liệu giả lập với ngưỡng 0 bản ghi thật áp dụng theo NFR-GLOBAL-01. Các ngưỡng đo còn đề xuất trong bảng cần đại diện nhóm và khách hàng Mô phỏng xác nhận trước khi dùng làm baseline nghiệm thu. Người phụ trách PRD lưu quyết định, dữ liệu và công cụ đo trong Issue liên quan. [Hồ sơ xác nhận ngưỡng OQ-06](../09-quality/quality-plan.md#xác-nhận-ngưỡng-chất-lượng-oq-06).

| Mã | Nhóm | Yêu cầu | Ngưỡng đo | Cách đo | Áp dụng cho |
| --- | --- | --- | --- | --- | --- |
| NFR-GLOBAL-01 | Dữ liệu kiểm thử | Dùng 100% dữ liệu giả lập trên Dev/Test/Staging, gồm UAT trên Staging | 0 bản ghi thật trên Dev/Test/Staging | Audit dữ liệu và đối chiếu nguồn bộ dữ liệu từng môi trường | Toàn hệ thống |
| NFR-GLOBAL-02 | Đa ngôn ngữ | Hỗ trợ song ngữ Tiếng Việt & Tiếng Anh | 100% nhãn, nút, thông báo hệ thống được bản địa hóa | UI Test Suite / Manual check | Toàn bộ giao diện M01-M05 |
| NFR-GLOBAL-03 | Tính tương thích | Web Responsive trên Desktop và Mobile | Layout chuẩn trên màn hình >= 375px (Mobile) và >= 1024px (Desktop) | Chrome DevTools Responsive / BrowserStack | Toàn bộ giao diện M01-M05 |
| NFR-GLOBAL-04 | Usability | Giao diện nhất quán, rõ ràng, dễ sử dụng | 100% form có validation feedback; thuật ngữ nhất quán | Usability review / UAT | Toàn bộ giao diện M01-M05 |
| NFR-PERF-01 | Hiệu năng | Thời gian phản hồi trang chính | 95% request trả về < 1.5s khi 100 người dùng đồng thời | JMeter / K6 Load testing | M01, M02, M03 |
| NFR-SEC-01 | Bảo mật | Kiểm soát quyền truy cập RBAC và bảo vệ phiên làm việc | 0 ca truy cập trái phép trong bộ kiểm thử quyền đã xác nhận, JWT hết hạn sau 24h theo cấu hình đề xuất | OWASP ZAP / Security Testing | Toàn hệ thống |

## Màn hình dùng để đo NFR giao diện

NFR-GLOBAL-02, 03 và 04 đo trên danh sách màn hình dưới đây. Ở MS-01 đến MS-04, QA kiểm các AC này trên màn hình đã giao của mốc, và mỗi module được làm VI/EN, responsive trong hạng mục báo giá của chính module đó (cột Module và FR, sheet Báo giá, [quotation.xlsx](../08-project/quotation.xlsx)). MS-05 chạy đủ 19 AC trên S01–S14. TS-117 đến TS-122 đo lại ngưỡng tổng trên bản tích hợp MS-06.

| Mã | Màn hình | Module | Giao ở mốc |
| --- | --- | --- | --- |
| S01 | Đăng nhập, đăng xuất | M01 | MS-01 |
| S02 | Đặt lại mật khẩu | M01 | MS-02 |
| S03 | Quản trị tài khoản và vai trò | M01 (FR-AUTH-07) | MS-02 |
| S04 | Tạo Ticket | M02 | MS-03 |
| S05 | Danh sách và chi tiết Ticket của sinh viên | M02 | MS-03 |
| S06 | FAQ | M02 | MS-03 |
| S07 | Thông báo, bổ sung thông tin, mở lại, CSAT | M02 | MS-04 |
| S08 | Hàng đợi Ticket của cán bộ | M03 | MS-04 |
| S09 | Chi tiết Ticket của cán bộ: phản hồi, ghi chú, chuyển, trạng thái | M03 | MS-04 |
| S10 | Cấu hình danh mục, phòng ban, routing | M04 | MS-04 |
| S11 | Cấu hình SLA, lịch làm việc, mẫu phản hồi, FAQ | M04 | MS-04 |
| S12 | Workload và phân công lại | M04 | MS-04 |
| S13 | Dashboard tổng quan | M05 | MS-05 |
| S14 | Báo cáo hiệu suất, xu hướng, CSAT và xuất CSV | M05 | MS-05 |

**Bố cục chuẩn** (ngưỡng NFR-GLOBAL-03) nghĩa là ở độ rộng đo: trang không cuộn ngang, không phần tử bị che hoặc cắt chữ, mọi trường và nút của luồng chính thao tác được. Bảng dữ liệu rộng được cuộn trong khung riêng. Độ rộng đo: 375×812 (Mobile), 1024×768 và 1366×768 (Desktop).

---

# GLOBAL NON-FUNCTIONAL REQUIREMENTS

# 1. Tổng quan

Các yêu cầu trong tài liệu này áp dụng xuyên suốt toàn bộ hệ thống UniSupport
và không thuộc riêng một Functional Module.

Phạm vi áp dụng bao gồm:

- M01 – Security, Authentication & RBAC.
- M02 – Student Portal.
- M03 – Staff Desk.
- M04 – Management & Administration.
- M05 – Dashboard & Report.

Các yêu cầu phi chức năng trong tài liệu này được sử dụng làm tiêu chí chung
trong quá trình thiết kế, phát triển, kiểm thử và nghiệm thu hệ thống.

---

# 2. Non-Functional Requirements

## NFR-GLOBAL-01 – Development & Testing Data

### Requirement

Trong phạm vi dự án hiện hành, Dev, Test và Staging, kể cả UAT trên Staging, chỉ dùng dữ liệu giả lập. Ngưỡng kiểm là **0 bản ghi thật**. Mọi đề xuất thay đổi chính sách cần đánh giá và phê duyệt qua Change Request trước khi áp dụng.

### Applies To

- Development Environment.
- Testing Environment.
- Integration Testing.
- System Testing.
- Chuẩn bị và thực hiện UAT trên Staging.

### Processing / Expected Behavior

1. Project Team chuẩn bị dữ liệu giả lập phục vụ Development và Testing.
2. Mock Data phải hỗ trợ các tình huống cần thiết để kiểm thử Functional Requirements.
3. DevOps kiểm nguồn bộ dữ liệu trước khi nạp. Nếu không chứng minh được là dữ liệu giả lập, giữ ngoài môi trường và báo PM.
4. QA và DevOps đối chiếu dữ liệu đã nạp với nguồn bộ dữ liệu giả lập trước đợt kiểm/UAT. Có bản ghi thật hoặc nguồn không xác minh được thì chặn sử dụng môi trường để kiểm, xử lý dữ liệu và kiểm lại.
5. Dữ liệu giả lập bao phủ vai trò, Ticket, danh mục và phòng ban theo kịch bản kiểm thử.

### Output

- Development Environment có dữ liệu phục vụ phát triển.
- Testing Environment có dữ liệu phục vụ kiểm thử.
- Functional Requirements có thể được kiểm thử mà không phụ thuộc vào dữ liệu thật của Aurora University.

### Acceptance Criteria

**NFR-GLOBAL-01/AC-01 – Development dùng dữ liệu giả lập**

- Given: Bộ dữ liệu giả lập phiên bản hiện hành có manifest nguồn: 4 vai trò và 50 Ticket đánh dấu MOCK.
- When: Developer khởi tạo môi trường Dev bằng script nạp dữ liệu của dự án.
- Then: Môi trường có đủ 4 vai trò và 50 Ticket. 100% bản ghi mang nhãn MOCK, 0 bản ghi lấy từ nguồn thật.

**NFR-GLOBAL-01/AC-02 – Testing dùng dữ liệu giả lập**

- Given: Test run của một mốc và danh sách TS của mốc đó.
- When: QA nạp dữ liệu Test/Staging và đối chiếu tài khoản, Ticket mà từng TS cần.
- Then: Mọi TS của mốc dùng tài khoản và Ticket có trong manifest (SV-MOCK-01/02, Staff A/B, Manager A/B, Admin). Số TS thiếu dữ liệu là 0, không TS nào phải tạo dữ liệu thật.

**NFR-GLOBAL-01/AC-03 – Chỉ dùng dữ liệu giả lập trên Dev/Test/Staging**

- Given: Có danh sách nguồn của bộ dữ liệu thử và một bộ mẫu tổng hợp mô phỏng nguồn chưa xác minh.
- When: Đối chiếu bộ dữ liệu đã nạp trên Dev/Test/Staging, kiểm quyết định nhận hoặc từ chối bộ mẫu chưa xác minh.
- Then: Số bản ghi thật là 0, mọi bộ được dùng truy vết được về nguồn giả lập, bộ chưa xác minh bị loại khỏi đợt kiểm cho tới khi xác minh. Lưu bằng chứng audit và quyết định cho từng môi trường.

**NFR-GLOBAL-01/AC-04 – Dữ liệu giả lập đủ tình huống kiểm thử chức năng**

- Given: Danh sách tình huống tại mục Dữ liệu dùng chung của [kịch bản test](../06-acceptance/test-scenarios.md#dữ-liệu-dùng-chung).
- When: QA đối chiếu manifest với danh sách tình huống.
- Then: Có ít nhất một Ticket cho mỗi trạng thái New, In Progress, Pending, Resolved; có và không có tệp; đúng hạn và quá hạn; có và không có CSAT; đủ bộ DT-01, IT-01, DT-02 cho chuyển phòng. Mỗi tình huống thiếu ghi Fail.

### TBD / Pending Confirmation

- Bộ Mock Data chuẩn của dự án.
- Cách quản lý và reset Test Data giữa các lần kiểm thử.

---

## NFR-GLOBAL-02 – Hỗ trợ Tiếng Việt và Tiếng Anh

### User Story

Là **người dùng UniSupport**, tôi muốn sử dụng hệ thống bằng Tiếng Việt hoặc
Tiếng Anh để có thể tương tác với giao diện bằng ngôn ngữ phù hợp.

### Requirement

Giao diện UniSupport phải hỗ trợ:

- Tiếng Việt.
- Tiếng Anh.

### Applies To

Yêu cầu này áp dụng cho các giao diện người dùng của:

- M01 – Authentication.
- M02 – Student Portal.
- M03 – Staff Desk.
- M04 – Management & Administration.
- M05 – Dashboard & Report.

### Processing / Expected Behavior

1. Hệ thống phải có khả năng hiển thị giao diện bằng Tiếng Việt.
2. Hệ thống phải có khả năng hiển thị giao diện bằng Tiếng Anh.
3. Khi một ngôn ngữ được áp dụng:
   - Label.
   - Button.
   - Menu.
   - Navigation.
   - Form field.
   - System message.
   - Các nội dung giao diện thuộc phạm vi hệ thống.

   phải hiển thị nhất quán theo ngôn ngữ tương ứng.
4. Việc thay đổi ngôn ngữ không được làm thay đổi dữ liệu nghiệp vụ của người dùng.
5. Việc thay đổi ngôn ngữ không được làm mất trạng thái hoặc quyền truy cập của User.

### Output

- Giao diện Tiếng Việt.
- Giao diện Tiếng Anh.

### Acceptance Criteria

**NFR-GLOBAL-02/AC-01 – Giao diện Tiếng Việt**

- Given: Ngôn ngữ đang chọn là Tiếng Việt. Danh sách màn hình đã giao của mốc lấy từ S01–S14.
- When: QA mở từng màn hình, kích hoạt một thông báo thành công và một thông báo lỗi của luồng chính.
- Then: 100% nhãn, nút, tiêu đề, placeholder và thông báo hệ thống hiển thị Tiếng Việt. Còn một chuỗi Tiếng Anh hoặc khóa dịch thô (ví dụ `ticket.submit`) là Fail. Nội dung người dùng nhập không thuộc phạm vi dịch.

**NFR-GLOBAL-02/AC-02 – Giao diện Tiếng Anh**

- Given: Ngôn ngữ đang chọn là Tiếng Anh. Danh sách màn hình đã giao của mốc lấy từ S01–S14.
- When: QA mở từng màn hình, kích hoạt một thông báo thành công và một thông báo lỗi của luồng chính.
- Then: 100% nhãn, nút, tiêu đề, placeholder và thông báo hệ thống hiển thị Tiếng Anh. Còn một chuỗi Tiếng Việt hoặc khóa dịch thô là Fail.

**NFR-GLOBAL-02/AC-03 – Giữ ngôn ngữ khi chuyển module**

- Given: Người dùng đã chọn Tiếng Anh.
- When: Đi qua các màn hình theo quyền của vai trò (ví dụ S01 → S05 → S08 → S13), tải lại trang, đăng xuất rồi đăng nhập lại.
- Then: Mọi màn hình giữ Tiếng Anh, lựa chọn được nhớ theo tài khoản. Số màn hình tự đổi ngôn ngữ là 0.

**NFR-GLOBAL-02/AC-04 – Đổi ngôn ngữ không đổi dữ liệu**

- Given: Ticket AU-2026-0001 có tiêu đề, nội dung và trạng thái; Dashboard có số liệu của bộ dữ liệu giả lập.
- When: Ghi lại nội dung Ticket, số đếm Dashboard và tệp CSV, đổi Tiếng Việt ↔ Tiếng Anh rồi ghi lại lần nữa.
- Then: Nội dung Ticket, số đếm và dữ liệu CSV giống hệt trước khi đổi. Chỉ nhãn giao diện và tên trạng thái hiển thị theo ngôn ngữ.

### TBD / Pending Confirmation

- Ngôn ngữ mặc định.
- Cơ chế lựa chọn/chuyển ngôn ngữ.
- Ngôn ngữ được lưu theo User hay theo phiên sử dụng.
- Phạm vi dịch đối với nội dung do người dùng nhập.
- Phạm vi dịch đối với FAQ/Knowledge Base.
- Đơn vị chịu trách nhiệm cung cấp nội dung dịch nghiệp vụ.

---

## NFR-GLOBAL-03 – Responsive trên Desktop và Mobile

### User Story

Là **người dùng UniSupport**, tôi muốn sử dụng hệ thống trên Desktop và Mobile
để có thể truy cập các chức năng chính trên các kích thước màn hình khác nhau.

### Requirement

UniSupport phải hỗ trợ giao diện Responsive trên:

- Desktop.
- Mobile.

Đây là Web Responsive và không phải Native Mobile Application.

### Applies To

Tất cả các giao diện chính của:

- M01 – Authentication.
- M02 – Student Portal.
- M03 – Staff Desk.
- M04 – Management & Administration.
- M05 – Dashboard & Report.

### Processing / Expected Behavior

1. Giao diện phải điều chỉnh bố cục phù hợp với kích thước màn hình.
2. Các chức năng chính phải tiếp tục sử dụng được khi truy cập bằng Desktop.
3. Các chức năng chính phải tiếp tục sử dụng được khi truy cập bằng Mobile.
4. Nội dung chính không được bị che khuất hoặc mất khả năng thao tác do thay đổi kích thước màn hình.
5. Navigation và các thao tác chính phải có khả năng sử dụng trên cả Desktop và Mobile.
6. Responsive Design không được làm thay đổi Business Logic của hệ thống.

### Output

- Giao diện sử dụng được trên Desktop.
- Giao diện sử dụng được trên Mobile.

### Acceptance Criteria

**NFR-GLOBAL-03/AC-01 – Desktop**

- Given: Chrome và Edge bản ổn định hiện hành ở 1024×768 và 1366×768.
- When: Thực hiện luồng chính trên từng màn hình đã giao của mốc.
- Then: Đạt bố cục chuẩn ở cả hai độ rộng: không cuộn ngang trang, không che hoặc cắt chữ, mọi trường và nút của luồng chính thao tác được.

**NFR-GLOBAL-03/AC-02 – Mobile**

- Given: Chrome Android và Safari iOS ở 375×812.
- When: Thực hiện luồng chính trên từng màn hình đã giao của mốc.
- Then: Đạt bố cục chuẩn ở 375px. Menu thu gọn mở được, bảng dữ liệu cuộn trong khung riêng, trang không cuộn ngang.

**NFR-GLOBAL-03/AC-03 – Đổi kích thước màn hình**

- Given: Một màn hình đã giao đang mở ở 1366px và đang nhập dở một form.
- When: Thu hẹp cửa sổ qua 1024px, 768px rồi 375px.
- Then: Ở mỗi độ rộng, bố cục đạt chuẩn, không mất trường hoặc nút của luồng chính và dữ liệu đang nhập không mất.

**NFR-GLOBAL-03/AC-04 – Điều hướng**

- Given: Mỗi vai trò đăng nhập ở 375px và 1024px.
- When: Từ trang chủ của vai trò, mở menu và đi tới từng màn hình theo quyền.
- Then: Mọi màn hình theo quyền tới được trong tối đa 3 lần chạm hoặc nhấp từ trang chủ của vai trò ở cả hai độ rộng.

**NFR-GLOBAL-03/AC-05 – Cùng quy tắc trên Desktop và Mobile**

- Given: Tài khoản Staff A, Ticket DT-01 và một ghi chú nội bộ của phòng B.
- When: Thực hiện cùng thao tác đổi trạng thái và xem ghi chú phòng B ở 375px rồi ở 1366px.
- Then: Kết quả, thông báo lỗi và quyền giống nhau ở hai độ rộng. API trả cùng mã phản hồi.

### TBD / Pending Confirmation

- Breakpoint cụ thể.
- Minimum Screen Width.
- Browser Support Matrix.
- Mobile Browser được hỗ trợ.
- Desktop Browser được hỗ trợ.
- Tablet có được xem là phạm vi bắt buộc hay không.

---

## NFR-GLOBAL-04 – Giao diện đơn giản, nhất quán và dễ sử dụng

### User Story

Là **người dùng UniSupport**, tôi muốn giao diện đơn giản, nhất quán và dễ hiểu
để có thể thực hiện các tác vụ mà không gặp khó khăn không cần thiết.

### Requirement

Giao diện UniSupport phải đảm bảo:

- Đơn giản.
- Nhất quán.
- Dễ sử dụng.

### Applies To

Toàn bộ giao diện của UniSupport.

### Processing / Expected Behavior

#### Tính nhất quán

1. Các chức năng có cùng mục đích phải sử dụng cách đặt tên nhất quán.
2. Các hành động phổ biến phải được thể hiện nhất quán giữa các Module.
3. Các trạng thái Ticket phải sử dụng cùng cách gọi trên toàn hệ thống.
4. Category, Priority, Role và các thuật ngữ nghiệp vụ phải được sử dụng nhất quán.

#### Khả năng sử dụng

1. Người dùng phải có khả năng nhận biết hành động chính trên màn hình.
2. Form phải thể hiện rõ các thông tin cần nhập.
3. Khi thao tác không thành công, hệ thống phải cung cấp phản hồi phù hợp.
4. Khi thao tác thành công, hệ thống phải cung cấp phản hồi để User biết kết quả.
5. Các màn hình phải ưu tiên hiển thị thông tin cần thiết cho nghiệp vụ tương ứng.

#### Điều hướng

1. User phải có khả năng truy cập các chức năng được cấp quyền.
2. Navigation phải nhất quán giữa các màn hình thuộc cùng hệ thống.
3. User không được nhìn thấy hoặc sử dụng Function ngoài Permission được cấp theo M01.

### Output

- Giao diện nhất quán giữa các Module.
- User nhận biết được chức năng và kết quả thao tác.
- Navigation phù hợp với Role.

### Acceptance Criteria

**NFR-GLOBAL-04/AC-01 – Thuật ngữ nhất quán**

- Given: Bảng thuật ngữ tại [terminology.md](../02-domain/terminology.md).
- When: QA rà nhãn của các màn hình đã giao ở cả hai ngôn ngữ.
- Then: Ticket, Category, Priority và bốn vai trò dùng đúng một cách gọi theo bảng thuật ngữ ở mỗi ngôn ngữ. Mỗi cách gọi khác ghi Fail.

**NFR-GLOBAL-04/AC-02 – Trạng thái Ticket nhất quán**

- Given: Có Ticket ở đủ bốn trạng thái.
- When: Xem cùng Ticket ở S05, S08, S09, S13 và trong tệp CSV.
- Then: Trạng thái hiển thị đúng bốn cặp Mới tạo/New, Đang xử lý/In Progress, Cần bổ sung/Pending, Hoàn thành/Resolved. Số cách gọi khác là 0.

**NFR-GLOBAL-04/AC-03 – Phản hồi khi nhập sai**

- Given: Danh sách form đã giao của mốc: S01, S02, S03, S04, S07, S09, S10, S11, S12.
- When: Gửi mỗi form với một trường bắt buộc để trống, sau đó với một trường sai định dạng.
- Then: 100% form chặn gửi, đánh dấu đúng trường lỗi và nêu cách sửa bằng ngôn ngữ đang chọn. Form gửi được hoặc chỉ báo lỗi chung là Fail.

**NFR-GLOBAL-04/AC-04 – Phản hồi khi thao tác thành công**

- Given: Các thao tác tạo, lưu, gửi và xuất trên màn hình đã giao.
- When: Thực hiện thành công từng thao tác.
- Then: Mỗi thao tác hiển thị thông báo thành công nêu đối tượng vừa xử lý (ví dụ mã Ticket), và dữ liệu mới hiện trên màn hình mà không cần tải lại trang.

**NFR-GLOBAL-04/AC-05 – Giao diện theo quyền**

- Given: Bốn tài khoản Student, Staff, Manager, Administrator và ma trận quyền đã xác nhận tại OQ-05.
- When: Đăng nhập lần lượt từng tài khoản và mở mọi mục trên menu.
- Then: Menu và nút chỉ hiện chức năng có trong ma trận quyền của vai trò. Số nút dẫn tới màn hình bị từ chối là 0.

**NFR-GLOBAL-04/AC-06 – Thể hiện dữ liệu nhất quán giữa module**

- Given: Ticket DT-01 xuất hiện ở M02, M03 và M05.
- When: So sánh cùng Ticket ở S05, S09, S13 và trong CSV.
- Then: Cùng mã Ticket, tên phòng, trạng thái và định dạng ngày giờ dd/mm/yyyy HH:mm (UTC+7) ở mọi nơi.

### TBD / Pending Confirmation

- Design System cụ thể.
- Typography.
- Color System.
- Component Library.
- Spacing System.
- Icon Library.
- Accessibility Standard.
- Usability Metric cụ thể.


Các yêu cầu mới ngoài In-Scope phải được xử lý thông qua Change Request.
