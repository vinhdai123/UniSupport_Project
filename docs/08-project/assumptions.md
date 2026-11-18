# Giả định

Bảng theo dõi A-01 đến A-07 trong tình huống **Mô phỏng**. Nội dung cam kết đối chiếu với [Proposal](proposal.docx), mục 3 và 6. PM/BA lưu bằng chứng xác minh trong Issue và theo dõi điểm còn mở tại [Câu hỏi mở](open-questions.md).

| Mã | Nội dung | Ảnh hưởng | Trạng thái |
| --- | --- | --- | --- |
| `A-01` | Vòng đời Ticket đáp ứng quy trình hỗ trợ. Khác biệt giữa các phòng ban xử lý được bằng cấu hình danh mục, quyền, phân luồng và thời hạn. | Nếu phải đổi quy trình hoặc phát triển thêm chức năng, đánh giá lại phạm vi và effort. | Chờ xác minh quy trình khi khảo sát |
| `A-02` | Nhà trường cung cấp đầu vào nghiệp vụ và dữ liệu cấu hình trước việc phụ thuộc. Luồng đăng nhập và tài khoản thử MS-01 dự kiến chốt cuối tuần 2. | Đầu vào chậm có thể dời phân tích, cấu hình và tích hợp MS-01. | Chờ xác nhận đầu vào và tài khoản thử |
| `A-03` | Đầu mối trường tổng hợp ý kiến và phản hồi tài liệu phân tích, thiết kế trong 3 ngày làm việc từ khi nhận đủ. Nghiệm thu theo mục 8 Proposal. | Phản hồi chậm ảnh hưởng thiết kế và công việc phụ thuộc. | Chờ xác nhận đầu mối và khả dụng |
| `A-04` | Quy mô dự kiến khoảng 3.000 sinh viên và bốn nhóm vai trò. Tải đồng thời, dung lượng dữ liệu và cấu hình phục vụ xác định khi khảo sát tại MS-01. | Quy mô khác giả định có thể ảnh hưởng cấu hình, kiểm hiệu năng và giá. | Chờ chốt tải và dung lượng trong PRD |
| `A-05` | Staging dự kiến sẵn sàng tuần 3, Production từ đầu tuần 21. Email hỗ trợ kết nối tiêu chuẩn và quyền được cấp theo lịch tích hợp. | Thiếu môi trường hoặc quyền làm chậm tích hợp, UAT hoặc Go-live. | Chờ xác nhận môi trường, Email và quyền |
| `A-06` | Sau MS-01, quy trình Ticket, ma trận quyền và quy tắc nghiệp vụ đã xác nhận dự kiến ổn định trong đợt phát triển. | Thay đổi có thể phát sinh làm lại và kiểm hồi quy. Đánh giá CR nếu đổi cam kết. | Chờ xác nhận phạm vi tại MS-01 |
| `A-07` | Đại diện nghiệp vụ và vận hành có thể tham gia UAT, xác nhận kết quả và đào tạo trong tuần 21–22. | Thiếu người tham gia có thể dời quyết định sẵn sàng Go-live tại MS-07. | Chờ xác nhận đại diện và lịch UAT |
