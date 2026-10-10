# PRODUCT SCOPE – UNISUPPORT

## 1. Tổng quan phạm vi

UniSupport v1.0 là hệ thống quản lý yêu cầu hỗ trợ sinh viên trên nền tảng Web,
được phát triển cho Aurora University với quy mô phục vụ khoảng 3.000 sinh viên.

Dự án tập trung xây dựng một hệ thống hỗ trợ tập trung cho phép tiếp nhận,
phân loại, phân luồng, xử lý và theo dõi Ticket, đồng thời hỗ trợ quản lý
thời hạn xử lý, khối lượng công việc và báo cáo vận hành.

**Thời gian triển khai dự kiến:** 23 tuần.

**Phạm vi bàn giao:** Hệ thống UniSupport, mã nguồn, tài liệu kỹ thuật
và hướng dẫn sử dụng theo Proposal.

---

## 2. Phạm vi trong dự án (In-Scope)

UniSupport v1.0 bao gồm 05 nhóm chức năng chính.

### 2.1. Student Portal

- Tạo Ticket theo danh mục.
- Tự động tạo mã Ticket.
- Đính kèm tài liệu hoặc hình ảnh.
- Theo dõi trạng thái:
  - Mới tạo.
  - Đang xử lý.
  - Cần bổ sung.
  - Hoàn thành.
- Trao đổi trực tiếp với cán bộ xử lý.
- Bổ sung thông tin/tài liệu khi được yêu cầu.
- Mở lại Ticket trong thời gian quy định.
- Xem lịch sử xử lý Ticket.
- Nhận thông báo trên hệ thống và qua Email khi có cập nhật quan trọng.
- Tra cứu FAQ theo chủ đề.
- Tìm kiếm hướng dẫn trước khi tạo Ticket.
- Đánh giá mức độ hài lòng sau khi Ticket hoàn thành.

### 2.2. Staff Desk

- Xem danh sách tập trung các Ticket cần xử lý.
- Tự động phân luồng theo danh mục/phòng ban.
- Phân công Ticket cho cán bộ.
- Chuyển tiếp hoặc chuyển cấp Ticket.
- Tìm kiếm, lọc và sắp xếp Ticket theo:
  - Trạng thái.
  - Danh mục.
  - Mức ưu tiên.
  - Thời gian.
- Cập nhật trạng thái Ticket.
- Thiết lập hoặc cập nhật mức độ ưu tiên.
- Yêu cầu Sinh viên bổ sung thông tin.
- Thêm ghi chú nội bộ.
- Phản hồi chính thức cho Sinh viên.
- Sử dụng mẫu phản hồi có sẵn.
- Lưu lịch sử thao tác và thay đổi trạng thái.

### 2.3. Management & Administration

#### Quản lý hoạt động xử lý

- Theo dõi số lượng Ticket theo phòng ban/cán bộ.
- Theo dõi Ticket tồn đọng.
- Theo dõi Ticket sắp quá hạn.
- Điều chuyển hoặc phân công lại Ticket.
- Theo dõi khối lượng công việc của cán bộ.

#### Quản lý thời hạn xử lý

- Thiết lập thời hạn xử lý theo loại Ticket hoặc mức ưu tiên.
- Theo dõi thời gian xử lý.
- Cảnh báo Ticket sắp đến hạn hoặc quá hạn.

#### Cấu hình hệ thống

- Quản lý danh mục yêu cầu.
- Quản lý phòng ban.
- Quản lý mức độ ưu tiên.
- Cấu hình Routing Rule.
- Quản lý tài khoản và vai trò người dùng.
- Quản lý FAQ / Knowledge Base.
- Quản lý Response Template.

### 2.4. Dashboard & Reporting

- Thống kê số lượng Ticket theo trạng thái.
- Theo dõi tỷ lệ hoàn thành.
- Theo dõi Ticket tồn đọng.
- Theo dõi Average Processing Time.
- Theo dõi hiệu suất theo phòng ban/cán bộ.
- Thống kê các nhóm vấn đề phổ biến.
- Phân tích xu hướng Ticket theo thời gian.
- Báo cáo Student Satisfaction.
- Xuất báo cáo CSV.

### 2.5. Security, Authentication & User Experience

- Đăng nhập bằng tài khoản UniSupport.
- Hỗ trợ đặt lại mật khẩu.
- Hỗ trợ 04 Role:
  - Student.
  - Staff.
  - Manager.
  - Administrator.
- Phân quyền chức năng và dữ liệu theo Role.
- Kiểm soát quyền truy cập dữ liệu và tệp đính kèm.
- Ghi nhận các thao tác quan trọng.
- Sử dụng dữ liệu giả lập trong Development và Testing.
- Hỗ trợ Tiếng Việt và Tiếng Anh.
- Responsive trên Desktop và Mobile.
- Giao diện đơn giản, nhất quán và dễ sử dụng.

Chi tiết Functional Requirement được mô tả tại `docs/03-modules/`.

---

## 3. Phạm vi ngoài dự án (Out-of-Scope)

### OS-01 – Thay đổi quy trình nghiệp vụ

Không xây dựng lại hoặc thay đổi quy trình nghiệp vụ hiện tại
của Aurora University.

### OS-02 – Hạ tầng phần cứng

Không cung cấp hoặc nâng cấp phần cứng, máy chủ vật lý
và hạ tầng mạng.

### OS-03 – Native Mobile Application

Không phát triển Native Mobile App riêng cho iOS hoặc Android.

### OS-04 – External Authentication

Không tích hợp SSO hoặc các hệ thống xác thực bên ngoài.

### OS-05 – Third-party Integration

Không tích hợp các hệ thống bên thứ ba ngoài những hệ thống
đã được thống nhất trong phạm vi dự án.

### OS-06 – AI / ML / Chatbot

Không phát triển AI, Machine Learning, Chatbot hoặc các chức năng
nâng cao ngoài phạm vi.

### OS-07 – Historical Data Migration

Không thu thập, làm sạch, chuẩn hóa hoặc chuyển đổi toàn bộ
dữ liệu lịch sử thay cho Aurora University.

### OS-08 – Nghiệp vụ chuyên môn phòng ban

UniSupport không trực tiếp thực hiện hoặc giải quyết nghiệp vụ
chuyên môn thay cho các phòng ban.

### OS-09 – Long-term Operations

Không bao gồm hoạt động vận hành, bảo trì và hỗ trợ dài hạn
sau bàn giao, ngoại trừ Warranty Support được quy định trong Proposal.

---

## 4. Giả định dự án (Assumptions)

### AS-01 – Cung cấp thông tin nghiệp vụ

Aurora University cung cấp đầy đủ thông tin, quy trình và yêu cầu nghiệp vụ
cần thiết cho quá trình phân tích và triển khai.

### AS-02 – Phối hợp và phản hồi

Aurora University bố trí đầu mối phối hợp và phản hồi các nội dung cần
xác nhận hoặc phê duyệt theo kế hoạch dự án.

### AS-03 – Tham gia UAT

Aurora University bố trí đại diện tham gia UAT và cung cấp phản hồi
theo kế hoạch nghiệm thu.

> Các giới hạn về hạ tầng, tích hợp, dữ liệu lịch sử và vận hành
> được quy định tại `3. Out-of-Scope`.

---

## 5. Quản lý thay đổi phạm vi

- Phạm vi dự án được xác nhận và khóa tại Milestone M1 – Tuần 5.
- Các yêu cầu bổ sung hoặc điều chỉnh ngoài phạm vi phải được ghi nhận
  bằng Change Request.
- Change Request phải được đánh giá tác động đến:
  - Chức năng/phạm vi.
  - Tiến độ.
  - Chi phí.
  - Nguồn lực.
- Chỉ triển khai thay đổi sau khi hai bên thống nhất.
- Yêu cầu chưa được phê duyệt không mặc định thuộc trách nhiệm
  của Project Team.

---

## 6. Nguyên tắc nghiệm thu phạm vi

- Hệ thống được đánh giá dựa trên các chức năng thuộc In-Scope đã thống nhất.
- Aurora University thực hiện UAT và phản hồi trong vòng 05 ngày làm việc
  kể từ khi nhận phiên bản nghiệm thu.
- Lỗi ảnh hưởng đến chức năng In-Scope phải được Project Team khắc phục
  theo điều kiện nghiệm thu.
- Các lỗi nhỏ không ảnh hưởng chức năng chính được xử lý theo danh sách lỗi
  đã thống nhất và không mặc nhiên là căn cứ trì hoãn toàn bộ nghiệm thu.
- Yêu cầu ngoài In-Scope không được bổ sung vào điều kiện nghiệm thu
  nếu chưa có Change Request được phê duyệt.