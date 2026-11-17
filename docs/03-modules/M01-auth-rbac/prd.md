# MODULE M01: SECURITY, AUTHENTICATION & RBAC

# 1. Đặc tả yêu cầu chức năng

## FR-AUTH-01 – Đăng nhập hệ thống

### Mô tả
Cho phép người dùng xác thực danh tính bằng tài khoản hệ thống để truy cập các chức năng và dữ liệu được cấp quyền trong UniSupport.

### Actor
Tất cả người dùng.

### Mức độ ưu tiên
Cao.

### Điều kiện tiên quyết
Người dùng đã có tài khoản hợp lệ trên hệ thống.

### Luồng chính
1. Người dùng truy cập màn hình đăng nhập.
2. Người dùng nhập thông tin định danh tài khoản và mật khẩu.
3. Hệ thống kiểm tra các thông tin bắt buộc.
4. Hệ thống tìm tài khoản tương ứng và kiểm tra thông tin xác thực.
5. Khi thông tin hợp lệ, hệ thống xác định vai trò của người dùng và áp dụng quyền chức năng, quyền dữ liệu tương ứng.
6. Hệ thống chuyển hướng người dùng vào trang chủ phù hợp với vai trò.

### Quy tắc nghiệp vụ
- BR-AUTH-01: Thông tin định danh và mật khẩu là bắt buộc, không được để trống.
- BR-AUTH-02: Quyền truy cập sau khi đăng nhập phải tuân thủ chính xác theo vai trò của tài khoản.

### Luồng rẽ nhánh và lỗi
- E-AUTH-01: Nếu người dùng thiếu thông tin bắt buộc, hệ thống không cho phép gửi yêu cầu và hiển thị cảnh báo.
- E-AUTH-02: Nếu thông tin không hợp lệ, hệ thống từ chối truy cập và hiển thị thông báo lỗi chung để bảo mật thông tin tài khoản.

### Tiêu chí nghiệm thu
- **FR-AUTH-01/AC-01:** Kiểm tra đăng nhập thành công
  - Given: Người dùng ở màn hình đăng nhập và có tài khoản hợp lệ.
  - When: Người dùng nhập đúng thông tin định danh cùng mật khẩu và chọn đăng nhập.
  - Then: Hệ thống xác thực thành công và chuyển người dùng vào bên trong hệ thống.
- **FR-AUTH-01/AC-02:** Kiểm tra đăng nhập thất bại
  - Given: Người dùng ở màn hình đăng nhập.
  - When: Người dùng nhập sai mật khẩu.
  - Then: Hệ thống từ chối đăng nhập và hiển thị thông báo lỗi.

### Tình huống ngoại lệ
- Người dùng đăng nhập thành công nhưng tài khoản vừa bị vô hiệu hóa trên cơ sở dữ liệu. Hệ thống sẽ ngay lập tức hủy phiên làm việc và yêu cầu đăng nhập lại.

---

## FR-AUTH-02 – Đặt lại mật khẩu

### Mô tả
Cho phép người dùng đặt lại mật khẩu khi không thể sử dụng mật khẩu hiện tại thông qua quy trình xác minh an toàn.

### Actor
Tất cả người dùng.

### Mức độ ưu tiên
Cao.

### Điều kiện tiên quyết
Tài khoản của người dùng tồn tại trên hệ thống.

### Luồng chính
1. Người dùng chọn chức năng đặt lại mật khẩu trên màn hình đăng nhập.
2. Người dùng cung cấp thông tin xác định tài khoản.
3. Hệ thống thực hiện quy trình xác minh người dùng qua email hoặc mã xác thực.
4. Sau khi xác minh thành công, người dùng nhập mật khẩu mới.
5. Hệ thống kiểm tra tính hợp lệ của mật khẩu mới.
6. Hệ thống cập nhật mật khẩu, thông báo thành công và chuyển về màn hình đăng nhập.

> Quy trình xác minh người dùng cụ thể: **TBD – Pending Confirmation**.

### Quy tắc nghiệp vụ
- BR-AUTH-03: Mật khẩu mới phải đáp ứng chính sách bảo mật mật khẩu của hệ thống.
- BR-AUTH-04: Quá trình xác minh người dùng có giới hạn thời gian hiệu lực.

### Luồng rẽ nhánh và lỗi
- E-AUTH-03: Nếu tài khoản không tồn tại, hệ thống không tiếp tục quy trình để tránh lộ lọt thông tin.
- E-AUTH-04: Nếu xác minh người dùng không thành công, hệ thống không cho phép thay đổi mật khẩu.

### Tiêu chí nghiệm thu
- **FR-AUTH-02/AC-01:** Đặt lại mật khẩu thành công
  - Given: Người dùng đã vượt qua bước xác minh danh tính.
  - When: Người dùng nhập mật khẩu mới hợp lệ và xác nhận lưu.
  - Then: Hệ thống cập nhật mật khẩu mới và người dùng có thể sử dụng ngay lập tức.
- **FR-AUTH-02/AC-02:** Mật khẩu mới không đạt chuẩn
  - Given: Người dùng ở bước nhập mật khẩu mới.
  - When: Người dùng nhập mật khẩu quá ngắn hoặc thiếu ký tự bảo mật.
  - Then: Hệ thống báo lỗi và yêu cầu nhập lại theo đúng chính sách.

### Tình huống ngoại lệ
- Người dùng yêu cầu gửi mã xác minh quá nhiều lần trong thời gian ngắn. Hệ thống sẽ tạm khóa chức năng này đối với tài khoản đó trong một khoảng thời gian nhất định.

---

## FR-AUTH-03 – Phân quyền chức năng theo vai trò

### Mô tả
Kiểm soát quyền truy cập và thao tác của người dùng dựa trên vai trò được cấu hình, đảm bảo người dùng chỉ sử dụng các chức năng phù hợp với phạm vi quyền hạn.

### Actor
Hệ thống.

### Mức độ ưu tiên
Cao.

### Điều kiện tiên quyết
Người dùng đã đăng nhập thành công và được gán một vai trò cụ thể.

### Luồng chính
1. Người dùng yêu cầu truy cập một chức năng hoặc thực hiện một thao tác.
2. Hệ thống xác định chức năng được yêu cầu.
3. Hệ thống kiểm tra vai trò hiện tại của người dùng có quyền sử dụng chức năng này hay không.
4. Nếu có quyền, hệ thống cho phép truy cập hoặc thực hiện thao tác.

> Hệ thống hỗ trợ 04 vai trò: Student, Staff, Manager, Administrator. Permission Matrix chi tiết được quy định tại các module khác.

### Quy tắc nghiệp vụ
- BR-AUTH-05: Việc kiểm tra quyền phải được thực hiện ở cả giao diện người dùng và lớp xử lý logic bên dưới.
- BR-AUTH-06: Người dùng không có vai trò hợp lệ sẽ không được tự động cấp bất kỳ quyền nghiệp vụ nào.

### Luồng rẽ nhánh và lỗi
- E-AUTH-05: Nếu người dùng không có quyền truy cập, hệ thống từ chối thao tác và không hiển thị chức năng được yêu cầu.

### Tiêu chí nghiệm thu
- **FR-AUTH-03/AC-01:** Cho phép truy cập hợp lệ
  - Given: Người dùng có vai trò Student.
  - When: Người dùng truy cập chức năng tạo yêu cầu hỗ trợ mới.
  - Then: Hệ thống hiển thị màn hình tạo yêu cầu bình thường.
- **FR-AUTH-03/AC-02:** Ngăn chặn truy cập trái phép
  - Given: Người dùng có vai trò Student.
  - When: Người dùng cố tình truy cập vào đường dẫn chức năng của Administrator.
  - Then: Hệ thống từ chối truy cập và chuyển hướng đến trang thông báo lỗi phân quyền.

### Tình huống ngoại lệ
- Quản trị viên thay đổi quyền của một nhân sự khi nhân sự đó đang sử dụng hệ thống. Lần thao tác tiếp theo của nhân sự đó sẽ áp dụng ngay bộ quyền mới.

---

## FR-AUTH-04 – Kiểm soát quyền truy cập dữ liệu và tệp đính kèm

### Mô tả
Đảm bảo người dùng chỉ được xem hoặc thao tác trên các bản ghi dữ liệu và tệp đính kèm nằm trong phạm vi được cấp quyền của mình.

### Actor
Hệ thống.

### Mức độ ưu tiên
Cao.

### Điều kiện tiên quyết
Người dùng đã vượt qua bước kiểm tra quyền chức năng tại FR-AUTH-03.

### Luồng chính
1. Người dùng yêu cầu xem dữ liệu hoặc tải tệp đính kèm.
2. Hệ thống xác định phạm vi dữ liệu mà vai trò của người dùng được phép truy cập.
3. Hệ thống đối chiếu dữ liệu được yêu cầu với phạm vi cho phép.
4. Nếu hợp lệ, hệ thống trả về dữ liệu hoặc tệp đính kèm tương ứng.

> Data Scope cụ thể của từng Role: **TBD – Pending Confirmation**.

### Quy tắc nghiệp vụ
- BR-AUTH-07: Quyền truy cập tệp đính kèm phải nhất quán hoàn toàn với quyền truy cập dữ liệu liên quan.
- BR-AUTH-08: Việc có quyền sử dụng một chức năng không đồng nghĩa với việc được phép xem toàn bộ dữ liệu của chức năng đó.

### Luồng rẽ nhánh và lỗi
- E-AUTH-06: Nếu dữ liệu nằm ngoài phạm vi phân quyền, hệ thống từ chối yêu cầu và không hiển thị nội dung.

### Tiêu chí nghiệm thu
- **FR-AUTH-04/AC-01:** Hiển thị dữ liệu đúng phạm vi
  - Given: Nhân viên thuộc phòng Công nghệ thông tin.
  - When: Nhân viên xem danh sách các yêu cầu hỗ trợ.
  - Then: Hệ thống chỉ hiển thị các yêu cầu thuộc danh mục Công nghệ thông tin.
- **FR-AUTH-04/AC-02:** Chặn truy cập tệp đính kèm trái phép
  - Given: Sinh viên A.
  - When: Sinh viên A cố tình truy cập vào liên kết tải tệp đính kèm từ một yêu cầu của Sinh viên B.
  - Then: Hệ thống từ chối tải tệp và hiển thị thông báo lỗi truy cập.

### Tình huống ngoại lệ
- Một yêu cầu hỗ trợ vừa được chuyển giao sang bộ phận khác trong lúc nhân viên bộ phận cũ đang xem chi tiết yêu cầu đó. Khi nhân viên này tải lại trang, hệ thống sẽ ẩn dữ liệu này đi.

---

## FR-AUTH-05 – Ghi nhận nhật ký thao tác

### Mô tả
Tự động ghi nhận các thao tác quan trọng vào hệ thống để hỗ trợ quá trình theo dõi, kiểm tra và truy vết hoạt động.

### Actor
Hệ thống.

### Mức độ ưu tiên
Trung bình.

### Điều kiện tiên quyết
Người dùng vừa thực hiện thành công một thao tác làm thay đổi dữ liệu hoặc trạng thái trên hệ thống.

### Luồng chính
1. Hệ thống xác định thao tác người dùng vừa thực hiện có thuộc nhóm cần ghi nhật ký hay không.
2. Nếu thuộc nhóm cần ghi nhận, hệ thống thu thập thông tin bao gồm người thực hiện, thao tác, đối tượng bị tác động và thời điểm.
3. Hệ thống tạo bản ghi nhật ký và lưu trữ an toàn vào cơ sở dữ liệu.

> Danh sách cụ thể các thao tác cần ghi nhật ký: **TBD – Pending Confirmation**.

### Quy tắc nghiệp vụ
- BR-AUTH-09: Việc ghi nhật ký hệ thống diễn ra độc lập và không được làm thay đổi kết quả hay tốc độ xử lý của thao tác gốc.

### Luồng rẽ nhánh và lỗi
- E-AUTH-07: Nếu quá trình lưu bản ghi nhật ký gặp sự cố kỹ thuật, hệ thống vẫn đảm bảo hoàn thành giao dịch chính của người dùng mà không gây lỗi ứng dụng.

### Tiêu chí nghiệm thu
- **FR-AUTH-05/AC-01:** Ghi nhận thao tác thành công
  - Given: Quản trị viên thay đổi vai trò của một tài khoản.
  - When: Thao tác cập nhật thành công.
  - Then: Hệ thống lưu lại một bản ghi chứa ID của quản trị viên, hành động thay đổi quyền và thời gian thực hiện.

### Tình huống ngoại lệ
- Nếu hành động chính của người dùng bị hoàn tác do lỗi nghiệp vụ ở bước cuối cùng, hệ thống sẽ không ghi nhận bản ghi nhật ký báo thành công cho thao tác đó.

---

## FR-AUTH-06 – Đăng xuất hệ thống

### Mô tả
Cho phép người dùng chủ động kết thúc phiên làm việc để đảm bảo an toàn cho tài khoản và dữ liệu.

### Actor
Tất cả người dùng.

### Mức độ ưu tiên
Cao.

### Điều kiện tiên quyết
Người dùng đang ở trạng thái đăng nhập trên hệ thống.

### Luồng chính
1. Người dùng chọn chức năng đăng xuất trên giao diện.
2. Hệ thống thu hồi và xóa bỏ phiên làm việc hiện tại của người dùng.
3. Hệ thống chuyển hướng người dùng về màn hình đăng nhập.

### Quy tắc nghiệp vụ
- BR-AUTH-10: Các thông tin xác thực cũ sẽ bị vô hiệu hóa hoàn toàn và không thể sử dụng lại sau khi đăng xuất.

### Luồng rẽ nhánh và lỗi
- E-AUTH-08: Nếu mất kết nối mạng khi đang xử lý đăng xuất, hệ thống vẫn xóa thông tin xác thực trên trình duyệt để đảm bảo an toàn tại máy khách.

### Tiêu chí nghiệm thu
- **FR-AUTH-06/AC-01:** Đăng xuất thành công
  - Given: Người dùng đang đăng nhập hợp lệ.
  - When: Người dùng chọn chức năng đăng xuất.
  - Then: Hệ thống kết thúc phiên làm việc và hiển thị lại màn hình đăng nhập.

### Tình huống ngoại lệ
- Dù người dùng không chủ động đăng xuất, hệ thống sẽ tự động kết thúc phiên làm việc nếu trình duyệt không có bất kỳ tương tác nào vượt quá khoảng thời gian giới hạn an toàn.

---

# 2. Yêu cầu phi chức năng / Ràng buộc

## NFR-AUTH-01 – Dữ liệu phát triển và kiểm thử

### Yêu cầu
Trong suốt quá trình phát triển và kiểm thử, hệ thống phải sử dụng hoàn toàn dữ liệu giả lập theo phạm vi đã thống nhất. Tuyệt đối không sử dụng dữ liệu thật của Aurora University khi chưa được cho phép.

### Tiêu chí nghiệm thu
- Môi trường phát triển và kiểm thử chỉ chứa dữ liệu giả lập.
- Dữ liệu giả lập phải đa dạng và đủ trường hợp để kiểm thử toàn vẹn các chức năng phân quyền.
- Không có bất kỳ dữ liệu thật nào tồn tại trên các môi trường này.