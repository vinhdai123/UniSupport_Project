# MODULE M01: SECURITY, AUTHENTICATION & RBAC

# 1. Đặc tả yêu cầu chức năng

## FR-AUTH-01 – Đăng nhập hệ thống

### User Story

Là một người dùng UniSupport, tôi muốn đăng nhập bằng tài khoản hệ thống để hệ thống xác định danh tính và vai trò của tôi, từ đó cho phép tôi truy cập các chức năng và dữ liệu được cấp quyền.

### Input

- Thông tin định danh tài khoản UniSupport.
- Mật khẩu.

> Định dạng cụ thể của thông tin định danh tài khoản: **TBD – Pending Confirmation**.

### Xử lý

1. Người dùng truy cập màn hình đăng nhập.
2. Người dùng nhập thông tin định danh tài khoản và mật khẩu.
3. Hệ thống kiểm tra các thông tin bắt buộc.
4. Hệ thống tìm tài khoản tương ứng trong hệ thống UniSupport.
5. Hệ thống kiểm tra thông tin xác thực của tài khoản.
6. Nếu thông tin không hợp lệ:
   - Không cho phép đăng nhập.
   - Hiển thị thông báo đăng nhập không thành công.
7. Nếu thông tin hợp lệ:
   - Xác định người dùng hiện tại.
   - Xác định Role của tài khoản.
   - Áp dụng quyền chức năng và quyền dữ liệu tương ứng.
8. Hệ thống cho phép người dùng truy cập UniSupport.

### Output

Khi đăng nhập thành công:

- Người dùng được xác thực.
- Role của người dùng được xác định.
- Quyền chức năng và dữ liệu tương ứng được áp dụng.
- Người dùng được chuyển vào hệ thống.

Khi đăng nhập không thành công:

- Người dùng không được truy cập hệ thống.
- Hệ thống hiển thị thông báo lỗi.

### Acceptance Criteria

- [ ] Người dùng có tài khoản UniSupport hợp lệ có thể đăng nhập.
- [ ] Không cho phép gửi Login khi thiếu thông tin bắt buộc.
- [ ] Thông tin đăng nhập không hợp lệ không được phép truy cập hệ thống.
- [ ] Sau khi đăng nhập thành công, hệ thống xác định đúng người dùng.
- [ ] Sau khi đăng nhập thành công, hệ thống xác định đúng Role.
- [ ] Quyền truy cập sau Login phải tuân theo Role của tài khoản.

---

## FR-AUTH-02 – Đặt lại mật khẩu

### User Story

Là một người dùng UniSupport, tôi muốn đặt lại mật khẩu khi không thể sử dụng mật khẩu hiện tại để có thể tiếp tục truy cập hệ thống bằng tài khoản của mình.

### Input

- Thông tin xác định tài khoản.
- Thông tin cần thiết để xác minh người dùng.
- Mật khẩu mới sau khi xác minh thành công.

> Quy trình xác minh người dùng và Password Policy cụ thể: **TBD – Pending Confirmation**.

### Xử lý

1. Người dùng chọn chức năng đặt lại mật khẩu.
2. Người dùng cung cấp thông tin xác định tài khoản.
3. Hệ thống kiểm tra tài khoản có tồn tại hay không.
4. Nếu không xác định được tài khoản:
   - Không tiếp tục quy trình Reset Password.
5. Nếu tài khoản tồn tại:
   - Hệ thống thực hiện quy trình xác minh người dùng.
6. Nếu xác minh không thành công:
   - Không cho phép thay đổi mật khẩu.
7. Nếu xác minh thành công:
   - Người dùng nhập mật khẩu mới.
8. Hệ thống kiểm tra mật khẩu mới theo Password Policy đã được xác nhận.
9. Nếu hợp lệ:
   - Hệ thống cập nhật mật khẩu mới.
10. Hệ thống thông báo Reset Password thành công.
11. Người dùng có thể sử dụng mật khẩu mới cho lần đăng nhập tiếp theo.

### Output

Khi thành công:

- Mật khẩu mới được ghi nhận.
- Người dùng có thể sử dụng mật khẩu mới để đăng nhập.

Khi không thành công:

- Mật khẩu hiện tại không bị thay đổi.
- Hệ thống hiển thị thông báo lỗi.

### Acceptance Criteria

- [ ] Hệ thống cung cấp chức năng đặt lại mật khẩu.
- [ ] Chỉ tài khoản tồn tại mới được tiếp tục quy trình Reset Password.
- [ ] Xác minh người dùng không thành công không được thay đổi mật khẩu.
- [ ] Mật khẩu mới phải đáp ứng Password Policy sau khi Policy được xác nhận.
- [ ] Sau khi Reset Password thành công, người dùng có thể đăng nhập bằng mật khẩu mới.

---

## FR-AUTH-03 – Xác định vai trò người dùng

### User Story

Là hệ thống UniSupport, tôi cần xác định vai trò của từng người dùng để áp dụng đúng quyền chức năng và quyền dữ liệu sau khi người dùng được xác thực.

### Roles

Hệ thống hỗ trợ 04 vai trò:

1. `Student`
2. `Staff`
3. `Manager`
4. `Administrator`

### Input

- User được xác thực.
- Role đã được cấu hình cho User.

### Xử lý

1. Sau khi người dùng đăng nhập thành công, hệ thống xác định User hiện tại.
2. Hệ thống lấy Role được liên kết với tài khoản.
3. Hệ thống kiểm tra Role có thuộc danh sách Role được hỗ trợ hay không.
4. Nếu Role hợp lệ:
   - Role được sử dụng trong quá trình kiểm tra quyền chức năng.
   - Role được sử dụng trong quá trình kiểm tra quyền dữ liệu.
5. Nếu Role không hợp lệ hoặc chưa được xác định:
   - Không cấp quyền truy cập vào các chức năng nghiệp vụ tương ứng.

### Output

- Role hiện tại của người dùng.
- Thông tin Role được sử dụng cho Authorization.

### Acceptance Criteria

- [ ] Hệ thống hỗ trợ đúng 04 Role: Student, Staff, Manager và Administrator.
- [ ] Mỗi người dùng sau khi đăng nhập phải được xác định Role.
- [ ] Role hợp lệ được sử dụng để kiểm tra quyền chức năng.
- [ ] Role hợp lệ được sử dụng để kiểm tra quyền dữ liệu.
- [ ] User không có Role hợp lệ không được tự động cấp quyền nghiệp vụ.

> Việc tạo, cập nhật hoặc thay đổi Role thuộc chức năng quản lý tài khoản và vai trò trong Module M04.

---

## FR-AUTH-04 – Phân quyền chức năng theo vai trò

### User Story

Là một người dùng UniSupport, tôi chỉ muốn truy cập và thực hiện các chức năng phù hợp với vai trò của mình để đảm bảo đúng phạm vi sử dụng hệ thống.

### Input

- User ID.
- Role của người dùng.
- Chức năng người dùng yêu cầu truy cập hoặc thực hiện.

### Xử lý

1. Người dùng yêu cầu truy cập một chức năng.
2. Hệ thống xác định User hiện tại.
3. Hệ thống xác định Role của User.
4. Hệ thống xác định chức năng được yêu cầu.
5. Hệ thống kiểm tra Role có quyền sử dụng chức năng hay không.
6. Nếu có quyền:
   - Cho phép người dùng truy cập hoặc thực hiện chức năng.
7. Nếu không có quyền:
   - Từ chối thao tác.
   - Không thực hiện chức năng được yêu cầu.

### Output

- Cho phép truy cập nếu User có Permission phù hợp.
- Từ chối truy cập nếu User không có Permission.

### Acceptance Criteria

- [ ] Student chỉ sử dụng các chức năng được cấp cho Student.
- [ ] Staff chỉ sử dụng các chức năng xử lý được cấp cho Staff.
- [ ] Manager chỉ sử dụng các chức năng quản lý và báo cáo được cấp quyền.
- [ ] Administrator chỉ sử dụng các chức năng quản trị được cấp quyền.
- [ ] Người dùng không thể sử dụng chức năng ngoài Permission của mình.
- [ ] Việc kiểm tra quyền phải được thực hiện trước khi chức năng nghiệp vụ được thực thi.

> Permission Matrix chi tiết được xác định dựa trên Functional Requirements của M02, M03, M04 và M05.

---

## FR-AUTH-05 – Kiểm soát quyền truy cập dữ liệu

### User Story

Là một người dùng UniSupport, tôi chỉ được xem hoặc thao tác trên dữ liệu nằm trong phạm vi được cấp quyền cho tài khoản và vai trò của mình.

### Input

- User ID.
- Role.
- Dữ liệu hoặc tài nguyên được yêu cầu truy cập.
- Loại thao tác người dùng muốn thực hiện.

### Xử lý

1. Người dùng yêu cầu truy cập hoặc thao tác trên dữ liệu.
2. Hệ thống xác định User hiện tại.
3. Hệ thống xác định Role.
4. Hệ thống xác định dữ liệu được yêu cầu.
5. Hệ thống xác định phạm vi dữ liệu User được phép truy cập.
6. Hệ thống kiểm tra dữ liệu yêu cầu có nằm trong phạm vi được cấp hay không.
7. Nếu nằm trong phạm vi:
   - Cho phép xem hoặc thao tác tương ứng.
8. Nếu nằm ngoài phạm vi:
   - Từ chối yêu cầu.
   - Không trả dữ liệu cho người dùng.

### Output

- Dữ liệu được phép truy cập; hoặc
- Yêu cầu truy cập bị từ chối.

### Acceptance Criteria

- [ ] Hệ thống kiểm tra quyền dữ liệu trước khi cung cấp dữ liệu.
- [ ] Người dùng không thể xem dữ liệu ngoài phạm vi được cấp quyền.
- [ ] Người dùng không thể cập nhật dữ liệu ngoài phạm vi được cấp quyền.
- [ ] Có quyền sử dụng chức năng không đồng nghĩa với quyền truy cập toàn bộ dữ liệu của chức năng đó.
- [ ] Việc kiểm soát Data Access phải được áp dụng nhất quán giữa các Module.

> Data Scope cụ thể của từng Role: **TBD – Pending Confirmation**.

---

## FR-AUTH-06 – Kiểm soát quyền truy cập tệp đính kèm

### User Story

Là một người dùng UniSupport, tôi chỉ được truy cập các tệp đính kèm thuộc Ticket hoặc dữ liệu mà mình có quyền truy cập.

### Input

- User ID.
- Role.
- Attachment được yêu cầu truy cập.
- Ticket hoặc Resource liên quan đến Attachment.

### Xử lý

1. Người dùng yêu cầu truy cập Attachment.
2. Hệ thống xác định User hiện tại.
3. Hệ thống xác định Attachment được yêu cầu.
4. Hệ thống xác định Ticket hoặc Resource liên quan đến Attachment.
5. Hệ thống kiểm tra quyền truy cập dữ liệu của User đối với Ticket/Resource đó.
6. Nếu User có quyền:
   - Cho phép truy cập Attachment.
7. Nếu User không có quyền:
   - Từ chối yêu cầu.
   - Không cung cấp nội dung tệp.

### Output

- Attachment được cung cấp cho User có quyền; hoặc
- Access Denied.

### Acceptance Criteria

- [ ] Người dùng có quyền đối với Ticket/Resource có thể truy cập Attachment liên quan.
- [ ] Người dùng không có quyền đối với Ticket/Resource không thể truy cập Attachment.
- [ ] Quyền truy cập Attachment phải nhất quán với quyền truy cập dữ liệu liên quan.
- [ ] Hệ thống phải kiểm tra Authorization trước khi cung cấp Attachment.

---

## FR-AUTH-07 – Ghi nhận thao tác quan trọng

### User Story

Là người quản lý hệ thống, tôi muốn các thao tác quan trọng được ghi nhận để hỗ trợ việc theo dõi, kiểm tra và truy vết hoạt động của UniSupport.

### Input

- Người dùng thực hiện thao tác.
- Thao tác được thực hiện.
- Đối tượng bị tác động.
- Thời điểm thực hiện.

### Xử lý

1. Người dùng thực hiện một thao tác trong hệ thống.
2. Hệ thống xác định thao tác có thuộc nhóm thao tác cần Audit hay không.
3. Nếu thao tác không thuộc nhóm cần Audit:
   - Hệ thống tiếp tục xử lý nghiệp vụ bình thường.
4. Nếu thao tác thuộc nhóm cần Audit:
   - Xác định User thực hiện.
   - Xác định Action.
   - Xác định Target/Object liên quan.
   - Ghi nhận thời điểm thực hiện.
5. Hệ thống tạo Audit Record.
6. Audit Record được lưu lại để phục vụ việc kiểm tra khi cần.

### Output

Audit Record tối thiểu phải có khả năng xác định:

- Actor/User thực hiện.
- Action được thực hiện.
- Target/Object bị tác động.
- Timestamp.

### Acceptance Criteria

- [ ] Các thao tác được xác định là quan trọng phải tạo Audit Record.
- [ ] Audit Record phải liên kết được với User thực hiện thao tác.
- [ ] Audit Record phải xác định được Action.
- [ ] Audit Record phải xác định được đối tượng liên quan.
- [ ] Audit Record phải xác định được thời điểm thao tác.
- [ ] Việc ghi Audit không được làm thay đổi kết quả nghiệp vụ của thao tác gốc.

> Danh sách cụ thể các thao tác cần Audit và nội dung chi tiết Audit Log: **TBD – Pending Confirmation**.

---

# 2. Yêu cầu phi chức năng / Ràng buộc

## NFR-AUTH-01 – Development & Testing Data

### Requirement

Trong quá trình Development và Testing, UniSupport sử dụng dữ liệu giả lập theo phạm vi đã thống nhất.

Không sử dụng dữ liệu thật của Aurora University khi chưa được cho phép.

### Acceptance Criteria

- [ ] Development Environment có dữ liệu giả lập phục vụ phát triển.
- [ ] Testing Environment có dữ liệu giả lập phục vụ kiểm thử.
- [ ] Mock Data phải đủ để kiểm thử các chức năng Authentication và Authorization.
- [ ] Không sử dụng dữ liệu thật của Aurora University nếu chưa được phê duyệt.



Các yêu cầu mới ngoài In-Scope phải được xử lý thông qua Change Request.