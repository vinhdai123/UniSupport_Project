# MODULE M01: SECURITY, AUTHENTICATION & RBAC

Bản đặc tả phục vụ kế hoạch Mô phỏng. Tham số mật khẩu, thời hạn, tệp, số dòng và chính sách quyền theo Business Rules/NFR là đề xuất cần PM/BA xác nhận trước baseline nghiệm thu.


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
- **FR-AUTH-01/AC-01:** Kiểm tra đăng nhập thành công (Kiểm tra BR-AUTH-02)
  - Given: Người dùng ở màn hình đăng nhập và có tài khoản hợp lệ.
  - When: Người dùng nhập đúng thông tin định danh cùng mật khẩu và chọn đăng nhập.
  - Then: Hệ thống xác thực thành công và mở trang được phép theo vai trò hiện tại, đối chiếu FR-AUTH-03.
- **FR-AUTH-01/AC-02:** Kiểm tra đăng nhập thất bại (Kiểm tra E-AUTH-02)
  - Given: Người dùng ở màn hình đăng nhập.
  - When: Người dùng nhập sai mật khẩu.
  - Then: Hệ thống từ chối đăng nhập và hiển thị thông báo lỗi.

- **FR-AUTH-01/AC-03:** Thiếu định danh hoặc mật khẩu (BR-AUTH-01, E-AUTH-01)
  - Given: Người dùng ở form đăng nhập.
  - When: Lần lượt bỏ trống định danh, mật khẩu và cả hai rồi gửi.
  - Then: Hệ thống chỉ rõ trường bắt buộc, từ chối đăng nhập và không tạo phiên.

### Tình huống ngoại lệ
- Thử định danh chỉ có khoảng trắng và đăng nhập liên tiếp bằng hai vai trò, kiểm trường bắt buộc và quyền theo FR-AUTH-03.

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
- **FR-AUTH-02/AC-02:** Mật khẩu mới không đạt chuẩn (Kiểm tra BR-AUTH-03)
  - Given: Người dùng ở bước nhập mật khẩu mới.
  - When: Người dùng nhập mật khẩu quá ngắn hoặc thiếu ký tự bảo mật.
  - Then: Hệ thống báo lỗi và yêu cầu nhập lại theo đúng chính sách.

- **FR-AUTH-02/AC-03:** Tài khoản không tồn tại (E-AUTH-03)
  - Given: Người dùng chưa đăng nhập.
  - When: Yêu cầu đặt lại mật khẩu cho định danh không tồn tại.
  - Then: Hệ thống hiển thị phản hồi chung, không tiết lộ sự tồn tại của tài khoản và không tạo thay đổi mật khẩu.
- **FR-AUTH-02/AC-04:** Xác minh thất bại hoặc hết hạn (BR-AUTH-04, E-AUTH-04)
  - Given: Có yêu cầu đặt lại mật khẩu với cơ chế xác minh và thời hạn đã xác nhận.
  - When: Gửi bằng chứng xác minh sai, sau đó thử bằng chứng đã hết hạn.
  - Then: Cả hai trường hợp đều bị từ chối ở API, mật khẩu cũ giữ nguyên và người dùng được hướng dẫn thực hiện lại.

### Tình huống ngoại lệ
- Thử bằng chứng xác minh ngay trước và sau thời hạn đã xác nhận, sau đó thử dùng lại sau một lần đổi thành công.

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
- **FR-AUTH-03/AC-02:** Ngăn chặn truy cập trái phép (Kiểm tra BR-AUTH-05) (Kiểm tra E-AUTH-05)
  - Given: Người dùng có vai trò Student.
  - When: Người dùng cố tình truy cập vào đường dẫn chức năng của Administrator.
  - Then: Giao diện và API đều từ chối truy cập, không trả dữ liệu hoặc thực hiện chức năng quản trị.

- **FR-AUTH-03/AC-03:** Thiếu vai trò hợp lệ (BR-AUTH-05, BR-AUTH-06)
  - Given: Tài khoản đăng nhập không có vai trò hợp lệ.
  - When: Mở chức năng nghiệp vụ và gọi trực tiếp API tương ứng.
  - Then: Hệ thống từ chối truy cập, không trả dữ liệu và không thay đổi dữ liệu nghiệp vụ.

### Tình huống ngoại lệ
- Tài khoản bị gỡ vai trò giữa hai lần gọi API phải bị kiểm quyền lại, không dựa riêng vào menu đang mở.

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

> Phạm vi dữ liệu của từng vai trò và quyền khi Ticket chuyển phòng đang chờ xác nhận tại [OQ-05](../../08-project/open-questions.md#phạm-vi-quyền-và-báo-cáo-oq-05).

### Quy tắc nghiệp vụ
- BR-AUTH-07: Quyền truy cập tệp đính kèm phải nhất quán hoàn toàn với quyền truy cập dữ liệu liên quan.
- BR-AUTH-08: Việc có quyền sử dụng một chức năng không đồng nghĩa với việc được phép xem toàn bộ dữ liệu của chức năng đó.

### Luồng rẽ nhánh và lỗi
- E-AUTH-06: Nếu dữ liệu nằm ngoài phạm vi phân quyền, hệ thống từ chối yêu cầu và không hiển thị nội dung.

### Tiêu chí nghiệm thu
- **FR-AUTH-04/AC-01:** Hiển thị dữ liệu đúng phạm vi (Kiểm tra BR-AUTH-08)
  - Given: Có Staff IT và Staff Đào tạo được cấp phạm vi của từng phòng, cùng Ticket đã chuyển phòng nhưng giữ danh mục gốc trong bộ dữ liệu TS-011.
  - When: Hai Staff tải danh sách không lọc danh mục. Đối chiếu bản ghi trả về ở giao diện và API.
  - Then: Từng tài khoản chỉ nhận các bản ghi thuộc phạm vi được cấp. Tập mã mong đợi cho Ticket đã chuyển lấy theo Permission Matrix được xác nhận tại OQ-05. TS-011 ghi riêng kết quả của hai tài khoản.
- **FR-AUTH-04/AC-02:** Chặn truy cập tệp đính kèm trái phép (Kiểm tra BR-AUTH-07) (Kiểm tra E-AUTH-06)
  - Given: Sinh viên A.
  - When: Sinh viên A cố tình truy cập vào liên kết tải tệp đính kèm từ một yêu cầu của Sinh viên B.
  - Then: Hệ thống từ chối tải tệp và hiển thị thông báo lỗi truy cập.


### Tình huống ngoại lệ
- Thay Ticket ID và attachment ID trong URL bằng tài nguyên của người khác, kiểm API trả dữ liệu theo phạm vi.

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
- BR-AUTH-09: Việc ghi nhật ký hệ thống diễn ra độc lập và giữ nguyên kết quả thao tác gốc, thời gian phản hồi tuân theo NFR-PERF-01 đã xác nhận.

### Luồng rẽ nhánh và lỗi
- E-AUTH-07: Nếu quá trình lưu bản ghi nhật ký gặp sự cố kỹ thuật, hệ thống vẫn đảm bảo hoàn thành giao dịch chính của người dùng mà không gây lỗi ứng dụng.

### Tiêu chí nghiệm thu
- **FR-AUTH-05/AC-01:** Ghi nhận thao tác thành công
  - Given: Quản trị viên thay đổi vai trò của một tài khoản.
  - When: Thao tác cập nhật thành công.
  - Then: Hệ thống lưu lại một bản ghi chứa ID của quản trị viên, hành động thay đổi quyền và thời gian thực hiện.

- **FR-AUTH-05/AC-02:** Lỗi hệ thống ghi nhật ký (BR-AUTH-09, E-AUTH-07)
  - Given: Môi trường kiểm thử cô lập mô phỏng lỗi nơi lưu nhật ký.
  - When: Thực hiện một thao tác hợp lệ cần ghi log.
  - Then: Giao dịch chính hoàn tất đúng một lần, lỗi log được ghi nhận cho vận hành và thời gian phản hồi được đối chiếu NFR-PERF-01 đã xác nhận.

### Tình huống ngoại lệ
- Mô phỏng nơi lưu log mất kết nối trong khi thao tác chính thành công, đối chiếu giao dịch và việc ghi nhận sự cố.

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
- BR-AUTH-10: Khi server xác nhận đăng xuất thành công, phiên cũ bị vô hiệu hóa và không thể dùng lại. Khi mất mạng, client xóa thông tin cục bộ theo E-AUTH-08, trạng thái phiên server được kiểm khi có kết nối.

### Luồng rẽ nhánh và lỗi
- E-AUTH-08: Nếu mất kết nối mạng khi đang xử lý đăng xuất, hệ thống vẫn xóa thông tin xác thực trên trình duyệt để đảm bảo an toàn tại máy khách.

### Tiêu chí nghiệm thu
- **FR-AUTH-06/AC-01:** Đăng xuất thành công
  - Given: Người dùng đang đăng nhập hợp lệ.
  - When: Người dùng chọn chức năng đăng xuất.
  - Then: Hệ thống kết thúc phiên làm việc và hiển thị lại màn hình đăng nhập.

- **FR-AUTH-06/AC-02:** Không tái sử dụng phiên đã kết thúc (BR-AUTH-10)
  - Given: Server đã xác nhận đăng xuất thành công.
  - When: Dùng thông tin xác thực cũ gọi lại API được bảo vệ.
  - Then: Hệ thống từ chối truy cập và không trả dữ liệu.
- **FR-AUTH-06/AC-03:** Mất mạng khi đăng xuất (E-AUTH-08)
  - Given: Người dùng có phiên hợp lệ và môi trường kiểm thử ngắt mạng.
  - When: Chọn đăng xuất và mở lại trang trên cùng trình duyệt.
  - Then: Thông tin xác thực cục bộ bị xóa, trang yêu cầu đăng nhập lại. QA ghi riêng trạng thái kết thúc phiên phía server để kiểm khi có kết nối.

### Tình huống ngoại lệ
- Mất mạng trước khi server nhận đăng xuất và mở lại trang ở cùng trình duyệt, đối chiếu xóa phiên cục bộ với trạng thái server.

---

## FR-AUTH-07 – Quản trị tài khoản và vai trò

### Mô tả
Cho phép tài khoản quản trị được ủy quyền tạo, cập nhật, khóa hoặc mở lại tài khoản do trường cấp và gán vai trò trong phạm vi quản trị.

### Actor
Administrator.

### Mức độ ưu tiên
Cao.

### Điều kiện tiên quyết
Admin đã đăng nhập, danh sách vai trò và phạm vi quản trị đã xác nhận.

### Luồng chính
1. Mở danh sách tài khoản, tìm tài khoản hoặc chọn tạo mới.
2. Nhập định danh được trường cấp, thông tin tài khoản và vai trò hợp lệ.
3. Lưu cấu hình, kiểm quyền tại server và ghi nhật ký.
4. Tài khoản được cập nhật và dùng quyền tương ứng khi đăng nhập hoặc tải lại theo chính sách phiên.

### Quy tắc nghiệp vụ
- BR-AUTH-11: Định danh tài khoản là duy nhất, quản trị không được tự cấp quyền ngoài phạm vi được ủy quyền.
- BR-AUTH-12: Tài khoản bị khóa không được đăng nhập mới. Hiệu lực với phiên đang hoạt động cần được xác nhận cùng chính sách phiên.

### Luồng rẽ nhánh và lỗi
- E-AUTH-09: Thiếu dữ liệu hoặc định danh trùng thì từ chối lưu, giữ cấu hình hiện tại.
- E-AUTH-10: API từ chối thao tác của tài khoản thiếu quyền quản trị hoặc yêu cầu gán quyền vượt phạm vi được ủy quyền.

### Tiêu chí nghiệm thu
- **FR-AUTH-07/AC-01:** Tạo tài khoản và áp dụng vai trò
  - Given: Admin có quyền, chưa có định danh SV-MOCK-03.
  - When: Tạo tài khoản giả lập với vai trò Student rồi đăng nhập bằng tài khoản đó.
  - Then: Tài khoản vào được chức năng Student và bị chặn chức năng Admin.
- **FR-AUTH-07/AC-02:** Chặn định danh trùng và dữ liệu thiếu (BR-AUTH-11, E-AUTH-09)
  - Given: Đã có tài khoản SV-MOCK-01.
  - When: Tạo lại định danh này, sau đó thử dữ liệu bắt buộc rỗng.
  - Then: Các yêu cầu bị từ chối, không tạo bản ghi trùng hoặc dở dang.
- **FR-AUTH-07/AC-03:** Khóa tài khoản và chặn cấp quyền trái ủy quyền (BR-AUTH-11, BR-AUTH-12, E-AUTH-10)
  - Given: Có tài khoản Student đang hoạt động, người dùng không có quyền quản trị và Admin có phạm vi cấp quyền giới hạn theo ma trận quyền áp dụng.
  - When: Thử riêng ba ca. Admin khóa tài khoản rồi thử đăng nhập mới. Người không có quyền quản trị yêu cầu đổi vai trò. Admin có quyền quản trị thử gán một quyền ngoài phạm vi được ủy quyền.
  - Then: Đăng nhập mới bị từ chối. Cả hai yêu cầu đổi quyền trái phép bị từ chối tại API, quyền của tài khoản đích giữ nguyên.

### Tình huống ngoại lệ
- Hai Admin đồng thời sửa cùng tài khoản, kiểm phát hiện phiên bản cũ theo cơ chế cập nhật đã xác nhận.

---

# 2. Yêu cầu phi chức năng / Ràng buộc

Áp dụng [NFR-GLOBAL-01](../../05-non-functional-requirements/README.md) về dữ liệu giả lập và các NFR toàn cục. Mã NFR-AUTH-01 trước đây được hợp nhất vào NFR-GLOBAL-01 để duy trì một nơi gốc.

---
