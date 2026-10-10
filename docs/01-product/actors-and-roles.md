# Actors & Roles – UniSupport

## 1. Tổng quan

Hệ thống áp dụng cơ chế phân quyền dựa trên vai trò (Role-Based Access Control – RBAC), gồm 04 nhóm người dùng chính:

- Student – Sinh viên
- Staff – Cán bộ xử lý
- Manager – Quản lý phòng ban
- Administrator – Quản trị viên

Mỗi nhóm người dùng có trách nhiệm, nhu cầu và phạm vi truy cập khác nhau trong hệ thống.

## 2. Student – Sinh viên

**Vai trò:** Người dùng cuối gửi yêu cầu hỗ trợ đến các phòng ban của Aurora University.

**Khó khăn hiện tại:**
- Khó xác định phòng ban phụ trách yêu cầu.
- Không theo dõi được tiến độ xử lý.
- Phải liên hệ nhiều lần để cập nhật kết quả.

**Mục tiêu sử dụng:**
- Tạo Ticket và đính kèm tài liệu.
- Theo dõi trạng thái và lịch sử Ticket.
- Trao đổi với cán bộ phụ trách.
- Bổ sung thông tin khi được yêu cầu.
- Nhận thông báo về các cập nhật quan trọng.
- Tra cứu FAQ và đánh giá mức độ hài lòng.

**Bối cảnh sử dụng:** Truy cập hệ thống thông qua trình duyệt trên Desktop hoặc thiết bị Mobile.

## 3. Staff – Cán bộ xử lý

**Vai trò:** Nhân viên thuộc các phòng ban chịu trách nhiệm tiếp nhận và giải quyết Ticket.

**Khó khăn hiện tại:**
- Yêu cầu hỗ trợ phân tán qua nhiều kênh.
- Khó theo dõi các Ticket đang phụ trách.
- Dễ bỏ sót hoặc chậm xử lý yêu cầu.
- Khó phối hợp khi Ticket cần chuyển phòng ban.

**Mục tiêu sử dụng:**
- Xem và quản lý danh sách Ticket được phân công.
- Cập nhật trạng thái và mức độ ưu tiên.
- Phản hồi hoặc yêu cầu sinh viên bổ sung thông tin.
- Phân công, chuyển tiếp hoặc chuyển cấp Ticket theo quyền được cấp.
- Sử dụng mẫu phản hồi và ghi chú nội bộ.
- Theo dõi lịch sử xử lý Ticket.

## 4. Manager – Quản lý phòng ban

**Vai trò:** Trưởng hoặc Phó phòng ban chịu trách nhiệm giám sát hoạt động xử lý yêu cầu.

**Khó khăn hiện tại:**
- Khó theo dõi khối lượng công việc của cán bộ.
- Thiếu thông tin tập trung về Ticket tồn đọng.
- Khó phát hiện sớm các Ticket có nguy cơ quá hạn.

**Mục tiêu sử dụng:**
- Theo dõi tình trạng Ticket trong phạm vi quản lý.
- Giám sát khối lượng công việc của từng cán bộ.
- Phát hiện Ticket sắp đến hạn hoặc quá hạn.
- Điều chuyển hoặc phân công lại Ticket.
- Theo dõi hiệu suất và thời hạn xử lý (SLA).
- Xem Dashboard và báo cáo phục vụ quản lý.

## 5. Administrator – Quản trị viên

**Vai trò:** Nhân sự được giao trách nhiệm quản trị, cấu hình và quản lý quyền truy cập hệ thống UniSupport.

**Khó khăn hiện tại:**
- Khó quản lý tập trung danh mục hỗ trợ và cơ cấu phòng ban.
- Khó duy trì sự nhất quán trong quy tắc phân luồng yêu cầu.
- Cần kiểm soát tài khoản và quyền truy cập của các nhóm người dùng.

**Mục tiêu sử dụng:**
- Quản lý tài khoản và vai trò người dùng.
- Quản lý danh mục yêu cầu và phòng ban.
- Cấu hình mức độ ưu tiên của Ticket.
- Thiết lập quy tắc phân luồng tự động (Routing Rules).
- Quản lý FAQ/Knowledge Base.
- Quản lý mẫu phản hồi.
- Cấu hình thời hạn xử lý theo loại Ticket hoặc mức ưu tiên.

## 6. Nguyên tắc phân quyền

- Hệ thống sử dụng 04 vai trò: Student, Staff, Manager và Administrator.
- Người dùng chỉ được truy cập các chức năng và dữ liệu phù hợp với vai trò được cấp.
- Student chỉ được truy cập các Ticket thuộc phạm vi được phép.
- Staff thực hiện xử lý Ticket theo phạm vi phân công và quyền hạn.
- Manager giám sát và điều phối công việc trong phạm vi quản lý.
- Administrator quản lý cấu hình hệ thống, tài khoản và phân quyền.
- Quy tắc phân quyền chi tiết được mô tả tại module Authentication & RBAC.

## 7. Phạm vi xác thực

Theo Proposal, UniSupport sử dụng tài khoản nội bộ của hệ thống để đăng nhập và hỗ trợ đặt lại mật khẩu.

