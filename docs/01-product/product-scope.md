# PHẠM VI SẢN PHẨM & GIẢ ĐỊNH (PRODUCT SCOPE)

## 1. Phạm vi trong dự án (In-Scope)
Dự án UniSupport v1.0 tập trung phát triển và bàn giao một hệ thống Web-based (Responsive) bao gồm 05 phân hệ nghiệp vụ lõi:

1. **Cổng Hỗ trợ Sinh viên (Student Portal):** Tiếp nhận yêu cầu, đính kèm minh chứng, theo dõi trạng thái Ticket, trao đổi 2 chiều và tra cứu FAQ.
2. **Không gian làm việc Cán bộ (Staff Service Desk):** Quản lý hàng đợi Ticket, phân công xử lý, chuyển tiếp phòng ban, cập nhật trạng thái và sử dụng mẫu phản hồi (Canned Responses).
3. **Quản lý & Cấu hình hệ thống (Admin & Operations):** Điều phối Workload cán bộ, cấu hình danh mục, quản lý phòng ban, định tuyến tự động (Routing Rules) và thiết lập thời hạn xử lý (SLA).
4. **Báo cáo & Thống kê (Dashboard & Analytics):** Cung cấp biểu đồ trực quan về tỷ lệ hoàn thành, thời gian xử lý trung bình (MTTR), Backlog, đánh giá CSAT và trích xuất dữ liệu CSV.
5. **Hạ tầng Bảo mật & Xác thực (Security & Auth):** Hệ thống phân quyền 4 vai trò (RBAC), quản lý phiên đăng nhập và bảo mật tệp đính kèm.

*(Chi tiết đặc tả tính năng của từng phân hệ được mô tả tại thư mục `03-modules/`)*.

## 2. Giới hạn phạm vi (Out of Scope / Non-Goals)
Để đảm bảo tiến độ triển khai trong 22 tuần, dự án KHÔNG bao gồm các hạng mục sau:
* Thiết kế lại hoặc can thiệp vào quy trình nghiệp vụ hành chính nội bộ của Aurora University.
* Cung cấp, nâng cấp phần cứng, máy chủ vật lý hoặc hạ tầng mạng.
* Phát triển ứng dụng Native Mobile App (iOS/Android).
* Tích hợp đăng nhập một lần (SSO) hoặc tích hợp API với các hệ thống phần mềm thứ ba khác.
* Xây dựng các tính năng Trí tuệ nhân tạo (AI/ML) hoặc Chatbot trả lời tự động.
* Thu thập, làm sạch và chuyển đổi (Migration) toàn bộ dữ liệu lịch sử từ các kênh cũ (Email, Excel) vào hệ thống mới.
* Vận hành dài hạn sau bàn giao (ngoài thời gian bảo hành quy định).

## 3. Giả định dự án (Assumptions)
* Aurora University cung cấp đầy đủ yêu cầu nghiệp vụ, luồng xử lý và dữ liệu danh mục đúng thời hạn.
* Đại diện khách hàng tham gia phản hồi và phê duyệt đúng theo lịch trình chốt Requirement (Sprint Review) và UAT.
* Mọi yêu cầu phát sinh tính năng mới ngoài phần In-Scope bắt buộc phải thực hiện quy trình Quản lý thay đổi (Change Request) để đánh giá lại Timeline, Chi phí và Nguồn lực trước khi đưa vào phát triển.
