# Nghiệp vụ miền (Domain Model & Rules)

<!-- Hướng dẫn: phần này dùng làm bằng chứng cho PRD, effort và rủi ro. Giúp đội ngũ phát triển và các bên liên quan hiểu rõ nghiệp vụ cốt lõi của UniSupport. -->

Thư mục này đặc tả chi tiết các yếu tố nghiệp vụ miền của hệ thống **UniSupport**:

- [Thuật ngữ nghiệp vụ (Terminology & Glossary)](terminology.md): Định nghĩa chuẩn hóa các khái niệm: Ticket, SLA, Category, CSAT, Internal Notes, Escalation...
- [Quy tắc nghiệp vụ (Business Rules)](business-rules.md): Các quy định ràng buộc về quyền truy cập, quyền gán việc, tính toán thời hạn SLA, điều kiện đóng Ticket và tính toán tỷ lệ tuân thủ.
- [Chuyển trạng thái (State Transition)](state-transition.md): Sơ đồ vòng đời và ma trận chuyển đổi các trạng thái Ticket (`Open` ➔ `In Progress` ➔ `Pending Info` ➔ `Resolved` ➔ `Closed`).
