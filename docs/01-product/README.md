# Tổng quan sản phẩm (Product Overview)

<!-- Hướng dẫn: phần mở đầu của PRD. Ngắn, cụ thể, đủ để người đọc hiểu vì sao làm và làm cho ai. -->

Tài liệu này tổng hợp bối cảnh, bài toán, đối tượng sử dụng, mục tiêu và phạm vi của hệ thống **UniSupport - Student Support Management System** dành cho Aurora University trong tình huống **Mô phỏng**.

Các nguồn để tra cứu chi tiết gồm
- [Bài toán thực tế](problem-statement.md)
- [Đối tượng & Phân vai](actors-and-roles.md)
- [Mục tiêu có mã BG/UG và giới hạn NG](goals-and-non-goals.md)
- [Phạm vi cam kết trong Proposal](../08-project/proposal.docx)
- [Phạm vi chi tiết phục vụ PRD](product-scope.md)
- [Bản mô tả tổng quan sản phẩm](product-overview.md)

---

## Vấn đề

Tại Aurora University, quy trình tiếp nhận và xử lý yêu cầu hỗ trợ của sinh viên hiện đang gặp các trở ngại lớn:
1. **Kênh tiếp nhận phân tán:** Yêu cầu gửi qua email cá nhân, biểu mẫu rải rác hoặc gặp trực tiếp, dễ thất lạc thông tin.
2. **Thiếu minh bạch:** Sinh viên không theo dõi được ai đang xử lý, trạng thái và thời gian hoàn thành dự kiến.
3. **Quá tải và khó kiểm soát:** Cán bộ tiếp nhận trùng lặp nhiều câu hỏi phổ biến; cấp quản lý thiếu số liệu đo lường khối lượng và chất lượng cam kết (SLA).

Chi tiết: [problem-statement.md](problem-statement.md)

---

## Actor

| Actor | Là ai | Cần gì từ hệ thống |
| --- | --- | --- |
| **Student** | Sinh viên trường Đại học Aurora | Gửi yêu cầu hỗ trợ tập trung, theo dõi tiến độ, nhận thông báo, tra cứu FAQ và đánh giá CSAT. |
| **Staff** | Cán bộ hỗ trợ thuộc các phòng ban (Đào tạo, CTSV, Kế toán...) | Xem danh sách Ticket phân công, xử lý, trao đổi với sinh viên, cập nhật trạng thái và chuyển tiếp phòng ban. |
| **Manager** | Trưởng bộ phận / Trưởng phòng ban | Theo dõi hiệu suất phòng ban, tỷ lệ tuân thủ SLA, khối lượng Ticket và duyệt các trường hợp chuyển tiếp/khiếu nại. |
| **Administrator** | Quản trị viên hệ thống của Aurora University | Quản lý người dùng, phân quyền vai trò (RBAC), cấu hình danh mục Ticket và thiết lập cam kết SLA. |

Chi tiết: [actors-and-roles.md](actors-and-roles.md)

---

## Goals

- **Tập trung hóa:** Tiếp nhận và theo dõi yêu cầu hỗ trợ thuộc phạm vi UniSupport qua một cổng tập trung. Xem [BG-01](goals-and-non-goals.md#bg-01--quản-lý-tập-trung-yêu-cầu-hỗ-trợ).
- **Minh bạch hóa:** Cung cấp mã định danh Ticket và trạng thái tiến độ thời gian thực cho sinh viên.
- **Tự động hóa & Kiểm soát SLA:** Tự động phân luồng yêu cầu tới đúng phòng ban chuyên trách và cảnh báo vi phạm cam kết thời gian giải quyết.
- **Quản trị bằng dữ liệu:** Cung cấp Dashboard đo lường khối lượng, tỷ lệ giải quyết đúng hạn và độ hài lòng (CSAT).

Chi tiết: [goals-and-non-goals.md](goals-and-non-goals.md)

---

## Non-goals

<!-- Hướng dẫn: những gì dự án KHÔNG làm. Phạm vi trong PRD phải khớp với goals và non-goals. -->

- **Không xây dựng Ứng dụng di động Native (Native Mobile App):** Hệ thống chỉ triển khai bản Web Responsive (Desktop & Mobile Web).
- **Không tích hợp tổng đài VoIP / Hotline gọi điện trực tiếp:** Tiếp nhận qua Ticket trên cổng thông tin, không tích hợp tổng đài thoại tự động.
- **Không thay thế Cổng đào tạo / Cổng đăng ký tín chỉ hiện có:** UniSupport là hệ thống tiếp nhận và giải quyết yêu cầu hỗ trợ, không can thiệp trực tiếp vào cơ sở dữ liệu xếp lớp hoặc thu học phí tự động.
- **Không can thiệp vào quy trình nghiệp vụ nội bộ độc quyền ngoài hệ thống:** Việc ra quyết định chuyên môn nội bộ vẫn thuộc thẩm quyền của Aurora University.

Tra [Non-goals có mã](goals-and-non-goals.md#2-mục-tiêu-ngoài-phạm-vi-non-goals) và phần Out-of-Scope trong [Proposal](../08-project/proposal.docx) để đối chiếu phạm vi cam kết.
