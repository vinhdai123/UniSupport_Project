# QUALITY MANAGEMENT
**UNISUPPORT - STUDENT SUPPORT MANAGEMENT SYSTEM**

---

## 1. TỔNG QUAN QUẢN LÝ CHẤT LƯỢNG

### 1.1. Mục đích
Tài liệu Quản lý chất lượng xác định các tiêu chí và hoạt động nhằm đảm bảo UniSupport đáp ứng yêu cầu đã thống nhất, hoạt động ổn định và phù hợp với nhu cầu sử dụng tại Aurora University.

### 1.2. Phạm vi áp dụng
Hoạt động quản lý chất lượng được thực hiện xuyên suốt quá trình phân tích yêu cầu, thiết kế, phát triển, kiểm thử và chuẩn bị phát hành UniSupport. Nội dung tập trung vào sản phẩm thuộc phạm vi Release 1.0 của dự án.

### 1.3. Nguyên tắc quản lý chất lượng
* Xem xét chất lượng ngay từ giai đoạn xác định và rà soát yêu cầu, không chỉ ở bước kiểm thử cuối cùng.
* Phòng ngừa sai lệch thông qua rà soát yêu cầu, thiết kế và quá trình phát triển.
* Kiểm tra sản phẩm dựa trên yêu cầu và Acceptance Criteria đã thống nhất.
* Ghi nhận, phân loại, phân công và theo dõi lỗi đến khi có kết quả xử lý.
* Phát hành và nghiệm thu dựa trên kết quả kiểm thử và xác nhận của các bên có thẩm quyền.

---

## 2. MỤC TIÊU VÀ TIÊU CHÍ CHẤT LƯỢNG

### 2.1. Mục tiêu chất lượng
* Đảm bảo chức năng được triển khai đúng yêu cầu và phạm vi đã thống nhất.
* Đảm bảo giao diện dễ hiểu, thuận tiện cho các nhóm người dùng.
* Kiểm soát quyền truy cập đối với dữ liệu và chức năng của hệ thống.
* Đảm bảo hệ thống hoạt động ổn định và có hiệu suất phù hợp với yêu cầu sử dụng.
* Đảm bảo khả năng sử dụng trên Desktop và Mobile, hỗ trợ Tiếng Việt và Tiếng Anh.

### 2.2. Tiêu chí đánh giá chất lượng

| Tiêu chí | Nội dung đánh giá |
| :--- | :--- |
| **Functional Quality** | Các chức năng hoạt động đúng theo yêu cầu và Acceptance Criteria đã thống nhất. |
| **Usability** | Giao diện rõ ràng, dễ hiểu và thuận tiện cho người dùng. |
| **Security** | Dữ liệu và chức năng được kiểm soát theo quyền truy cập. |
| **Reliability** | Hệ thống hoạt động ổn định trong điều kiện sử dụng đã thống nhất. |
| **Performance** | Hiệu suất đáp ứng yêu cầu sử dụng của hệ thống. |
| **Compatibility** | Hỗ trợ sử dụng trên Desktop và Mobile. |
| **Localization** | Hỗ trợ Tiếng Việt và Tiếng Anh. |

---

## 3. ĐẢM BẢO CHẤT LƯỢNG (QUALITY ASSURANCE – QA)

Quality Assurance tập trung vào việc phòng ngừa lỗi và đảm bảo các hoạt động phát triển được thực hiện theo yêu cầu, thiết kế và định hướng đã thống nhất.

### 3.1. Requirement Review – Rà soát yêu cầu
Rà soát yêu cầu nhằm kiểm tra tính rõ ràng, đầy đủ và nhất quán của thông tin nghiệp vụ trước khi triển khai. Các nội dung chưa rõ cần được trao đổi và xác nhận với Aurora University.

### 3.2. Design Review – Rà soát thiết kế
Đánh giá thiết kế hệ thống và giao diện để đảm bảo phù hợp với yêu cầu nghiệp vụ, luồng sử dụng và nhóm người dùng mục tiêu.

### 3.3. Development Review - Rà soát quá trình phát triển
Theo dõi và rà soát quá trình phát triển nhằm phát hiện sớm sai lệch so với yêu cầu và thiết kế đã thống nhất. Các vấn đề được ghi nhận để điều chỉnh trước khi chuyển sang các hoạt động kiểm thử tiếp theo.

---

## 4. KIỂM SOÁT CHẤT LƯỢNG (QUALITY CONTROL – QC)

Quality Control tập trung vào việc kiểm tra sản phẩm thực tế, phát hiện lỗi và đánh giá mức độ đáp ứng các yêu cầu đã thống nhất.

### 4.1. Testing – Kiểm thử
* **Functional Testing:** Kiểm tra hoạt động của các chức năng theo yêu cầu.
* **Integration Testing:** Kiểm tra khả năng phối hợp giữa các thành phần trong hệ thống.
* **Security Testing:** Kiểm tra các nội dung liên quan đến quyền truy cập và bảo vệ dữ liệu.

### 4.2. User Acceptance Testing (UAT)
Đại diện Aurora University thực hiện kiểm tra các luồng nghiệp vụ và chức năng để đánh giá mức độ đáp ứng nhu cầu thực tế. Kết quả UAT được ghi nhận làm cơ sở cho việc hoàn thiện và nghiệm thu sản phẩm.

### 4.3. Bảng Cổng Kiểm soát Chất lượng theo Milestone (Milestone Quality Gates)
Hoạt động QA/QC được gắn chặt với 4 mốc bàn giao chính (M1-M4) của dự án để đảm bảo không dồn áp lực kiểm thử vào cuối kỳ:

| Cột mốc Milestone | Trọng tâm Hoạt động Kiểm soát Chất lượng | Bằng chứng & Đầu ra Chất lượng bắt buộc |
| :--- | :--- | :--- |
| **M1 - Design & Spec Gate** | • Review tính nhất quán giữa PRD và System Architecture.<br>• Usability Walkthrough trên Figma UI/UX Prototype. | • Biên bản Requirement & Design Review.<br>• Ma trận Truy xuất Yêu cầu khởi tạo.<br>• 0% Lỗi Critical và High tồn đọng. |
| **M2 - System Quality Gate** | • Integration Testing cho toàn bộ 6 Phân hệ DEV.<br>• Security & RBAC Testing.<br>• Smoke Testing & Regression Testing. | • Báo cáo Kết quả Kiểm thử Hệ thống. |
| **M3 - UAT & Acceptance Gate** | • Hỗ trợ Đại diện Aurora University thực hiện User Acceptance Testing.<br>• Verification các lỗi phát sinh trong UAT. | • Biên bản nghiệm thu UAT có xác nhận của Aurora University. |
| **M4 - Production Release Gate** | • Final Smoke Test trên môi trường Production thật của nhà trường.<br>• Rà soát Hồ sơ Chuyển giao & Tài liệu Hướng dẫn Sử dụng. | • Biên bản Bàn giao & Kích hoạt thời gian Bảo hành phần mềm. |

### 4.4. Cấu hình Môi trường Kiểm thử & Quy định Dữ liệu Test
* **Môi trường Kiểm thử:**
  * **Local/Dev Environment:** Môi trường phát triển của lập trình viên, dùng để chạy Unit Test và kiểm tra chức năng đơn lẻ.
  * **Staging Environment:** Môi trường giả lập giống 99% môi trường Production của Aurora University, dùng để thực hiện Integration Testing, Security Testing và UAT.
* **Quy định Dữ liệu Kiểm thử:**
  * Tuyệt đối không sử dụng dữ liệu thực của 3.000 sinh viên Aurora University trong quá trình Dev/Test nhằm tuân thủ Luật Bảo vệ Dữ liệu cá nhân.
  * Đội QA chịu trách nhiệm khởi tạo **Bộ dữ liệu giả lập** trên Staging gồm: 4 bộ tài khoản đại diện cho 4 vai trò (Student, Staff, Manager, Admin); 50 Ticket mẫu bao phủ đầy đủ các trạng thái, loại danh mục và các mức độ SLA.

### 4.5. Tiêu chuẩn Code Review & Quy định Đóng gói
* **Quy trình Code Review:** 100% Pull Request từ Developer bắt buộc phải có sự review và phê duyệt của Technical Lead trước khi được merge vào nhánh chính.
* **Tiêu chuẩn Code Coverage:** Các mô-đun nghiệp vụ cốt lõi (Xác thực Auth, Routing Ticket, Tính toán SLA) bắt buộc phải đạt tối thiểu 80% Code Coverage thông qua Unit Test tự động.

---

## 5. QUẢN LÝ LỖI (DEFECT MANAGEMENT)

Mọi lỗi phát sinh trong quá trình phát triển và kiểm thử cần được ghi nhận, phân loại, phân công và theo dõi đến khi hoàn tất.

### 5.1. Phân loại mức độ nghiêm trọng (Severity)

| Mức độ | Mô tả |
| :--- | :--- |
| **Critical** | Ảnh hưởng nghiêm trọng đến hệ thống hoặc chức năng cốt lõi. |
| **High** | Ảnh hưởng lớn đến chức năng hoặc người dùng. |
| **Medium** | Có ảnh hưởng nhưng vẫn tồn tại phương án thay thế. |
| **Low** | Lỗi nhỏ, ít ảnh hưởng đến quá trình sử dụng. |

### 5.2. Quy trình xử lý lỗi
`Record` ➔ `Classify` ➔ `Assign` ➔ `Investigate` ➔ `Resolve` ➔ `Verify` ➔ `Close`

*Cần phân biệt Severity (mức độ nghiêm trọng và ảnh hưởng của lỗi) với Priority (mức độ ưu tiên cần xử lý). Hai khái niệm này hỗ trợ việc đánh giá tác động và sắp xếp thứ tự xử lý.*

### 5.3. Theo dõi kết quả xử lý
* Lỗi cần có thông tin mô tả và kết quả kiểm tra để phục vụ việc xác minh.
* Lỗi sau khi khắc phục cần được kiểm tra lại trước khi đóng.
* Các lỗi chưa được xử lý tại thời điểm phát hành phải được ghi nhận và thông báo cho các bên liên quan.

---

## 6. ĐIỀU KIỆN PHÁT HÀNH VÀ NGHIỆM THU

Trước khi bàn giao UniSupport, cần rà soát các điều kiện sau:
* Các chức năng thuộc phạm vi dự án đã hoàn thành.
* Các chức năng đáp ứng Acceptance Criteria đã thống nhất.
* Các lỗi nghiêm trọng đã được xử lý.
* Kết quả kiểm thử được ghi nhận.
* Tài liệu hướng dẫn và tài liệu kỹ thuật đã được chuẩn bị.
* Các vấn đề còn tồn tại được thông báo cho Aurora University.
* Có xác nhận nghiệm thu từ người có thẩm quyền.

---

## 7. PHỐI HỢP THỰC HIỆN

Hoạt động quản lý chất lượng cần có sự phối hợp giữa đội dự án và đại diện Aurora University. Đội dự án thực hiện rà soát, kiểm thử, ghi nhận và xử lý lỗi theo phân công; đại diện nhà trường tham gia xác nhận yêu cầu nghiệp vụ, UAT và nghiệm thu.

Các hoạt động theo dõi chất lượng sau thời gian bảo hành hoặc trong giai đoạn vận hành lâu dài cần được xác định theo thỏa thuận riêng, không mặc nhiên thuộc phạm vi bàn giao hiện tại.