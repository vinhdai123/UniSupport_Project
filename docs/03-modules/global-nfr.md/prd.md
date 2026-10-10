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

Trong quá trình Development và Testing, hệ thống UniSupport phải sử dụng
dữ liệu giả lập theo phạm vi đã thống nhất.

Không sử dụng dữ liệu thật của Aurora University khi chưa được phép.

### Applies To

- Development Environment.
- Testing Environment.
- Integration Testing.
- System Testing.
- UAT Preparation nếu sử dụng dữ liệu giả lập.

### Processing / Expected Behavior

1. Project Team chuẩn bị dữ liệu giả lập phục vụ Development và Testing.
2. Mock Data phải hỗ trợ các tình huống cần thiết để kiểm thử Functional Requirements.
3. Các Module sử dụng Mock Data thay cho dữ liệu thật của Aurora University trong quá trình phát triển và kiểm thử.
4. Nếu cần sử dụng dữ liệu thật:
   - Phải có sự cho phép phù hợp từ Aurora University.
5. Dữ liệu giả lập phải có khả năng hỗ trợ kiểm thử các Role, Ticket, Category, Department và các chức năng liên quan trong phạm vi dự án.

### Output

- Development Environment có dữ liệu phục vụ phát triển.
- Testing Environment có dữ liệu phục vụ kiểm thử.
- Functional Requirements có thể được kiểm thử mà không phụ thuộc vào dữ liệu thật của Aurora University.

### Acceptance Criteria

**AC1 – Development sử dụng Mock Data**

- Given: Hệ thống đang được phát triển.
- When: Developer cần dữ liệu để phát triển chức năng.
- Then: Có dữ liệu giả lập phù hợp để sử dụng.

**AC2 – Testing sử dụng Mock Data**

- Given: QA thực hiện kiểm thử chức năng.
- When: Test Case yêu cầu dữ liệu đầu vào.
- Then: Có Mock Data phù hợp để thực hiện kiểm thử.

**AC3 – Không tự ý sử dụng dữ liệu thật**

- Given: Dữ liệu thật của Aurora University chưa được cho phép sử dụng.
- When: Development hoặc Testing được thực hiện.
- Then: Dữ liệu thật không được sử dụng trong các môi trường tương ứng.

**AC4 – Mock Data hỗ trợ Functional Testing**

- Given: Một Functional Requirement cần được kiểm thử.
- When: QA chuẩn bị Test Data.
- Then: Mock Data phải có khả năng hỗ trợ các trường hợp kiểm thử cần thiết.

### TBD / Pending Confirmation

- Quy trình phê duyệt khi cần sử dụng dữ liệu thật.
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

**AC1 – Giao diện Tiếng Việt**

- Given: Hệ thống đang sử dụng Tiếng Việt.
- When: User truy cập các chức năng chính.
- Then: Các thành phần giao diện thuộc phạm vi hỗ trợ hiển thị bằng Tiếng Việt.

**AC2 – Giao diện Tiếng Anh**

- Given: Hệ thống đang sử dụng Tiếng Anh.
- When: User truy cập các chức năng chính.
- Then: Các thành phần giao diện thuộc phạm vi hỗ trợ hiển thị bằng Tiếng Anh.

**AC3 – Nhất quán ngôn ngữ**

- Given: Một ngôn ngữ đã được áp dụng.
- When: User di chuyển giữa các Module.
- Then: Giao diện phải tiếp tục sử dụng ngôn ngữ tương ứng.

**AC4 – Không ảnh hưởng dữ liệu**

- Given: User thay đổi ngôn ngữ giao diện.
- When: Hệ thống cập nhật ngôn ngữ.
- Then: Dữ liệu Ticket, User, Report và các dữ liệu nghiệp vụ khác không bị thay đổi.

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

**AC1 – Desktop**

- Given: User truy cập UniSupport trên Desktop.
- When: User sử dụng một chức năng nằm trong In-Scope.
- Then: Giao diện phải hiển thị và cho phép thực hiện chức năng tương ứng.

**AC2 – Mobile**

- Given: User truy cập UniSupport trên Mobile.
- When: User sử dụng một chức năng nằm trong In-Scope.
- Then: Giao diện phải hiển thị và cho phép thực hiện chức năng tương ứng.

**AC3 – Responsive Layout**

- Given: Kích thước màn hình thay đổi.
- When: Giao diện được render lại.
- Then: Nội dung phải điều chỉnh phù hợp và không mất chức năng cốt lõi.

**AC4 – Navigation**

- Given: User đang sử dụng Mobile hoặc Desktop.
- When: User điều hướng giữa các chức năng.
- Then: Các chức năng chính vẫn có thể truy cập được.

**AC5 – Business Logic**

- Given: Cùng một User và cùng một chức năng.
- When: User sử dụng trên Desktop hoặc Mobile.
- Then: Business Rule và Permission phải được áp dụng giống nhau.

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

**AC1 – Consistent Terminology**

- Given: Một thuật ngữ nghiệp vụ được sử dụng ở nhiều Module.
- When: User truy cập các Module khác nhau.
- Then: Thuật ngữ phải được sử dụng nhất quán.

Ví dụ:

- Ticket.
- Category.
- Priority.
- Student.
- Staff.
- Manager.
- Administrator.

**AC2 – Consistent Ticket Status**

- Given: Ticket được hiển thị ở nhiều màn hình.
- When: User xem trạng thái Ticket.
- Then: Cách gọi trạng thái phải nhất quán với:
  - Mới tạo.
  - Đang xử lý.
  - Cần bổ sung.
  - Hoàn thành.

**AC3 – Form Validation Feedback**

- Given: User nhập thiếu hoặc nhập dữ liệu không hợp lệ.
- When: User thực hiện Submit.
- Then: Hệ thống phải cung cấp thông tin để User nhận biết dữ liệu cần bổ sung hoặc chỉnh sửa.

**AC4 – Success Feedback**

- Given: Một thao tác được thực hiện thành công.
- When: Hệ thống hoàn tất xử lý.
- Then: User phải nhận được phản hồi thể hiện kết quả thao tác.

**AC5 – Permission-aware UI**

- Given: User có một Role cụ thể.
- When: User truy cập hệ thống.
- Then: Các chức năng được cung cấp phải phù hợp với Permission của Role đó.

**AC6 – Cross-module Consistency**

- Given: Cùng một loại dữ liệu hoặc thao tác xuất hiện ở nhiều Module.
- When: User sử dụng các Module khác nhau.
- Then: Cách thể hiện và thuật ngữ phải nhất quán.

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