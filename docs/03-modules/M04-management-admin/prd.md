# MODULE M04: ADMIN CONFIG (QUẢN TRỊ & CẤU HÌNH)

Bản đặc tả phục vụ kế hoạch Mô phỏng. Tham số mật khẩu, thời hạn, tệp, số dòng và chính sách quyền theo Business Rules/NFR là đề xuất cần PM/BA xác nhận trước baseline nghiệm thu.


# 1. Đặc tả yêu cầu chức năng

## FR-ADM-01 – Quản lý Danh mục yêu cầu (Category Management)

### Mô tả
Cho phép Quản trị viên (Admin) tạo mới, cập nhật và quản lý trạng thái các danh mục (Category) để sinh viên phân loại Ticket khi gửi, đồng thời làm cơ sở cho hệ thống phân luồng.

### Actor
Quản trị viên (Administrator).

### Mức độ ưu tiên
Cao (Critical).

### Điều kiện tiên quyết
Tài khoản đăng nhập có vai trò Administrator.

### Luồng chính
1. Admin truy cập menu "Cấu hình hệ thống" > "Danh mục yêu cầu".
2. Hệ thống hiển thị danh sách các Danh mục hiện có (gồm: Mã danh mục, Tên, Mô tả, Trạng thái Hoạt động/Ngưng hoạt động).
3. Admin chọn "Thêm mới" hoặc bấm vào một danh mục để "Cập nhật".
4. Admin nhập các thông tin bắt buộc (Tên danh mục) và thông tin tùy chọn (Mô tả).
5. Admin chọn trạng thái (Hoạt động/Ngưng hoạt động) và bấm "Lưu".
6. Hệ thống kiểm tra tính hợp lệ của dữ liệu.
7. Hệ thống lưu vào cơ sở dữ liệu và hiển thị danh mục mới trên danh sách.

### Quy tắc nghiệp vụ
- BR-ADM-01: Tên danh mục phải là duy nhất (không phân biệt chữ hoa, chữ thường).
- BR-ADM-02: Không được phép xóa cứng (Hard Delete) danh mục đã có Ticket liên kết. Chỉ được phép chuyển trạng thái sang "Ngưng hoạt động" (Inactive) để bảo toàn dữ liệu lịch sử.
- BR-ADM-03: Các danh mục ở trạng thái "Ngưng hoạt động" sẽ không hiển thị trên Student Portal khi sinh viên tạo Ticket mới.

### Luồng rẽ nhánh và lỗi
- E-ADM-01: Nếu Admin nhập tên danh mục đã tồn tại, hệ thống chặn lưu và báo lỗi: "Tên danh mục đã tồn tại, vui lòng chọn tên khác".
- E-ADM-02: Nếu Admin bỏ trống tên danh mục, hệ thống báo "Trường Tên danh mục là bắt buộc".

### Tiêu chí nghiệm thu
- **FR-ADM-01/AC-01:** Thêm mới danh mục thành công
  - Given: Admin ở form thêm mới Danh mục.
  - When: Admin nhập tên "Hỗ trợ học phí" và lưu.
  - Then: Hệ thống thông báo thành công, danh mục xuất hiện trong danh sách với trạng thái Hoạt động.
- **FR-ADM-01/AC-02:** Chặn trùng lặp tên danh mục (Kiểm tra BR-ADM-01, E-ADM-01)
  - Given: Hệ thống đã có danh mục "Kỹ thuật".
  - When: Admin tạo mới một danh mục tên "Kỹ thuật" (hoặc "kỹ thuật").
  - Then: Hệ thống báo lỗi trùng lặp và không cho phép lưu.
- **FR-ADM-01/AC-03:** Ngưng hoạt động danh mục (Kiểm tra BR-ADM-02, BR-ADM-03)
  - Given: Danh mục "Bảo lưu" đang có 10 Ticket cũ.
  - When: Admin chuyển trạng thái danh mục sang "Ngưng hoạt động".
  - Then: Trạng thái được cập nhật thành công, sinh viên không còn thấy mục "Bảo lưu" khi tạo Ticket mới, nhưng 10 Ticket cũ không bị lỗi dữ liệu.
- **FR-ADM-01/AC-04:** Tên danh mục bắt buộc (E-ADM-02)
  - Given: Admin ở form danh mục.
  - When: Để tên rỗng hoặc chỉ có khoảng trắng rồi lưu.
  - Then: Hệ thống báo trường bắt buộc, không lưu danh mục.

### Tình huống ngoại lệ
- Tạo tên chỉ khác hoa/thường với tên đang có, hoặc ngưng danh mục đã có Ticket lịch sử.

---

## FR-ADM-02 – Quản lý Phòng ban & Nhóm xử lý (Department Management)

### Mô tả
Cho phép Admin thiết lập các Phòng/Ban và phân bổ cán bộ xử lý vào các phòng ban đó để định tuyến công việc.

### Actor
Quản trị viên.

### Mức độ ưu tiên
Cao.

### Điều kiện tiên quyết
Có danh sách tài khoản Staff trong hệ thống.

### Luồng chính
1. Admin truy cập "Quản lý Phòng ban".
2. Hệ thống hiển thị danh sách phòng ban.
3. Admin chọn "Thêm phòng ban mới", nhập Tên phòng ban và Mã phòng ban.
4. Admin chọn tab "Thành viên" và gán các tài khoản Cán bộ (Staff/Manager) vào phòng ban này.
5. Admin lưu thông tin.
6. Hệ thống cập nhật phân quyền, cho phép các Cán bộ được gán có quyền nhìn thấy Hàng đợi (Queue) của phòng ban đó.

### Quy tắc nghiệp vụ
- BR-ADM-04: Mỗi phòng ban phải có ít nhất 01 Quản lý (Manager).
- BR-ADM-05: Một cán bộ (Staff) có thể thuộc nhiều phòng ban khác nhau (nếu kiêm nhiệm).

### Luồng rẽ nhánh và lỗi
- E-ADM-03: Nếu Admin xóa tất cả thành viên khỏi một phòng ban đang có Ticket "Đang xử lý", hệ thống hiện cảnh báo: "Phòng ban này đang có Ticket chưa hoàn thành. Vui lòng chuyển giao Ticket trước khi xóa nhân sự".

### Tiêu chí nghiệm thu
- **FR-ADM-02/AC-01:** Gán nhân sự vào phòng ban thành công (Kiểm tra BR-ADM-05)
  - Given: Admin đang sửa Phòng IT.
  - When: Admin thêm Staff A vào danh sách thành viên và lưu.
  - Then: Staff A có quyền truy cập Hàng đợi của Phòng IT ngay trong lần tải lại trang tiếp theo.
- **FR-ADM-02/AC-02:** Ràng buộc xóa nhân sự (Kiểm tra E-ADM-03)
  - Given: Phòng Khảo thí chỉ có duy nhất Staff B và đang có 5 Ticket chưa đóng.
  - When: Admin gỡ Staff B khỏi Phòng Khảo thí.
  - Then: Hệ thống cảnh báo không cho gỡ cho đến khi 5 Ticket kia được chuyển cho người/phòng ban khác.
- **FR-ADM-02/AC-03:** Phải giữ ít nhất một Manager (BR-ADM-04)
  - Given: Phòng ban đang có một Manager.
  - When: Admin xóa hoặc hạ vai trò Manager cuối cùng mà chưa bố trí người thay thế.
  - Then: Hệ thống từ chối lưu thay đổi, yêu cầu bổ sung Manager và giữ cấu hình hiện tại.
- **FR-ADM-02/AC-04:** Cán bộ kiêm nhiệm (BR-ADM-05)
  - Given: Staff A thuộc phòng X.
  - When: Admin thêm Staff A vào phòng Y và lưu.
  - Then: Staff A có quyền hàng đợi của X và Y sau khi tải lại, vẫn bị chặn đối với phòng Z.

### Tình huống ngoại lệ
- Gỡ Manager cuối cùng và thử Staff kiêm nhiệm hai phòng, kiểm cấu hình và quyền từng phòng.

---

## FR-ADM-03 – Cấu hình Quy tắc phân luồng (Routing Rules)

### Mô tả
Thiết lập các bộ quy tắc tự động chuyển Ticket về đúng Phòng ban dựa trên Danh mục (Category) mà sinh viên đã chọn. Tính năng này cung cấp dữ liệu đầu vào cho FR-STF-02 của Module 03.

### Actor
Quản trị viên.

### Mức độ ưu tiên
Cao.

### Điều kiện tiên quyết
Hệ thống đã có dữ liệu Danh mục (FR-ADM-01) và Phòng ban (FR-ADM-02).

### Luồng chính
1. Admin truy cập "Cấu hình Phân luồng".
2. Hệ thống hiển thị bảng mapping (ánh xạ) giữa Danh mục và Phòng ban.
3. Admin chọn một Danh mục (VD: Đăng ký môn học).
4. Admin chọn Phòng ban đích (VD: Phòng Đào tạo).
5. Admin bấm "Lưu quy tắc".
6. Mọi Ticket mới được tạo với danh mục "Đăng ký môn học" sẽ tự động rơi vào Hàng đợi của "Phòng Đào tạo".

### Quy tắc nghiệp vụ
- BR-ADM-06: Một Danh mục chỉ được phân luồng tự động (Default Routing) tới DUY NHẤT 01 Phòng ban để tránh xung đột trách nhiệm.
- BR-ADM-07: Admin có thể thiết lập "Nhân sự phụ trách mặc định" (Default Assignee) cho quy tắc này (Tùy chọn).

### Luồng rẽ nhánh và lỗi
- E-ADM-04: Nếu Admin chọn một Phòng ban đang ở trạng thái "Ngưng hoạt động" làm đích đến phân luồng, hệ thống báo lỗi: "Phòng ban đích không khả dụng".

### Tiêu chí nghiệm thu
- **FR-ADM-03/AC-01:** Thiết lập Routing Rule thành công (Kiểm tra BR-ADM-06)
  - Given: Admin thiết lập Danh mục X ánh xạ sang Phòng Y.
  - When: Admin lưu cấu hình.
  - Then: Cấu hình lưu thành công và có đúng một phòng đích hoạt động cho danh mục X. Cập nhật mapping hợp lệ thay thế phòng đích hiện tại, không tạo hai mapping mặc định.
- **FR-ADM-03/AC-02:** Ngăn chặn phân luồng vào phòng ban vô hiệu hóa (Kiểm tra E-ADM-04)
  - Given: Phòng Y đã bị ngưng hoạt động.
  - When: Admin cố gắng gán Danh mục X sang Phòng Y.
  - Then: Hệ thống báo lỗi và từ chối lưu quy tắc.
- **FR-ADM-03/AC-03:** Người phụ trách mặc định tùy chọn (BR-ADM-07)
  - Given: Danh mục X định tuyến tới phòng Y có Staff A khả dụng.
  - When: Lưu lần lượt quy tắc không có assignee, sau đó có assignee A và tạo Ticket mới cho từng cấu hình.
  - Then: Cả hai cấu hình hợp lệ. Trường hợp đầu Ticket ở hàng đợi Y chưa gán, trường hợp sau gán A và giữ phòng Y.

### Tình huống ngoại lệ
- Phòng đích bị ngưng hoạt động sau khi mở form cấu hình nhưng trước lúc lưu.

---

## FR-ADM-04 – Quản lý Mẫu phản hồi (Response Templates)

### Mô tả
Cho phép Admin tạo sẵn các đoạn văn bản trả lời chuẩn mực (có chứa các biến tự động điền) để Cán bộ sử dụng nhằm tăng tốc độ xử lý Ticket (phục vụ FR-STF-05 ở Module 03).

### Actor
Quản trị viên.

### Mức độ ưu tiên
Trung bình.

### Điều kiện tiên quyết
Người dùng đã đăng nhập bằng vai trò Administrator, danh sách biến và phạm vi hiển thị mẫu đã được xác nhận.

### Luồng chính
1. Admin truy cập "Quản lý Mẫu phản hồi".
2. Chọn "Tạo mẫu mới".
3. Nhập Tên mẫu (VD: Chào mừng), Mô tả, và Nội dung mẫu.
4. Trong Nội dung, Admin sử dụng các Biến placeholder do hệ thống cung cấp (VD: `{Ten_Sinh_Vien}`, `{Ma_Ticket}`, `{Ten_Can_Bo}`).
5. Admin lưu Mẫu phản hồi.
6. Cán bộ ở Module 03 có thể nhìn thấy và chọn Mẫu này khi trao đổi với sinh viên.

### Quy tắc nghiệp vụ
- BR-ADM-08: Admin có thể phân quyền để một Mẫu phản hồi hiển thị cho toàn hệ thống (Global) hoặc chỉ dành riêng cho một Phòng ban cụ thể (Department-specific).

### Luồng rẽ nhánh và lỗi
- E-ADM-05: Nếu Admin nhập sai cú pháp biến (VD: `{Ten_Sinh_Vien` - thiếu dấu đóng ngoặc), hệ thống báo lỗi cú pháp trước khi cho lưu.

### Tiêu chí nghiệm thu
- **FR-ADM-04/AC-01:** Lưu mẫu phản hồi chứa biến hợp lệ
  - Given: Admin nhập nội dung "Chào {Ten_Sinh_Vien}".
  - When: Admin bấm Lưu.
  - Then: Mẫu được lưu thành công và xuất hiện trong thư viện Template.
- **FR-ADM-04/AC-02:** Cảnh báo sai cú pháp biến (Kiểm tra E-ADM-05)
  - Given: Admin nhập nội dung "Chào {Ten_Sinh_Vien".
  - When: Admin bấm Lưu.
  - Then: Hệ thống báo "Lỗi cú pháp biến tự động, vui lòng kiểm tra lại cặp dấu {}".
- **FR-ADM-04/AC-03:** Phạm vi mẫu phản hồi (BR-ADM-08)
  - Given: Có mẫu Global và mẫu chỉ dành cho phòng A.
  - When: Staff A và Staff B thuộc phòng khác tải danh sách và mở từng mẫu qua API.
  - Then: Cả hai dùng được mẫu Global. Chỉ Staff A được lấy mẫu của phòng A.

### Tình huống ngoại lệ
- Mẫu có biến thiếu dấu đóng hoặc mẫu phòng A được truy cập từ Staff phòng B.

---

## FR-ADM-05 – Quản trị FAQ

### Mô tả
Admin quản lý nội dung FAQ và đối tượng xem, xuất bản hoặc gỡ xuất bản để hỗ trợ tra cứu FR-STU-06.

### Actor
Administrator.

### Mức độ ưu tiên
Cao.

### Điều kiện tiên quyết
Admin đã đăng nhập, có quyền quản lý nội dung FAQ.

### Luồng chính
1. Mở danh sách FAQ và tạo hoặc sửa bài.
2. Nhập câu hỏi, nội dung trả lời, từ khóa và đối tượng xem.
3. Lưu bản nháp hoặc xuất bản.
4. Kiểm kết quả tra cứu bằng tài khoản đúng đối tượng.

### Quy tắc nghiệp vụ
- BR-ADM-09: Chỉ FAQ đã xuất bản và đúng đối tượng mới hiển thị cho sinh viên theo FR-STU-06.

### Luồng rẽ nhánh và lỗi
- E-ADM-06: Thiếu câu hỏi hoặc câu trả lời thì từ chối xuất bản và chỉ rõ trường thiếu.

### Tiêu chí nghiệm thu
- **FR-ADM-05/AC-01:** Lưu và xuất bản FAQ (BR-ADM-09)
  - Given: Admin có FAQ nháp dành sinh viên.
  - When: Xuất bản rồi tìm bằng Student, sau đó gỡ xuất bản và tải lại.
  - Then: Student chỉ tìm và mở bài khi đã xuất bản.
- **FR-ADM-05/AC-02:** Nội dung bắt buộc (E-ADM-06)
  - Given: Admin tạo FAQ thiếu câu hỏi hoặc câu trả lời.
  - When: Chọn xuất bản.
  - Then: Hệ thống từ chối xuất bản, chỉ rõ trường thiếu và không tạo bài công khai.

### Tình huống ngoại lệ
- Bài vừa bị gỡ xuất bản vẫn còn trong kết quả cũ, truy cập lại phải kiểm trạng thái xuất bản hiện tại.

---

## FR-ADM-06 – Cấu hình SLA và lịch làm việc

### Mô tả
Admin thiết lập định mức xử lý theo priority, giờ/ngày làm việc và ngưỡng cảnh báo theo quyết định nghiệp vụ được xác nhận.

### Actor
Administrator.

### Mức độ ưu tiên
Cao.

### Điều kiện tiên quyết
PM/BA đã tổng hợp chính sách tại BR-03, BR-04 và quyền phê duyệt cấu hình.

### Luồng chính
1. Mở cấu hình SLA và lịch làm việc.
2. Nhập hoặc sửa định mức theo priority, lịch và ngưỡng cảnh báo.
3. Kiểm giá trị, lưu cấu hình kèm thời điểm hiệu lực.
4. Thử một Ticket theo cấu hình mới, kiểm tác động tới Ticket đang mở theo quyết định đã xác nhận.

### Quy tắc nghiệp vụ
- BR-ADM-10: Định mức và ngưỡng dùng cùng giá trị với BR-03, BR-04 đã xác nhận. Mỗi cấu hình có thời điểm hiệu lực.

### Luồng rẽ nhánh và lỗi
- E-ADM-07: Giá trị thời gian không dương, ngưỡng ngoài phạm vi hợp lệ hoặc cấu hình thiếu bị từ chối, giữ cấu hình hiện tại.

### Tiêu chí nghiệm thu
- **FR-ADM-06/AC-01:** Lưu cấu hình hợp lệ (BR-ADM-10)
  - Given: Admin có bộ SLA và lịch được xác nhận.
  - When: Lưu và tạo Ticket với priority tương ứng trong thời gian thử cố định.
  - Then: Hạn và cảnh báo khớp phép tính độc lập của bộ dữ liệu, lưu được thời điểm hiệu lực.
- **FR-ADM-06/AC-02:** Chặn cấu hình sai (E-ADM-07)
  - Given: Có cấu hình SLA hợp lệ đang dùng.
  - When: Thử thời gian 0, thời gian âm, ngưỡng phần trăm ngoài 0–100 hoặc thiếu priority bắt buộc.
  - Then: Hệ thống từ chối thay đổi, chỉ rõ lỗi và giữ cấu hình hiện tại.

### Tình huống ngoại lệ
- Cấu hình thay đổi khi còn Ticket đang mở, chính sách hồi tố hoặc áp dụng từ thời điểm hiệu lực phải được PM/BA xác nhận trước triển khai.

---

## FR-ADM-07 – Theo dõi workload và phân công lại

### Mô tả
Manager xem tải Ticket của nhân sự trong phạm vi quản lý và điều chỉnh assignee để cân bằng xử lý.

### Actor
Manager.

### Mức độ ưu tiên
Cao.

### Điều kiện tiên quyết
Manager đã đăng nhập, dữ liệu phòng ban và nhân sự đang hoạt động đã xác nhận.

### Luồng chính
1. Mở bảng workload của phòng quản lý.
2. Xem số Ticket theo người và trạng thái, xác định Ticket cần điều chỉnh.
3. Chọn nhân sự đích thuộc quyền quản lý, nhập lý do và xác nhận.
4. Hệ thống cập nhật một assignee, lưu lịch sử và tải lại workload.

### Quy tắc nghiệp vụ
- BR-ADM-11: Manager chỉ điều phối Ticket và nhân sự trong phạm vi quyền, mỗi Ticket có tối đa một assignee theo BR-STF-03.

### Luồng rẽ nhánh và lỗi
- E-ADM-08: Nhân sự đích không khả dụng hoặc Ticket đã được cập nhật bởi người khác thì từ chối thay đổi, yêu cầu tải lại.

### Tiêu chí nghiệm thu
- **FR-ADM-07/AC-01:** Phân công lại và cập nhật workload (BR-ADM-11)
  - Given: Ticket đang gán Staff A, Staff B cùng phòng đang hoạt động.
  - When: Manager chuyển Ticket từ A sang B với lý do.
  - Then: Chỉ B là assignee, lịch sử giữ trước/sau, workload của A giảm và B tăng một.
- **FR-ADM-07/AC-02:** Chặn ngoài quyền hoặc dữ liệu cũ (E-ADM-08, BR-ADM-11)
  - Given: Manager có màn hình cũ và có nhân sự phòng khác.
  - When: Thử phân công cho người ngoài quyền, rồi thử ghi đè Ticket vừa được người khác sửa.
  - Then: Cả hai yêu cầu bị từ chối, không thay đổi assignee hoặc làm sai số liệu workload.

### Tình huống ngoại lệ
- Hai Manager cùng phân công một Ticket, kiểm chỉ cập nhật hợp lệ đầu tiên và yêu cầu sau tải lại.
