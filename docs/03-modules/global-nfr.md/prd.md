# GLOBAL NON-FUNCTIONAL REQUIREMENTS (NFR)

# 1. Tổng quan

Các yêu cầu phi chức năng (NFR) trong tài liệu này áp dụng xuyên suốt toàn bộ hệ thống UniSupport, bao gồm:
- M01 – Security, Authentication & RBAC.
- M02 – Student Portal.
- M03 – Staff Desk.
- M04 – Management & Administration.
- M05 – Dashboard & Report.

Các tiêu chí này là thước đo bắt buộc để nghiệm thu (UAT) hệ thống. Mọi AC (Acceptance Criteria) đều có mã định danh duy nhất để phục vụ truy vết từ kịch bản test (Test Scenarios).

---

# 2. Đặc tả Yêu cầu Phi chức năng

## NFR-GLB-01 – Dữ liệu Kiểm thử & Môi trường (Testing Data)

### Mô tả
Trong quá trình Development và Testing, tuyệt đối không sử dụng dữ liệu thật của sinh viên Aurora University để đảm bảo an toàn thông tin. Hệ thống phải được cung cấp bộ dữ liệu giả lập (Mock Data) đủ lớn để mô phỏng tải thực tế.

### Tiêu chí nghiệm thu
- **NFR-GLB-01/AC-01:** Khởi tạo dữ liệu giả lập
  - Given: Môi trường Testing được khởi tạo.
  - When: Chạy script seed data.
  - Then: Hệ thống tự động sinh ra tập dữ liệu tối thiểu gồm: 3.000 tài khoản Sinh viên, 50 tài khoản Staff, và 5.000 Ticket trải đều các trạng thái.
- **NFR-GLB-01/AC-02:** Bảo vệ dữ liệu thật
  - Given: QA thực hiện kiểm thử trên môi trường Testing.
  - When: Truy vấn Database.
  - Then: Không tồn tại bất kỳ thông tin cá nhân (Email, CCCD, Mã SV) nào khớp với dữ liệu thực tế của Aurora University.

---

## NFR-GLB-02 – Đa ngôn ngữ (Bilingual Support)

### Mô tả
Giao diện UniSupport phải hỗ trợ đầy đủ Tiếng Việt (mặc định) và Tiếng Anh để phục vụ sinh viên quốc tế. 

### Tiêu chí nghiệm thu
- **NFR-GLB-02/AC-01:** Chuyển đổi ngôn ngữ tức thì
  - Given: Người dùng đang thao tác trên form tạo Ticket.
  - When: Click đổi ngôn ngữ từ Tiếng Việt sang Tiếng Anh.
  - Then: Toàn bộ Label, Menu, Placeholder chuyển sang Tiếng Anh trong vòng dưới 1 giây; nội dung người dùng đang gõ dở không bị mất.
- **NFR-GLB-02/AC-02:** Phạm vi không dịch thuật (Ngoại lệ)
  - Given: Hệ thống đang hiển thị Tiếng Anh.
  - When: Sinh viên xem nội dung phản hồi do Staff nhập bằng Tiếng Việt.
  - Then: Giao diện tĩnh là Tiếng Anh, nhưng phần nội dung bình luận/mô tả của Staff vẫn hiển thị nguyên bản Tiếng Việt, không dịch tự động.

---

## NFR-GLB-03 – Khả năng Tương thích & Hiển thị (Responsive)

### Mô tả
Hệ thống là Web Responsive, phải hoạt động tốt trên các thiết bị và trình duyệt phổ thông mà không bị che khuất nội dung hay xuất hiện thanh cuộn ngang (horizontal scroll).

### Điều kiện đo lường chốt:
- **Desktop Breakpoint:** Cửa sổ trình duyệt từ 1024px trở lên.
- **Mobile Breakpoint:** Cửa sổ trình duyệt từ 375px đến 768px.
- **Trình duyệt hỗ trợ:** 2 phiên bản mới nhất của Google Chrome, Safari, và Microsoft Edge.

### Tiêu chí nghiệm thu
- **NFR-GLB-03/AC-01:** Hiển thị trên Mobile
  - Given: Truy cập hệ thống bằng trình duyệt Safari với độ phân giải 375x812px.
  - When: Mở danh sách Ticket.
  - Then: Bảng dữ liệu tự động chuyển sang dạng danh sách thẻ (Card view), thanh Menu ngang thu gọn vào Hamburger Menu.
- **NFR-GLB-03/AC-02:** Tương thích trình duyệt
  - Given: Người dùng truy cập bằng Microsoft Edge.
  - When: Thực hiện luồng đính kèm file và gửi Ticket.
  - Then: Chức năng hoạt động thành công tương tự như trên Google Chrome, không có lỗi hiển thị (CSS/UI).

---

## NFR-GLB-04 – Hiệu năng & Khả năng chịu tải (Performance)

### Mô tả
Hệ thống phải đảm bảo tốc độ phản hồi nhanh trong các kỳ cao điểm (kỳ thi, đăng ký tín chỉ) của Aurora University.

### Điều kiện đo lường chốt:
- **Quy mô người dùng tải:** 3.000 Sinh viên kích hoạt, 50 Staff xử lý.
- **Tải đồng thời tối đa (Concurrent Users):** 300 người dùng thao tác cùng lúc.
- **Thời gian phản hồi API (Response Time):** < 2 giây.

### Tiêu chí nghiệm thu
- **NFR-GLB-04/AC-01:** Phản hồi dưới ngưỡng tiêu chuẩn
  - Given: Người dùng ở màn hình Student Portal hoặc Staff Desk.
  - When: Bấm "Tạo mới Ticket" hoặc "Lưu cập nhật trạng thái".
  - Then: Nút bấm hiển thị trạng thái Loading và hoàn tất xử lý (nhận thông báo thành công) trong tối đa 2 giây.
- **NFR-GLB-04/AC-02:** Chịu tải đồng thời mùa cao điểm
  - Given: Công cụ kiểm thử (JMeter) tạo 300 request gửi Ticket cùng một lúc vào API.
  - When: Hệ thống xử lý các request.
  - Then: Tỷ lệ lỗi (Error rate 5xx) < 1% và thời gian phản hồi trung bình (Average Response Time) không vượt quá 3 giây.

---

## NFR-GLB-05 – Tính dễ sử dụng & Phản hồi giao diện (Usability)

### Mô tả
Giao diện UniSupport phải đảm bảo tính nhất quán (Consistency) và luôn có phản hồi (Feedback) lập tức để người dùng không bị bối rối khi thao tác.

### Tiêu chí nghiệm thu
- **NFR-GLB-05/AC-01:** Chống submit nhiều lần (Anti-Double Click)
  - Given: Người dùng điền xong form tạo Ticket.
  - When: Bấm liên tục (click đúp) vào nút "Xác nhận gửi".
  - Then: Ngay sau click đầu tiên, nút bấm bị vô hiệu hóa (disabled) và chỉ gửi đúng 01 request lên server.
- **NFR-GLB-05/AC-02:** Nhất quán thuật ngữ trạng thái
  - Given: Mọi màn hình hiển thị danh sách hoặc chi tiết Ticket (ở M02, M03, M05).
  - When: Kiểm tra nhãn trạng thái.
  - Then: Tuyệt đối chỉ sử dụng 4 nhãn chuẩn: "Mới tạo", "Đang xử lý", "Cần bổ sung", "Hoàn thành". Không xuất hiện các biến thể như "Đã xong", "Đang chờ".
- **NFR-GLB-05/AC-03:** Phản hồi lỗi nhập liệu (Inline Validation)
  - Given: Người dùng đang thao tác trên form.
  - When: Bỏ trống trường bắt buộc và bấm Submit.
  - Then: Thông báo lỗi màu đỏ xuất hiện ngay bên dưới trường dữ liệu bị thiếu thay vì dùng Popup (Alert) của trình duyệt.