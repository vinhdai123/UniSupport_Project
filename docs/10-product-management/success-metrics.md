# Chỉ số giá trị (Success Metrics & KPIs)

<!-- Hướng dẫn: chỉ số đo giá trị cho người dùng/khách, có mục tiêu và cách đo. -->

Tài liệu này xác định các chỉ số đo lường giá trị thực tế mà hệ thống **UniSupport** mang lại cho Aurora University về mặt vận hành, chất lượng dịch vụ và trải nghiệm sinh viên.

---

## 1. Bảng Chỉ số Giá trị Vận hành

| Chỉ số | Mục tiêu | Cách đo | Tần suất | Ai theo dõi |
| --- | --- | --- | --- | --- |
| **Tỷ lệ tiếp nhận tập trung (Adoption Rate)** | $\ge 80\%$ sinh viên kích hoạt trong 3 tháng đầu; $100\%$ cán bộ xử lý | $\frac{\text{Số User đăng nhập sử dụng}}{\text{Tổng số User được cấp tài khoản}} \times 100\%$ | Hằng tháng | Product Manager & Phòng CTSV |
| **Thời gian phản hồi đầu tiên (First Response Time - FRT)** | $\le 4$ giờ làm việc cho mọi Ticket tiếp nhận | Thời gian từ lúc Ticket tạo thành công đến khi cán bộ có phản hồi đầu tiên | Hằng tuần | Trưởng phòng ban & Cán bộ xử lý |
| **Tỷ lệ tuân thủ cam kết SLA (SLA Compliance Rate)** | $\ge 90\%$ Ticket được xử lý và hoàn tất đúng hạn cam kết | $\frac{\text{Số Ticket hoàn thành đúng hạn SLA}}{\text{Tổng số Ticket đã xử lý}} \times 100\%$ | Hằng tuần / Hằng tháng | Trưởng phòng ban & Ban giám hiệu |
| **Tỷ lệ Ticket mở lại (Reopened Ticket Rate)** | $\le 5\%$ tổng số Ticket đã đóng | $\frac{\text{Số Ticket bị Reopen}}{\text{Tổng số Ticket đã Resolved}} \times 100\%$ | Hằng tháng | QA Lead & Trưởng phòng ban |
| **Độ hài lòng của sinh viên (CSAT Score)** | $\ge 4.2 / 5.0$ điểm đánh giá trung bình | Điểm đánh giá sao trung bình trên khảo sát sau khi hoàn tất Ticket | Thời gian thực / Báo cáo tuần | Trưởng phòng ban & Product Manager |
| **Độ ổn định hệ thống (System Availability)** | $\ge 99.5\%$ trong khung giờ hành chính (07:00 – 19:00) | $\frac{\text{Thời gian hệ thống hoạt động bình thường}}{\text{Tổng thời gian vận hành yêu cầu}} \times 100\%$ | Hằng tháng | DevOps Engineer & Technical Lead |

---

## 2. Bảng Cam kết Thời gian Xử lý Dịch vụ (SLA Reference)

| Mức độ ưu tiên | Định nghĩa | Cam kết thời gian xử lý đề xuất |
| --- | --- | --- |
| **Urgent (Khẩn cấp)** | Vấn đề đình chỉ học tập, sai sót học phí giờ chót, sự cố đăng ký môn thi | $\le 4$ giờ làm việc |
| **High (Cao)** | Yêu cầu giấy tờ xác nhận gấp, thủ tục tốt nghiệp, khiếu nại điểm | $\le 12$ giờ làm việc |
| **Medium (Bình thường)** | Xin cấp bảng điểm, xác nhận sinh viên, hướng dẫn học phần thông thường | $\le 24$ giờ làm việc |
| **Low (Thấp)** | Góp ý chung, tư vấn hoạt động ngoại khóa, câu lạc bộ | $\le 48$ giờ làm việc |
