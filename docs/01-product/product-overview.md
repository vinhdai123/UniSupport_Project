# TỔNG QUAN SẢN PHẨM (PRODUCT OVERVIEW)

> **Sản phẩm:** UniSupport – Student Support Management System  
> **Khách hàng:** Aurora University  
> **Tài liệu cha:** README.md

---

## 1. Bối cảnh và Bài toán (Context & Problem Statement)

Aurora University hiện có quy mô khoảng 3.000 sinh viên. Hiện tại, các yêu cầu hỗ trợ học vụ, tài chính, và sinh hoạt đang được tiếp nhận qua nhiều kênh phân tán như email, điện thoại hoặc gặp trực tiếp. 

**Vấn đề gặp phải:**
* **Thiếu tập trung:** Quá trình tiếp nhận, phân loại và theo dõi yêu cầu bị rời rạc, dẫn đến tình trạng thất lạc thông tin.
* **Quá tải cục bộ:** Trong các giai đoạn cao điểm (đầu năm học, kỳ thi), cán bộ gặp khó khăn trong việc kiểm soát khối lượng công việc và thời hạn xử lý (deadline).
* **Thiếu minh bạch:** Sinh viên không biết yêu cầu của mình đang ở khâu nào, do ai xử lý. Nhà trường thiếu dữ liệu tổng hợp để đánh giá hiệu suất của các phòng ban.

## 2. Giải pháp Đề xuất (Proposed Solution)

**UniSupport** được xây dựng nhằm cung cấp một cổng dịch vụ một cửa (One-stop Support Portal) tập trung hóa toàn bộ luồng tiếp nhận và xử lý yêu cầu hỗ trợ. 

**Giá trị cốt lõi mang lại:**
* **Với Sinh viên:** Cung cấp kênh duy nhất để tạo Ticket, tra cứu hướng dẫn (FAQ), theo dõi tiến độ xử lý theo thời gian thực và trao đổi trực tiếp với cán bộ.
* **Với Nhà trường:** Chuẩn hóa luồng phân công công việc (Routing), số hóa quy trình quản lý thời hạn (SLA), và cung cấp hệ thống Báo cáo/Dashboard trực quan để đo lường hiệu suất vận hành của từng phòng ban.

---

## 3. Chân dung Người dùng (User Personas)

Hệ thống được thiết kế để phục vụ 04 nhóm người dùng chính:

1. **Sinh viên (Student):** Người dùng cuối. Gặp khó khăn trong việc tìm đúng đầu mối hỗ trợ. Cần một công cụ để gửi yêu cầu nhanh chóng, đính kèm minh chứng và biết chính xác khi nào vấn đề của mình được giải quyết.
2. **Cán bộ xử lý (Staff):** Nhân viên các phòng ban (Đào tạo, CTSV, Kế toán...). Cần một không gian làm việc tập trung để quản lý danh sách Ticket được phân công, tránh bỏ sót công việc và dễ dàng phản hồi cho sinh viên theo các mẫu chuẩn.
3. **Quản lý phòng ban (Manager):** Trưởng/Phó phòng. Cần công cụ giám sát tổng khối lượng công việc (Workload), lượng Ticket tồn đọng (Backlog), quản lý thời hạn xử lý để kịp thời điều chuyển nhân sự.
4. **Quản trị viên (System Admin):** Cán bộ IT. Chịu trách nhiệm thiết lập và duy trì hệ thống, quản lý tài khoản, phân quyền, cấu hình danh mục và các quy tắc phân luồng tự động (Routing Rules).

---

## 4. Chỉ số Đo lường Thành công (Success Metrics)

Mức độ thành công của sản phẩm sau khi Go-live sẽ được đánh giá qua các chỉ số định lượng (KPIs) sau:

* **Tỷ lệ hoàn thành (Completion Rate):** Tỷ lệ Ticket được giải quyết đóng so với tổng Ticket tiếp nhận.
* **Tỷ lệ quá hạn (Overdue Rate):** Số lượng Ticket vi phạm cam kết thời gian xử lý (SLA).
* **Thời gian giải quyết trung bình (MTTR):** Thời gian trung bình từ lúc sinh viên tạo yêu cầu đến lúc hoàn thành.
* **Khối lượng tồn đọng (Backlog):** Số lượng Ticket chưa được xử lý tồn đọng qua các chu kỳ.
* **Chỉ số hài lòng (CSAT):** Điểm đánh giá trung bình của sinh viên sau khi nhận được kết quả hỗ trợ.

---

## 5. Giới hạn Phạm vi Dự án (Out of Scope)

Để đảm bảo tiến độ và chất lượng trong giới hạn 22 tuần phát triển, phiên bản hiện tại của UniSupport **KHÔNG** bao gồm các hạng mục sau:

* Thiết kế lại hoặc can thiệp vào quy trình nghiệp vụ nội bộ của Aurora University.
* Cung cấp, thiết lập hoặc nâng cấp hạ tầng phần cứng, mạng, máy chủ vật lý.
* Phát triển ứng dụng di động gốc (Native Mobile App). Web app sẽ được thiết kế Responsive để dùng trên di động.
* Tích hợp đăng nhập một lần (SSO) hoặc tích hợp với các hệ thống phần mềm thứ ba khác của trường.
* Xây dựng các tính năng Trí tuệ nhân tạo (AI/ML) hoặc Chatbot tự động.
* Thu thập, làm sạch và chuyển đổi (Migration) dữ liệu lịch sử từ các kênh cũ vào hệ thống mới.
