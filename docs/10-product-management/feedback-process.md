# Quy trình tiếp nhận và xử lý feedback (Feedback Process)

Tài liệu này quy định quy trình thu thập, phân loại, đánh giá và định tuyến các ý kiến phản hồi về hệ thống **UniSupport**.

---

## Kênh nhận feedback

1. **Khảo sát CSAT tự động (In-App CSAT Survey):** Hiển thị ngay sau khi Ticket được chuyển sang trạng thái `Resolved` để sinh viên đánh giá 1-5 sao và để lại nhận xét.
2. **Biểu mẫu góp ý trực tiếp trên hệ thống (In-App Feedback Form):** Dành cho cả sinh viên và cán bộ gửi ý kiến đóng góp về giao diện, tính năng hoặc hiệu năng.
3. **Các buổi Review và Demo cột mốc:** Thu thập ý kiến trực tiếp từ đại diện các phòng ban Aurora University tại các mốc MS-01, MS-06, MS-07.
4. **Kênh tiếp nhận sự cố khẩn cấp:** Hotline hoặc kênh trao đổi kỹ thuật dành riêng cho quản trị viên nhà trường khi có sự cố nghiêm trọng.

---

## Phân loại và Ma trận Định tuyến

Các phản hồi tiếp nhận được phân loại thành 5 nhóm chính và xử lý theo ma trận:

| Loại phản hồi | Kênh tiếp nhận | Đơn vị chịu trách nhiệm | Mẫu Issue / Quy trình xử lý |
| :--- | :--- | :--- | :--- |
| **Lỗi kỹ thuật (Bug)** | In-App Form, Báo cáo kiểm thử | QA Lead & Dev Team | Sử dụng GitHub Issue mẫu `2-bug.md`. Phân loại Severity và sửa trong Sprint. |
| **Trải nghiệm UI/UX** | Đánh giá khảo sát, Phỏng vấn người dùng | PM & UI/UX Designer | Đưa vào UX Improvement Backlog; cải tiến tại các phiên bản Release 1.x. |
| **Đề xuất tính năng (Feature Request)** | Form góp ý, Cuộc họp định kỳ | Product Manager / BA | Sử dụng GitHub Issue mẫu `3-feedback.md`. Nếu làm thay đổi phạm vi đã duyệt thì chuyển sang quy trình Change Request (`4-change-request.md`). |
| **Khiếu nại nghiệp vụ dịch vụ** | Khảo sát CSAT $\le$ 2 sao | Trưởng phòng ban liên quan | Hệ thống tự động gắn cờ gửi Trưởng phòng ban nhà trường để rà soát nghiệp vụ nội bộ của cán bộ xử lý. |
| **Sự cố vận hành khẩn cấp** | Cảnh báo tự động, Hotline | DevOps & Tech Lead | Xử lý theo quy trình phản ứng sự cố khẩn cấp, khắc phục trong 30–60 phút. |

---

## Ưu tiên

Tiêu chí đánh giá mức độ ưu tiên do **Product Manager** chủ trì sắp xếp dựa trên 3 tiêu chí:
1. **Giá trị mang lại (Value):** Mức độ tháo gỡ điểm nghẽn cho sinh viên và nhà trường.
2. **Tác động (Impact):** Số lượng người dùng bị ảnh hưởng.
3. **Tính khả thi & Nguồn lực (Effort/Feasibility):** Thời gian và chi phí kỹ thuật cần thiết.

Thang ưu tiên:
- **P1 (High):** Các cải tiến quan trọng về luồng xử lý và Dashboard ảnh hưởng trực tiếp đến cam kết vận hành.
- **P2 (Medium):** Nâng cấp tra cứu FAQ, mở rộng bộ mẫu câu trả lời nhanh cho cán bộ.
- **P3 (Low):** Tùy biến giao diện nâng cao, báo cáo phụ trợ.

---

## Ai quyết định sau bàn giao

- **Trong thời gian bảo hành (30 ngày sau Go-Live):** Đội ngũ dự án tiếp nhận và khắc phục miễn phí các lỗi phát sinh thuộc phạm vi hợp đồng Release 1.0. Quyết định khắc phục do PM và Technical Lead đưa ra.
- **Sau thời gian bảo hành:** Đơn vị quản trị hệ thống thuộc Aurora University tiếp nhận toàn quyền vận hành. Các yêu cầu phát triển tính năng mới hoặc nâng cấp lớn sẽ được thực hiện theo thỏa thuận dịch vụ phát triển mới giữa hai bên.
