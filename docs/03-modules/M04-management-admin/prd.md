# MODULE M04: ADMIN CONFIG (QUẢN TRỊ & CẤU HÌNH)

# 1. Đặc tả yêu cầu chức năng

## FR-ADM-01 – Quản lý Danh mục yêu cầu (Category Management)

### Mô tả
Cho phép Quản trị viên (Admin) tạo mới, cập nhật và quản lý trạng thái các danh mục (Category) để sinh viên phân loại Ticket khi gửi, đồng thời làm cơ sở cho hệ thống phân luồng.

### Actor
Quản trị viên (Administrator).

### Mức độ ưu tiên
Cao.

### Điều kiện tiên quyết
Tài khoản đăng nhập có vai trò Administrator.

### Luồng chính
1. Admin truy cập "Danh mục yêu cầu".
2. Hệ thống hiển thị danh sách các Danh mục hiện có.
3. Admin chọn "Thêm mới" hoặc bấm vào một danh mục để "Cập nhật".
4. Admin nhập các thông tin bắt buộc (Tên danh mục) và thông tin tùy chọn (Mô tả).
5. Admin chọn trạng thái (Hoạt động/Ngưng hoạt động) và bấm "Lưu".
6. Hệ thống lưu vào cơ sở dữ liệu.

### Quy tắc nghiệp vụ
- BR-ADM-01: Tên danh mục phải là duy nhất.
- BR-ADM-02: Không được xóa cứng (Hard Delete) danh mục đã có Ticket liên kết. Chỉ được chuyển sang "Ngưng hoạt động".
- BR-ADM-03: Danh mục "Ngưng hoạt động" sẽ không hiển thị trên Student Portal.

### Luồng rẽ nhánh, Tình huống biên (Edge Cases) và Lỗi
- E-ADM-01: Nhập tên danh mục đã tồn tại -> Chặn lưu, báo lỗi trùng lặp.
- E-ADM-02: Bỏ trống tên danh mục -> Chặn lưu, yêu cầu nhập trường bắt buộc.
- Edge Case: Admin vô hiệu hóa một danh mục đang được cấu hình trong Quy tắc phân luồng (FR-ADM-03) -> Hệ thống cảnh báo việc vô hiệu hóa này sẽ vô hiệu hóa cả quy tắc định tuyến tương ứng.

### Tiêu chí nghiệm thu
- **FR-ADM-01/AC-01:** Thêm mới danh mục thành công
  - Given: Admin ở form thêm mới Danh mục.
  - When: Nhập tên "Hỗ trợ học phí" và lưu.
  - Then: Hệ thống thông báo thành công, danh mục xuất hiện với trạng thái Hoạt động.
- **FR-ADM-01/AC-02:** Chặn trùng lặp tên (Kiểm tra BR-ADM-01, E-ADM-01)
  - Given: Đã có danh mục "Kỹ thuật".
  - When: Tạo mới danh mục tên "kỹ thuật".
  - Then: Báo lỗi trùng lặp, không cho phép lưu.
- **FR-ADM-01/AC-03:** Chặn bỏ trống tên (Kiểm tra E-ADM-02)
  - Given: Admin ở form thêm mới.
  - When: Để trống "Tên danh mục" và bấm Lưu.
  - Then: Nút lưu bị chặn, hiển thị lỗi màu đỏ "Vui lòng nhập tên danh mục".
- **FR-ADM-01/AC-04:** Ngưng hoạt động danh mục (Kiểm tra BR-ADM-02, BR-ADM-03)
  - Given: Danh mục "Bảo lưu" đang có 10 Ticket cũ.
  - When: Admin chuyển trạng thái sang "Ngưng hoạt động".
  - Then: Trạng thái cập nhật thành công, Sinh viên không thấy mục "Bảo lưu" khi tạo Ticket, 10 Ticket cũ không bị lỗi.

### Tình huống ngoại lệ
- Xóa một danh mục đang có Ticket. Thay vì xóa vật lý (hard delete) gây lỗi mất dữ liệu, hệ thống tự động chuyển danh mục sang trạng thái "Vô hiệu hóa" (ẩn khỏi menu tạo mới) nhưng vẫn hiển thị bình thường ở các Ticket lịch sử.

---

## FR-ADM-02 – Quản lý Phòng ban & Nhóm xử lý (Department Management)

### Mô tả
Thiết lập các Phòng/Ban và phân bổ cán bộ xử lý vào các phòng ban đó để định tuyến công việc.

### Actor
Quản trị viên.

### Mức độ ưu tiên
Cao.

### Luồng chính
1. Admin truy cập "Quản lý Phòng ban".
2. Chọn "Thêm phòng ban mới", nhập Tên, Mã phòng ban.
3. Chọn tab "Thành viên" và gán các tài khoản Cán bộ.
4. Chỉ định ít nhất 1 tài khoản làm Manager của phòng.
5. Lưu thông tin.

### Quy tắc nghiệp vụ
- BR-ADM-04: Mỗi phòng ban PHẢI có ít nhất 01 Quản lý (Manager).
- BR-ADM-05: Một cán bộ (Staff) có thể thuộc nhiều phòng ban khác nhau.

### Luồng rẽ nhánh, Tình huống biên và Lỗi
- E-ADM-03: Xóa tất cả thành viên khỏi phòng ban đang có Ticket "Đang xử lý" -> Báo lỗi yêu cầu chuyển giao.

### Tiêu chí nghiệm thu
- **FR-ADM-02/AC-01:** Ràng buộc tối thiểu 1 Manager (Kiểm tra BR-ADM-04)
  - Given: Admin tạo Phòng ban mới.
  - When: Admin gán 3 Staff nhưng không check chọn ai làm Manager và bấm Lưu.
  - Then: Hệ thống chặn và báo lỗi "Phòng ban phải có ít nhất 1 Manager".
- **FR-ADM-02/AC-02:** Gán nhân sự kiêm nhiệm (Kiểm tra BR-ADM-05)
  - Given: Staff A đang thuộc Phòng IT.
  - When: Admin thêm Staff A vào Phòng Đào tạo.
  - Then: Cấu hình lưu thành công, Staff A thấy Hàng đợi của cả 2 phòng.
- **FR-ADM-02/AC-03:** Ràng buộc xóa nhân sự (Kiểm tra E-ADM-03)
  - Given: Phòng Khảo thí có 1 Staff B và 5 Ticket chưa đóng.
  - When: Admin gỡ Staff B khỏi phòng.
  - Then: Cảnh báo "Phòng ban có Ticket đang xử lý, vui lòng chuyển giao trước".

### Tình huống ngoại lệ
- Admin tự xóa chính mình khỏi quyền Quản trị (Admin). Hệ thống chặn và yêu cầu phải có ít nhất 1 Admin khác tồn tại trên hệ thống trước khi tài khoản này được phép tự tước quyền.

---

## FR-ADM-03 – Cấu hình Quy tắc phân luồng (Routing Rules)

### Mô tả
Thiết lập bộ quy tắc tự động chuyển Ticket về đúng Phòng ban dựa trên Danh mục sinh viên chọn.

### Luồng chính
1. Admin truy cập "Cấu hình Phân luồng".
2. Chọn 1 Danh mục, ánh xạ sang 1 Phòng ban đích.
3. (Tùy chọn) Chọn 1 nhân sự phụ trách mặc định (Default Assignee).
4. Lưu quy tắc.

### Quy tắc nghiệp vụ
- BR-ADM-06: Một Danh mục chỉ ánh xạ tự động tới 01 Phòng ban.
- BR-ADM-07: Admin có thể thiết lập Default Assignee; nếu có, Ticket mới rơi vào phòng ban sẽ tự động gán thẳng cho người này thay vì nằm ở Hàng đợi chung.

### Luồng rẽ nhánh và Lỗi
- E-ADM-04: Chọn Phòng ban đích "Ngưng hoạt động" -> Báo lỗi.

### Tiêu chí nghiệm thu
- **FR-ADM-03/AC-01:** Ánh xạ 1-1 (Kiểm tra BR-ADM-06)
  - Given: Danh mục X đang ánh xạ Phòng Y.
  - When: Admin gán Danh mục X sang Phòng Z.
  - Then: Hệ thống hỏi "Ghi đè quy tắc cũ sang Phòng Z?", chỉ giữ lại 1 đích đến duy nhất.
- **FR-ADM-03/AC-02:** Người phụ trách mặc định (Kiểm tra BR-ADM-07)
  - Given: Danh mục "Bảo lưu" được cấu hình người tiếp nhận mặc định là "Trần Văn B".
  - When: Sinh viên tạo Ticket thuộc danh mục "Bảo lưu".
  - Then: Ticket tự động hiển thị ở trạng thái "Đang xử lý" và gán thẳng cho "Trần Văn B".

### Tình huống ngoại lệ
- Người tiếp nhận mặc định ("Trần Văn B") vừa nghỉ việc hoặc bị khóa tài khoản. Khi sinh viên tạo Ticket mới vào danh mục này, hệ thống sẽ tự động chuyển hướng (fallback) gán Ticket cho tài khoản "Manager" của phòng ban đó thay vì chặn sinh viên tạo Ticket.

---

## FR-ADM-04 – Quản lý Mẫu phản hồi (Response Templates)

### Mô tả
Tạo văn bản trả lời tự động điền biến (VD: `{Ten_Sinh_Vien}`) để Staff dùng.

### Quy tắc nghiệp vụ
- BR-ADM-08: Mẫu phản hồi có 2 phạm vi (Scope): "Toàn hệ thống" (mọi phòng ban đều thấy) hoặc "Nội bộ phòng ban" (chỉ phòng được chỉ định mới thấy).

### Luồng rẽ nhánh và Lỗi
- E-ADM-05: Sai cú pháp biến (thiếu ngoặc `}`) -> Báo lỗi cú pháp.

### Tiêu chí nghiệm thu
- **FR-ADM-04/AC-01:** Phân quyền hiển thị Mẫu phản hồi (Kiểm tra BR-ADM-08)
  - Given: Admin tạo Template T1 (Phạm vi: Phòng IT).
  - When: Staff Phòng Khảo thí mở chức năng chèn mẫu.
  - Then: Template T1 không xuất hiện trong danh sách của Staff Khảo thí.
- **FR-ADM-04/AC-02:** Bắt lỗi cú pháp biến (Kiểm tra E-ADM-05)
  - Given: Admin nhập "{Ten_Sinh_Vien".
  - When: Bấm Lưu.
  - Then: Báo lỗi "Sai cú pháp biến {}".
- **FR-ADM-04/AC-03:** Giới hạn phạm vi mẫu phản hồi (Kiểm tra BR-ADM-08)
  - Given: Mẫu phản hồi "M01" được thiết lập chỉ cấp quyền cho phòng IT.
  - When: Cán bộ phòng Đào tạo mở danh sách Mẫu phản hồi.
  - Then: Mẫu "M01" bị ẩn hoàn toàn, không xuất hiện trong danh sách chọn của cán bộ phòng Đào tạo.

### Tình huống ngoại lệ
- Admin thay đổi nội dung của một Mẫu phản hồi. Các Ticket trước đó đã dùng mẫu này để trả lời sinh viên không bị đổi nội dung (do text đã được copy cứng), nội dung mới chỉ áp dụng cho những lần cán bộ chèn mẫu tiếp theo.

---

## FR-ADM-05 – Quản lý Tài khoản & Phân quyền (Account & Role Management)

### Mô tả
Cho phép Admin tạo, cập nhật, vô hiệu hóa tài khoản và gán vai trò (Role), phòng ban cho nhân sự.

### Actor
Quản trị viên (Admin).

### Mức độ ưu tiên
Cao.

### Điều kiện tiên quyết
Tài khoản đăng nhập có quyền Admin hệ thống.

### Luồng chính
1. Admin mở danh sách tài khoản.
2. Chọn Thêm mới hoặc Chỉnh sửa một tài khoản.
3. Điền thông tin cơ bản (Tên, Email).
4. Gán vai trò (Manager/Staff) và chỉ định Phòng ban trực thuộc.
5. Bấm Lưu.

### Quy tắc nghiệp vụ
- BR-ADM-04: Mỗi phòng ban trên hệ thống bắt buộc phải có tối thiểu 1 tài khoản mang vai trò Manager đang ở trạng thái Hoạt động.

### Luồng rẽ nhánh và lỗi
- E-ADM-03: Nếu hành động vô hiệu hóa (deactivate) làm mất Manager duy nhất của một phòng ban, hệ thống chặn lại và báo lỗi.

### Tiêu chí nghiệm thu
- **FR-ADM-05/AC-01:** Đảm bảo tối thiểu 1 Manager (Kiểm tra BR-ADM-04 & E-ADM-03)
  - Given: Phòng ban IT chỉ còn đúng 1 Manager đang hoạt động.
  - When: Admin thực hiện vô hiệu hóa (deactivate) tài khoản Manager này.
  - Then: Hệ thống chặn lưu và báo lỗi đỏ "Phòng ban IT phải có ít nhất 1 Manager. Vui lòng gán Manager mới trước khi vô hiệu hóa".

### Tình huống ngoại lệ
- Admin đang thay đổi phân quyền cho một Staff, nhưng ngay lúc đó Staff này đang soạn dở một Ticket. Hệ thống cho phép Staff hoàn tất thao tác lưu Ticket hiện tại, quyền mới sẽ chỉ có hiệu lực ở lần tải lại trang hoặc request tiếp theo.

---

## FR-ADM-06 – Quản trị Cấu hình SLA & Cảnh báo (SLA Configuration)

### Mô tả
Cấu hình thời hạn xử lý tối đa cho từng mức độ ưu tiên và các mốc gửi thông báo nhắc nhở tự động.

### Actor
Quản trị viên, Quản lý.

### Mức độ ưu tiên
Cao.

### Điều kiện tiên quyết
Hệ thống đã có sẵn các Mức độ ưu tiên (Priority) được định nghĩa.

### Luồng chính
1. Truy cập cài đặt SLA.
2. Chọn mức ưu tiên (Cao/Trung bình/Thấp).
3. Đặt thời gian SLA (VD: 72 giờ).
4. Cấu hình gửi cảnh báo trước khi hết hạn (VD: gửi thông báo trước 12 giờ).
5. Bấm Lưu.

### Quy tắc nghiệp vụ
- Không có.

### Luồng rẽ nhánh và lỗi
- E-ADM-04: Nếu cấu hình thời gian cảnh báo lớn hơn hoặc bằng thời gian SLA (VD: SLA 24h nhưng cảnh báo trước 48h), hệ thống chặn và báo lỗi logic.

### Tiêu chí nghiệm thu
- **FR-ADM-06/AC-01:** Gửi cảnh báo sắp hết hạn
  - Given: SLA của Ticket là 72 giờ, hệ thống được cài cảnh báo trước 12 giờ.
  - When: Ticket đã xử lý được 60 giờ nhưng vẫn chưa chuyển sang trạng thái "Hoàn thành".
  - Then: Hệ thống tự động gửi Email và thông báo In-app cho người phụ trách (Assignee) với nội dung "Cảnh báo: Yêu cầu #... sắp quá hạn".

### Tình huống ngoại lệ
- Nếu cấu hình thời gian SLA bị thay đổi (ví dụ giảm từ 72h xuống 48h), các Ticket đã được tạo trước thời điểm đổi vẫn áp dụng SLA cũ (72h) để đảm bảo công bằng cho cán bộ, chỉ Ticket mới tạo mới áp dụng SLA 48h.

---

## FR-ADM-07 – Quản trị Câu hỏi thường gặp (FAQ Management)

### Mô tả
Tạo, chỉnh sửa, xuất bản (publish) hoặc ngừng xuất bản (unpublish) các bài viết FAQ trên Student Portal.

### Actor
Quản trị viên, Quản lý.

### Mức độ ưu tiên
Trung bình.

### Điều kiện tiên quyết
Không có.

### Luồng chính
1. Mở menu Quản lý FAQ.
2. Viết câu hỏi và câu trả lời.
3. Đính kèm hình ảnh minh họa (nếu có).
4. Chọn trạng thái "Xuất bản" hoặc "Nháp / Ngừng xuất bản".
5. Bấm Lưu.

### Quy tắc nghiệp vụ
- Không có.

### Luồng rẽ nhánh và lỗi
- E-ADM-05: Tên câu hỏi để trống, hệ thống chặn lưu.

### Tiêu chí nghiệm thu
- **FR-ADM-07/AC-01:** Kiểm soát hiển thị bằng trạng thái xuất bản
  - Given: Bài viết FAQ "Cách làm lại thẻ sinh viên" đang có trên hệ thống.
  - When: Manager đổi trạng thái bài viết thành "Ngừng xuất bản".
  - Then: Bài viết lưu thành công ở dạng Nháp, sinh viên đăng nhập Student Portal không thể tìm thấy hoặc tra cứu được bài viết này nữa.

### Tình huống ngoại lệ
- Manager đang cập nhật và sửa lỗi chính tả nội dung một bài FAQ trong lúc một sinh viên đang mở đọc bài đó. Sinh viên vẫn đọc được phiên bản cũ bình thường không bị lỗi, phiên bản mới chỉ áp dụng khi sinh viên tải lại trang.