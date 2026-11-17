# MODULE M04: ADMIN CONFIG (QUẢN TRỊ & CẤU HÌNH)

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
  - Then: Cấu hình lưu thành công. Giao diện không cho phép gán Danh mục X sang một Phòng Z nào khác.
- **FR-ADM-03/AC-02:** Ngăn chặn phân luồng vào phòng ban vô hiệu hóa (Kiểm tra E-ADM-04)
  - Given: Phòng Y đã bị ngưng hoạt động.
  - When: Admin cố gắng gán Danh mục X sang Phòng Y.
  - Then: Hệ thống báo lỗi và từ chối lưu quy tắc.

---

## FR-ADM-04 – Quản lý Mẫu phản hồi (Response Templates)

### Mô tả
Cho phép Admin tạo sẵn các đoạn văn bản trả lời chuẩn mực (có chứa các biến tự động điền) để Cán bộ sử dụng nhằm tăng tốc độ xử lý Ticket (phục vụ FR-STF-05 ở Module 03).

### Actor
Quản trị viên.

### Mức độ ưu tiên
Trung bình.

### Điều kiện tiên quyết
Không có.

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