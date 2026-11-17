# Sổ rủi ro (Risk Register)

<!-- Hướng dẫn: ưu tiên rủi ro phần mềm thật của dự án (tích hợp, dữ liệu, hiệu năng, phụ thuộc bên ngoài, thiếu người), không chỉ rủi ro chung chung. Mỗi rủi ro có owner cụ thể. -->

| Mã | Mô tả | Khả năng (1–5) | Tác động (1–5) | Owner | Phương án xử lý | Trạng thái | Liên quan |
| --- | --- | :---: | :---: | --- | --- | --- | --- |
| `R-01` | **Thay đổi phạm vi:** Phát sinh yêu cầu ngoài In-Scope làm tăng khối lượng và kéo dài tiến độ | 3 | 4 | Project Manager | Khóa phạm vi từ Milestone M1; xử lý nghiêm ngặt qua quy trình Change Request và tính phí/gia hạn phát sinh nếu duyệt | Mở | Toàn dự án, `MS-01` |
| `R-02` | **Chậm phản hồi từ khách hàng:** Aurora University chậm phê duyệt đặc tả hoặc UAT làm chậm đường găng | 3 | 4 | Project Manager | Thống nhất lịch làm việc trước 1 tuần; quy định rõ thời hạn phản hồi tối đa (3-5 ngày làm việc) trong hợp đồng | Mở | `MS-01`, `MS-03` |
| `R-03` | **Xung đột nghiệp vụ:** Quy trình tiếp nhận giữa các phòng ban (Đào tạo, CTSV, Kế toán) có điểm khác biệt | 3 | 3 | BA / PM | Khảo sát kỹ tại giai đoạn M1; chuẩn hóa cấu hình linh hoạt cho từng phòng ban trong Module M04 | Mở | `M03`, `M04` |
| `R-04` | **Biến động nhân sự:** Developer hoặc QA chủ chốt nghỉ ốm hoặc chuyển công tác | 2 | 4 | Tech Lead | Phân công cặp làm việc (Pair programming/Senior-Junior); duy trì tài liệu kiến trúc và tài liệu API rõ ràng | Mở | `MS-02` |
| `R-05` | **Hạ tầng Staging/Prod:** Cấu hình mạng hoặc bảo mật nội bộ của trường gây chậm trễ cài đặt | 2 | 3 | DevOps Engineer | Khảo sát thông số hạ tầng từ Tuần 4; chuẩn bị sẵn kịch bản Docker container hóa để triển khai nhanh | Mở | `MS-03`, `MS-04` |
| `R-06` | **Lỗi tồn đọng nghiêm trọng:** Phát hiện lỗi Critical/High muộn sát ngày bàn giao | 2 | 4 | QA Lead | Áp dụng Milestone Quality Gates; kiểm thử liên tục (CI), regression test trước mỗi mốc bàn giao | Mở | `MS-02`, `MS-03` |
| `R-07` | **Chậm nghiệm thu UAT:** Người dùng Aurora University bận việc hành chính, không tham gia test đúng lịch | 3 | 3 | Project Manager | Lên kế hoạch test chi tiết; tổ chức workshop tập trung có hỗ trợ trực tiếp từ đội dự án tại Tuần 21 | Mở | `MS-03` |
