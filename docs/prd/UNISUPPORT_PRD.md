# TÀI LIỆU YÊU CẦU SẢN PHẨM (PRD)

> **Trạng thái tài liệu:** Bản nháp  
> **Cập nhật lần cuối:** 02/10/2026  
> **Sản phẩm:** UniSupport – Hệ thống Quản lý Yêu cầu Hỗ trợ Sinh viên  
> **Khách hàng:** Aurora University  
> **Product Manager / BA:** TBD  
> **Người đóng góp:** Project Team

---

## 1. Tóm tắt điều hành

### 1.1. Tên sản phẩm

**UniSupport – Student Support Management System**

### 1.2. Vấn đề cần giải quyết

Aurora University có khoảng 3.000 sinh viên, trong khi các yêu cầu hỗ trợ hiện được tiếp nhận qua nhiều kênh khác nhau như email và điện thoại. Việc này khiến quá trình tiếp nhận, phân loại, theo dõi và xử lý yêu cầu thiếu tập trung, đặc biệt trong các giai đoạn cao điểm.

Nhà trường cần một hệ thống thống nhất để quản lý toàn bộ yêu cầu hỗ trợ, giúp sinh viên theo dõi tiến độ và hỗ trợ cán bộ kiểm soát khối lượng công việc, thời hạn xử lý và hiệu suất.

### 1.3. Giải pháp đề xuất

UniSupport là cổng hỗ trợ sinh viên tập trung, cho phép sinh viên tạo Ticket, theo dõi trạng thái, trao đổi với cán bộ xử lý, tra cứu FAQ và đánh giá mức độ hài lòng.

Hệ thống đồng thời hỗ trợ cán bộ xử lý Ticket, quản lý workload, deadline, Dashboard, báo cáo và quản trị cấu hình hệ thống.

### 1.4. Chỉ số thành công

Các chỉ số định lượng cụ thể chưa được thống nhất và sẽ được xác nhận trong giai đoạn Requirement Review.

Các chỉ số dự kiến theo dõi gồm:

- Tỷ lệ Ticket được xử lý hoàn thành.
- Tỷ lệ Ticket quá hạn.
- Thời gian xử lý Ticket trung bình.
- Số lượng Ticket tồn đọng.
- Mức độ hài lòng của sinh viên.
- Hiệu suất xử lý theo phòng ban/cán bộ.

### 1.5. Mục tiêu ra mắt

**Go-live dự kiến: Tuần 23 của dự án.**

---

## 2. Bối cảnh và lý do triển khai

### 2.1. Bối cảnh

Khi quy mô sinh viên và số lượng yêu cầu hỗ trợ tăng, Aurora University cần một hệ thống tập trung để giảm phụ thuộc vào email, điện thoại và các quy trình thủ công.

UniSupport được xây dựng nhằm:

- Tập trung hóa việc tiếp nhận và quản lý yêu cầu.
- Tăng khả năng theo dõi tiến độ xử lý.
- Giảm Ticket bị bỏ sót hoặc xử lý chậm.
- Hỗ trợ quản lý theo dõi workload và deadline.
- Cung cấp dữ liệu báo cáo phục vụ quản lý.

### 2.2. Giả định

- Aurora University cung cấp đầy đủ yêu cầu nghiệp vụ, quy trình và dữ liệu cần thiết cho dự án.
- Dự án không bao gồm nâng cấp phần cứng hoặc hạ tầng mạng.
- Không tích hợp hệ thống bên thứ ba ngoài phạm vi đã thống nhất.
- Không thực hiện thu thập, làm sạch hoặc chuyển đổi toàn bộ dữ liệu lịch sử.
- Không xử lý nghiệp vụ thay cho các phòng ban.
- Không cung cấp hoạt động vận hành dài hạn sau bàn giao ngoài thời gian bảo hành.

---

## 3. Mục tiêu và tiêu chí thành công

### 3.1. Mục tiêu nghiệp vụ

1. Xây dựng một cổng hỗ trợ tập trung cho khoảng 3.000 sinh viên.
2. Chuẩn hóa quá trình tiếp nhận, phân luồng, xử lý và theo dõi Ticket.
3. Hỗ trợ nhà trường quản lý deadline, backlog và hiệu suất xử lý.
4. Cung cấp Dashboard và báo cáo phục vụ quản lý.

### 3.2. Mục tiêu người dùng

**Sinh viên**
- Có thể gửi yêu cầu hỗ trợ trực tuyến.
- Có thể theo dõi trạng thái Ticket.
- Có thể trao đổi và bổ sung thông tin trực tiếp trên Ticket.
- Có thể tra cứu FAQ trước khi tạo Ticket.

**Cán bộ**
- Có danh sách Ticket tập trung để xử lý.
- Có thể cập nhật trạng thái, Priority và phản hồi Ticket.
- Có thể chuyển tiếp, chuyển cấp và yêu cầu bổ sung thông tin.

**Quản lý**
- Có thể theo dõi workload, backlog và Ticket sắp/quá hạn.
- Có thể điều chuyển hoặc phân công lại Ticket.
- Có thể theo dõi hiệu suất xử lý.

**Quản trị viên**
- Có thể cấu hình danh mục, phòng ban, Priority, Routing Rule, tài khoản, FAQ và mẫu phản hồi.

### 3.3. Ngoài mục tiêu

Phiên bản hiện tại không bao gồm:

- Thiết kế lại quy trình nghiệp vụ của Aurora University.
- Cung cấp hoặc nâng cấp phần cứng, máy chủ vật lý và hạ tầng mạng.
- SSO hoặc hệ thống xác thực bên ngoài.
- Tích hợp bên thứ ba ngoài phạm vi đã thống nhất.
- Làm sạch hoặc migration toàn bộ dữ liệu lịch sử.
- Native Mobile App.
- AI/ML hoặc Chatbot.
- Vận hành dài hạn sau bàn giao ngoài thời gian bảo hành.
- Chức năng ngoài In-Scope nếu chưa thông qua Change Request.

---

## 4. Non-Functional Requirements (Yêu cầu phi chức năng)

### 4.1. Giao diện và trải nghiệm (UI/UX)

- **Đa ngôn ngữ (i18n):** Hỗ trợ song ngữ Tiếng Việt (mặc định) và Tiếng Anh; cho phép chuyển đổi ngôn ngữ tức thì trên thanh điều hướng Header.
- **Thích ứng (Responsive):** Tương thích tối ưu trên Mobile Web (< 768px), Tablet (768px – 1023px) và Desktop (≥ 1024px).
- **Tính khả dụng:** Thiết kế giao diện hiện đại, đơn giản, nhất quán, tối đa 3 cú nhấp chuột để tạo Ticket hoặc tra cứu FAQ.

### 4.2. Bảo mật và an toàn dữ liệu

- **Kiểm soát truy cập (RBAC):** Phân quyền 04 vai trò nghiêm ngặt (Sinh viên, Cán bộ, Quản lý, Quản trị viên). Chặn truy cập trên cả UI và API nếu người dùng truy cập trái thẩm quyền.
- **Bảo mật tệp đính kèm:** Dung lượng tối đa 10MB/tệp (.png, .jpg, .jpeg, .pdf, .docx). Không công khai URL tĩnh, kiểm soát truy cập qua Signed URL hoặc API phân quyền.
- **Mã hóa:** Mã hóa mật khẩu người dùng theo chuẩn an toàn (BCrypt / Argon2), giao tiếp toàn hệ thống bắt buộc qua HTTPS (TLS 1.3).
- **Nhật ký kiểm toán (Audit Trail):** Ghi nhận toàn bộ thao tác quan trọng (đăng nhập thất bại liên tiếp, thay đổi phân quyền, cấu hình hệ thống).
- **Dữ liệu giả lập (Mock Data Enforcement):** Bắt buộc 100% môi trường phát triển và kiểm thử chỉ sử dụng dữ liệu giả lập (Mock Data), không sử dụng dữ liệu thật của sinh viên khi chưa phê duyệt.

### 4.3. Hiệu năng (Performance)

- **Thời gian phản hồi API:** $\le 500\text{ms}$ đối với 95% các yêu cầu (P95) trong điều kiện tải bình thường.
- **Thời gian tải trang (Page Load):** $\le 2.0\text{s}$ với mạng băng thông tiêu chuẩn.
- **Tải đồng thời (Concurrency):** Phục vụ ổn định 50 – 100 người dùng đồng thời (CCU) trong các đợt cao điểm đầu/cuối học kỳ.

### 4.4. Khả năng mở rộng (Scalability)

- Hệ thống được thiết kế kiến trúc sẵn sàng phục vụ quy mô khoảng **3.000 sinh viên** và 50 cán bộ vận hành của Aurora University.
- Cơ sở dữ liệu thiết kế có chỉ mục (Indexes) tối ưu cho việc truy vấn và mở rộng lên đến 10.000 sinh viên trong tương lai mà không cần tái cấu trúc dữ liệu cốt lõi.

### 4.5. Nền tảng và môi trường hỗ trợ

- Hỗ trợ các trình duyệt Web hiện đại (phiên bản mới nhất và lùi 2 phiên bản): Google Chrome, Microsoft Edge, Mozilla Firefox, Apple Safari.
- Không phát triển ứng dụng di động riêng biệt (Native App iOS/Android) theo phạm vi Out-of-scope.

---

## 5. User Personas và Use Cases

### 5.1. Persona 1 – Sinh viên

- **Vai trò:** Người gửi yêu cầu hỗ trợ.
- **Mục tiêu:** Gửi, theo dõi và trao đổi Ticket nhanh chóng.
- **Khó khăn hiện tại:** Không biết yêu cầu đang được xử lý ở đâu hoặc bởi ai.
- **Mức độ kỹ thuật:** Cơ bản đến trung bình.
- **Bối cảnh sử dụng:** Trình duyệt trên Desktop hoặc Mobile.

### 5.2. Persona 2 – Cán bộ xử lý

- **Vai trò:** Người tiếp nhận và xử lý Ticket.
- **Mục tiêu:** Quản lý Ticket được phân công và phản hồi sinh viên.
- **Khó khăn hiện tại:** Yêu cầu phân tán, khó theo dõi và dễ bỏ sót.
- **Mức độ kỹ thuật:** Trung bình.

### 5.3. Persona 3 – Quản lý

- **Vai trò:** Theo dõi hoạt động hỗ trợ.
- **Mục tiêu:** Theo dõi workload, backlog, deadline và hiệu suất.
- **Mức độ kỹ thuật:** Trung bình.

### 5.4. Persona 4 – Quản trị viên

- **Vai trò:** Quản lý cấu hình hệ thống.
- **Mục tiêu:** Quản lý người dùng, vai trò, danh mục, phòng ban và quy tắc hệ thống.
- **Mức độ kỹ thuật:** Trung bình đến nâng cao.

### 5.5. Use Case chính – Sinh viên tạo Ticket

**Actor:** Sinh viên

**Điều kiện trước:**
- Sinh viên đã đăng nhập UniSupport.

**Luồng chính:**
1. Sinh viên chọn danh mục hỗ trợ.
2. Sinh viên nhập nội dung yêu cầu.
3. Sinh viên có thể đính kèm tài liệu/hình ảnh.
4. Sinh viên gửi yêu cầu.
5. Hệ thống tạo Ticket ID.
6. Hệ thống ghi nhận Ticket và chuyển vào quy trình xử lý.

**Kết quả mong đợi:**  
Ticket được tạo thành công và có mã định danh duy nhất.

---

## 6. Yêu cầu sản phẩm (Product Requirements)

Tài liệu đặc tả toàn bộ 48 yêu cầu chức năng (Functional Requirements - FR) thuộc phạm vi dự án UniSupport, được phân nhóm theo 05 phân hệ nghiệp vụ chính. Mỗi yêu cầu chức năng bao gồm: **User Story**, **Đặc tả logic (Specifications)** và **Tiêu chí chấp nhận (Acceptance Criteria - AC)**.

> [!TIP]
> **Bộ tài liệu PRD độc lập theo từng phân hệ (Modular PRDs):**  
> Để phục vụ việc phát triển, kiểm thử và bàn giao độc lập theo từng nhóm chuyên trách, mỗi module đã được trích xuất thành 01 tài liệu PRD riêng biệt:
> * 📄 **Module A (Sinh viên):** [01_PRD_MODULE_SINH_VIEN.md](file:///c:/Users/Admin/Documents/New%20Folder/UniSupport_Project/docs/prd/01_PRD_MODULE_SINH_VIEN.md) – *Tiếp nhận & Theo dõi Yêu cầu (FR-01 $\rightarrow$ FR-10)*
> * 📄 **Module B (Cán bộ):** [02_PRD_MODULE_CAN_BO.md](file:///c:/Users/Admin/Documents/New%20Folder/UniSupport_Project/docs/prd/02_PRD_MODULE_CAN_BO.md) – *Phân luồng & Xử lý Yêu cầu (FR-11 $\rightarrow$ FR-22)*
> * 📄 **Module C (Quản lý & Admin):** [03_PRD_MODULE_QUAN_LY_QUAN_TRI.md](file:///c:/Users/Admin/Documents/New%20Folder/UniSupport_Project/docs/prd/03_PRD_MODULE_QUAN_LY_QUAN_TRI.md) – *Quản lý Hoạt động & Cấu hình (FR-23 $\rightarrow$ FR-32)*
> * 📄 **Module D (Báo cáo & Phân tích):** [04_PRD_MODULE_DASHBOARD_BAO_CAO.md](file:///c:/Users/Admin/Documents/New%20Folder/UniSupport_Project/docs/prd/04_PRD_MODULE_DASHBOARD_BAO_CAO.md) – *Dashboard & Thống kê MTTR/CSAT (FR-33 $\rightarrow$ FR-40)*
> * 📄 **Module E (Bảo mật & UX):** [05_PRD_MODULE_BAO_MAT_UX.md](file:///c:/Users/Admin/Documents/New%20Folder/UniSupport_Project/docs/prd/05_PRD_MODULE_BAO_MAT_UX.md) – *Bảo mật, RBAC, i18n & Responsive (FR-41 $\rightarrow$ FR-48)*

---

### 6.1. Phân hệ Tiếp nhận & Theo dõi Yêu cầu (Dành cho Sinh viên)

#### FR-01: Tạo và nộp yêu cầu hỗ trợ (Ticket Submission)

* **User Story:** Là một Sinh viên, tôi muốn gửi yêu cầu hỗ trợ trực tuyến theo từng danh mục và đính kèm tài liệu minh chứng, để vấn đề của tôi được hệ thống tiếp nhận và chuyển đến đúng phòng ban xử lý.
* **Đặc tả logic (Specifications):**
  * Giao diện cung cấp danh mục dịch vụ có hướng dẫn chọn: *Đào tạo*, *Công tác sinh viên*, *Kế toán/Tài chính*, *Khảo thí*. Dưới mỗi nhóm có mô tả ngắn về các loại nghiệp vụ phụ trách.
  * Các trường thông tin bắt buộc: Danh mục yêu cầu, Tiêu đề (tối đa 150 ký tự), Nội dung chi tiết (tối đa 2.000 ký tự).
  * Tệp đính kèm: Cho phép đính kèm tối đa 03 tệp định dạng `.pdf`, `.jpg`, `.png`. Dung lượng mỗi tệp không quá **5MB**.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-01.1 (Tạo thành công):** Khi sinh viên nhấn "Gửi yêu cầu", hệ thống tự động cấp phát một mã định danh duy nhất theo định dạng `AU-2026-XXXX` (trong đó XXXX là số tự tăng), trạng thái đặt về `Mới tạo`. Hệ thống hiển thị thông báo thành công và gửi email xác nhận chứa mã Ticket về email sinh viên.
  * **AC-01.2 (Lỗi tệp đính kèm):** Nếu người dùng tải lên tệp vượt quá 5MB hoặc sai định dạng cho phép, hệ thống chặn gửi và hiển thị cảnh báo đỏ trực tiếp tại vùng tải tệp.
  * **AC-01.3 (Thiếu trường bắt buộc):** Nếu sinh viên bỏ trống bất kỳ trường bắt buộc nào (Danh mục, Tiêu đề, Nội dung), nút gửi bị vô hiệu hóa hoặc hệ thống highlight trường lỗi kèm thông báo hướng dẫn.

#### FR-02: Đính kèm tài liệu & tệp minh chứng (File Attachments)

* **User Story:** Là một Sinh viên, tôi muốn tải lên các tệp tài liệu và hình ảnh minh họa để cán bộ có đầy đủ cơ sở xem xét và giải quyết vấn đề.
* **Đặc tả logic (Specifications):**
  * Hỗ trợ tải lên tối đa 03 tệp qua cơ chế kéo-thả (Drag & Drop) hoặc chọn tệp từ máy tính/thiết bị di động.
  * Định dạng hợp lệ: `.pdf`, `.jpg`, `.jpeg`, `.png`. Dung lượng tối đa: **5MB/tệp**.
  * Kiểm tra MIME type tại tầng Server để ngăn chặn nguy cơ tải lên mã độc hại.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-02.1 (Tải tệp hợp lệ):** Tệp tải lên thành công hiển thị tên tệp, dung lượng và icon tương ứng định dạng, kèm nút "Xóa" để sinh viên gỡ tệp trước khi gửi.
  * **AC-02.2 (Chặn tệp không hợp lệ):** Hệ thống từ chối các định dạng file thực thi (ví dụ: `.exe`, `.bat`, `.js`, `.zip`) và tệp vượt quá 5MB, đồng thời thông báo rõ nguyên nhân từ chối.

#### FR-03: Thông báo hệ thống & Email xác nhận (Notifications & Emails)

* **User Story:** Là một Sinh viên, tôi muốn nhận thông báo qua hệ thống và Email mỗi khi Ticket có cập nhật mới để tôi kịp thời nắm bắt tiến độ mà không cần truy cập trang liên tục.
* **Đặc tả logic (Specifications):**
  * Tự động kích hoạt thông báo In-app (biểu tượng chuông thông báo) và gửi Email tự động trong các trường hợp:
    1. Tạo Ticket thành công.
    2. Cán bộ gửi phản hồi chính thức hoặc yêu cầu bổ sung thông tin.
    3. Ticket chuyển trạng thái sang `Hoàn thành`.
  * Cấu trúc Email thông báo: Tiêu đề chứa mã Ticket `[AU-2026-XXXX]`, tên sinh viên, trích đoạn nội dung cập nhật mới và nút liên kết trực tiếp (Deep-link) đưa đến trang chi tiết Ticket.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-03.1 (Gửi email thời gian thực):** Email xác nhận được gửi tới địa chỉ email sinh viên trong vòng $\le 60$ giây kể từ khi sự kiện phát sinh.
  * **AC-03.2 (Cập nhật In-app realtime):** Số lượng thông báo chưa đọc trên icon chuông tự động tăng số và hiển thị popup thông báo ngắn trên góc màn hình nếu sinh viên đang mở ứng dụng.

#### FR-04: Theo dõi trạng thái & chi tiết tiến độ Ticket (Ticket Tracking)

* **User Story:** Là một Sinh viên, tôi muốn theo dõi danh sách tất cả các Ticket của mình cùng trạng thái xử lý hiện tại để biết yêu cầu đang ở khâu nào.
* **Đặc tả logic (Specifications):**
  * Màn hình danh sách hiển thị các thông tin: Mã Ticket, Tiêu đề, Danh mục, Trạng thái xử lý (kèm màu sắc phân biệt), Ngày tạo, Cập nhật gần nhất.
  * 04 trạng thái tiêu chuẩn: `Mới tạo` (Xanh dương), `Đang xử lý` (Cam), `Cần bổ sung` (Vàng), `Hoàn thành` (Xanh lá).
  * Bộ lọc hỗ trợ: Lọc theo trạng thái, lọc theo danh mục và ô tìm kiếm theo mã Ticket hoặc từ khóa tiêu đề.
  * Kiểm soát dữ liệu: Sinh viên chỉ xem được duy nhất các Ticket do tài khoản của mình tạo ra.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-04.1 (Hiển thị danh sách chính xác):** Danh sách chỉ trả về các Ticket của tài khoản đăng nhập hiện tại, sắp xếp theo thứ tự mới nhất lên đầu.
  * **AC-04.2 (Lọc và tìm kiếm mượt mà):** Khi sinh viên chọn lọc theo trạng thái `Đang xử lý` hoặc gõ mã Ticket, danh sách phản hồi kết quả chính xác trong vòng $\le 1$ giây.

#### FR-05: Trao đổi hai chiều trên Ticket (Direct Messaging)

* **User Story:** Là một Sinh viên, tôi muốn nhắn tin trao đổi trực tiếp với Cán bộ phụ trách ngay trên giao diện Ticket để làm rõ các nội dung còn khúc mắc.
* **Đặc tả logic (Specifications):**
  * Khung hội thoại hiển thị dạng luồng tin nhắn (Chat thread) theo trình tự thời gian từ cũ đến mới.
  * Mỗi tin nhắn thể hiện: Tên người gửi, vai trò (Cán bộ / Sinh viên), thời gian gửi (Timestamp) và nội dung văn bản.
  * **Nguyên tắc bảo mật nội bộ:** Sinh viên chỉ nhìn thấy tin nhắn phản hồi công khai của Cán bộ; **tuyệt đối không hiển thị Ghi chú nội bộ (Internal Notes)** trên cả giao diện người dùng và API phản hồi.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-05.1 (Gửi tin nhắn thành công):** Sinh viên nhập nội dung và bấm gửi, tin nhắn xuất hiện ngay trên luồng hội thoại và hệ thống gửi thông báo cho cán bộ phụ trách.
  * **AC-05.2 (Khóa trao đổi khi hoàn thành):** Khi Ticket đã chuyển trạng thái `Hoàn thành` quá thời hạn cho phép mở lại, khung soạn thảo tin nhắn tự động khóa và hiển thị ghi chú Ticket đã đóng.

#### FR-06: Bổ sung thông tin theo yêu cầu (Information Supplement)

* **User Story:** Là một Sinh viên, tôi muốn cập nhật thêm thông tin hoặc đính kèm tài liệu bổ sung khi Cán bộ yêu cầu để quá trình xử lý không bị ách tắc.
* **Đặc tả logic (Specifications):**
  * Chức năng tự động kích hoạt khi Ticket chuyển sang trạng thái `Cần bổ sung`.
  * Trên đầu trang chi tiết hiển thị banner cảnh báo nổi bật kèm nội dung yêu cầu cụ thể từ cán bộ.
  * Cho phép sinh viên nhập nội dung giải trình và đính kèm thêm tối đa 03 tệp minh chứng mới.
  * **Tự động chuyển trạng thái:** Ngay khi sinh viên nhấn nút "Gửi thông tin bổ sung", hệ thống **tự động chuyển trạng thái Ticket từ `Cần bổ sung` về `Đang xử lý`**.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-06.1 (Tự động đổi trạng thái):** Sau khi gửi bổ sung thành công, trạng thái Ticket lập tức chuyển thành `Đang xử lý`, đồng thời thông báo cho cán bộ phụ trách tiếp tục xử lý.
  * **AC-06.2 (Lưu vết bổ sung):** Nội dung và tệp bổ sung được đánh dấu rõ ràng trong luồng hội thoại với nhãn "Thông tin bổ sung từ sinh viên".

#### FR-07: Mở lại Ticket trong thời hạn quy định (Ticket Reopen)

* **User Story:** Là một Sinh viên, tôi muốn có thể mở lại Ticket đã hoàn thành nếu kết quả xử lý chưa thỏa đáng hoặc vấn đề phát sinh trở lại.
* **Đặc tả logic (Specifications):**
  * Nút "Mở lại Ticket" chỉ hiển thị khi Ticket đang ở trạng thái `Hoàn thành`.
  * **Thời hạn cho phép:** Sinh viên chỉ được phép mở lại Ticket trong vòng **03 ngày (72 giờ)** kể từ thời điểm Cán bộ bấm chuyển trạng thái `Hoàn thành`.
  * Sau 72 giờ, hệ thống tự động khóa vĩnh viễn (`Closed`), nút "Mở lại" tự động ẩn đi và sinh viên phải tạo Ticket mới nếu cần hỗ trợ.
  * Khi mở lại, sinh viên bắt buộc phải nhập lý do mở lại. Trạng thái Ticket tự động chuyển về `Đang xử lý`.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-07.1 (Mở lại hợp lệ):** Trong vòng 72 giờ, sinh viên nhập lý do và bấm "Mở lại Ticket" $\rightarrow$ Ticket chuyển trạng thái thành `Đang xử lý`, thông báo cho Cán bộ tiếp tục hỗ trợ.
  * **AC-07.2 (Quá hạn mở lại):** Sau 72 giờ, hệ thống khóa tính năng mở lại và hiển thị thông báo: "Ticket đã đóng vĩnh viễn. Vui lòng tạo yêu cầu hỗ trợ mới nếu bạn vẫn cần trợ giúp."

#### FR-08: Xem lịch sử và tiến trình xử lý (Ticket Activity Timeline)

* **User Story:** Là một Sinh viên, tôi muốn xem lịch sử các mốc thời gian xử lý Ticket để nắm bắt tiến độ một cách minh bạch.
* **Đặc tả logic (Specifications):**
  * Widget Timeline hiển thị theo chiều dọc, ghi nhận các sự kiện quan trọng:
    * Thời điểm tạo Ticket thành công.
    * Thời điểm phòng ban tiếp nhận và cán bộ được phân công.
    * Các lần thay đổi trạng thái và yêu cầu bổ sung thông tin.
    * Thời điểm cán bộ giải quyết xong và hoàn tất Ticket.
  * Mỗi mốc gồm: Thời gian cụ thể, tên sự kiện, và người thực hiện (nếu là thông tin công khai).
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-08.1 (Hiển thị mốc sự kiện chuẩn xác):** Mọi thay đổi trạng thái của Ticket đều được ghi nhận ngay vào Timeline với timestamp chính xác.

#### FR-09: Tra cứu câu hỏi thường gặp (FAQ & Knowledge Base)

* **User Story:** Là một Sinh viên, tôi muốn tra cứu câu hỏi thường gặp và hướng dẫn nghiệp vụ trước khi tạo Ticket để có thể tự giải quyết vấn đề nhanh chóng.
* **Đặc tả logic (Specifications):**
  * Cung cấp trang Knowledge Base phân nhóm theo chuyên mục: *Quy chế học vụ*, *Học phí & Học bổng*, *Ký túc xá*, *Tài khoản & Email trường*.
  * Hỗ trợ thanh tìm kiếm thông minh theo từ khóa (Keyword search).
  * **Smart Suggestion:** Tại màn hình Tạo Ticket, khi sinh viên gõ Tiêu đề, hệ thống tự động quét và gợi ý danh sách 3 bài viết FAQ liên quan nhất để sinh viên đọc trước.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-09.1 (Gợi ý tự động khi tạo Ticket):** Khi nhập tiêu đề có chứa từ khóa (ví dụ: "cấp bảng điểm"), khung gợi ý FAQ lập tức xuất hiện bên cạnh hoặc phía dưới ô nhập.
  * **AC-09.2 (Đọc bài viết chi tiết):** Bấm vào bài viết FAQ hiển thị nội dung hướng dẫn chi tiết, hình ảnh minh họa và các liên kết biểu mẫu tải về.

#### FR-10: Đánh giá mức độ hài lòng (CSAT Rating & Feedback)

* **User Story:** Là một Sinh viên, tôi muốn đánh giá mức độ hài lòng sau khi Ticket hoàn thành để phản ánh chất lượng phục vụ của nhà trường.
* **Đặc tả logic (Specifications):**
  * Form khảo sát đánh giá tự động xuất hiện tại trang chi tiết Ticket ngay sau khi Ticket chuyển sang trạng thái `Hoàn thành`.
  * Thang điểm đánh giá: 1 đến 5 sao (kèm nhãn mức độ: *Rất không hài lòng*, *Không hài lòng*, *Bình thường*, *Hài lòng*, *Rất hài lòng*).
  * Ô nhập ý kiến đóng góp tùy chọn (tối đa 500 ký tự).
  * Mỗi Ticket chỉ được gửi đánh giá duy nhất **01 lần**.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-10.1 (Gửi đánh giá thành công):** Sinh viên chọn số sao, nhập nhận xét và bấm gửi $\rightarrow$ hệ thống ghi nhận điểm CSAT và hiển thị thông báo "Cảm ơn bạn đã đóng góp ý kiến".
  * **AC-10.2 (Khóa sau khi đánh giá):** Sau khi gửi, form đánh giá chuyển sang chế độ chỉ đọc (Read-only), hiển thị điểm số sinh viên đã chấm và không cho phép chỉnh sửa lại.

---

### 6.2. Phân hệ Phân luồng & Xử lý Yêu cầu (Dành cho Cán bộ)

#### FR-11: Hàng đợi xử lý tập trung (Ticket Queue Management)

* **User Story:** Là một Cán bộ xử lý, tôi muốn có một giao diện hàng đợi tập trung hiển thị danh sách các Ticket cần xử lý để tôi dễ dàng quản lý và không bỏ sót công việc.
* **Đặc tả logic (Specifications):**
  * Danh sách phân chia theo các Tab nghiệp vụ rõ ràng:
    * *Ticket của tôi:* Các yêu cầu đang được phân công trực tiếp cho cá nhân cán bộ.
    * *Chưa phân công (Unassigned):* Các yêu cầu thuộc phòng ban của cán bộ nhưng chưa có người nhận xử lý.
    * *Tất cả Ticket phòng ban:* Toàn bộ yêu cầu thuộc phạm vi phòng ban quản lý.
  * Mỗi dòng hiển thị: Mã Ticket, Tiêu đề, Sinh viên, Trạng thái, Priority, Hạn xử lý (SLA Deadline).
  * Đánh dấu màu nổi bật cho Ticket sắp đến hạn (vàng) hoặc đã quá hạn xử lý (đỏ).
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-11.1 (Phân quyền dữ liệu phòng ban):** Cán bộ thuộc phòng ban nào chỉ nhìn thấy Ticket thuộc phòng ban đó; không nhìn thấy Ticket của phòng ban khác.
  * **AC-11.2 (Cảnh báo hạn xử lý trực quan):** Các Ticket có thời gian SLA còn lại $\le 25\%$ tự động đổi sang badge màu vàng; Ticket quá hạn hiển thị badge màu đỏ kèm số giờ quá hạn.

#### FR-12: Tự động phân luồng theo danh mục/phòng ban (Auto-Routing)

* **User Story:** Là một Cán bộ, tôi muốn hệ thống tự động chuyển Ticket mới về đúng phòng ban theo danh mục sinh viên đã chọn để giảm thiểu thao tác điều phối thủ công.
* **Đặc tả logic (Specifications):**
  * Khi sinh viên nộp Ticket thành công, hệ thống đọc cấu hình Routing Rules đang hoạt động:
    * Nhóm *Đào tạo* $\rightarrow$ Phòng Đào tạo.
    * Nhóm *Công tác sinh viên* $\rightarrow$ Phòng Công tác sinh viên (CTSV).
    * Nhóm *Kế toán/Tài chính* $\rightarrow$ Phòng Kế hoạch - Tài chính.
    * Nhóm *Khảo thí* $\rightarrow$ Phòng Khảo thí & Đảm bảo chất lượng.
  * Ticket tự động được gán vào hàng đợi chung của phòng ban tương ứng.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-12.1 (Phân luồng tức thì):** Ngay sau khi sinh viên tạo Ticket, Ticket xuất hiện ngay trong tab "Chưa phân công" của đúng phòng ban thụ lý.

#### FR-13: Tiếp nhận và phân công Ticket (Ticket Assignment & Self-Assign)

* **User Story:** Là một Cán bộ, tôi muốn chủ động nhận xử lý Ticket hoặc phân công cho đồng nghiệp trong phòng ban để phân định rõ trách nhiệm cá nhân.
* **Đặc tả logic (Specifications):**
  * Nút "Nhận xử lý" (Self-assign) cho phép cán bộ tự gán Ticket cho chính mình với 1 cú click.
  * Dropdown phân công hiển thị danh sách toàn bộ cán bộ trực thuộc cùng phòng ban.
  * Khi Ticket được gán người phụ trách, trạng thái Ticket tự động chuyển từ `Mới tạo` sang `Đang xử lý` (nếu đang ở trạng thái mới tạo).
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-13.1 (Tự nhận xử lý):** Cán bộ bấm "Nhận xử lý", trường Người phụ trách (Assignee) lập tức cập nhật tên cán bộ đó và ghi vết vào lịch sử Ticket.
  * **AC-13.2 (Phân công đồng nghiệp):** Cán bộ chọn tên đồng nghiệp trong dropdown và bấm lưu $\rightarrow$ hệ thống chuyển Ticket sang "Ticket của tôi" của cán bộ được gán và gửi thông báo In-app/Email cho người đó.

#### FR-14: Chuyển tiếp phòng ban & Chuyển cấp xử lý (Forward & Escalate)

* **User Story:** Là một Cán bộ, tôi muốn chuyển tiếp Ticket sang phòng ban khác hoặc chuyển cấp lên Quản lý khi nội dung yêu cầu thuộc thẩm quyền đơn vị khác hoặc vượt quá quyền hạn của tôi.
* **Đặc tả logic (Specifications):**
  * Chuyển tiếp phòng ban (Forward): Chọn phòng ban tiếp nhận mới từ danh sách, reset người phụ trách về Unassigned của phòng ban mới. Bắt buộc nhập lý do chuyển tiếp.
  * Chuyển cấp (Escalate): Gán trực tiếp Ticket lên tài khoản Quản lý (Trưởng phòng) của phòng ban để xin ý kiến chỉ đạo. Bắt buộc nhập lý do chuyển cấp.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-14.1 (Chuyển phòng ban hợp lệ):** Cán bộ chọn phòng ban mới, nhập lý do và bấm xác nhận $\rightarrow$ Ticket rời khỏi hàng đợi của phòng ban cũ và chuyển sang hàng đợi của phòng ban mới kèm log chuyển tiếp.
  * **AC-14.2 (Bắt buộc nhập lý do):** Nếu bỏ trống ô lý do chuyển tiếp/chuyển cấp, hệ thống chặn gửi và cảnh báo: "Vui lòng nhập lý do điều chuyển".

#### FR-15: Tìm kiếm, lọc và sắp xếp Ticket nâng cao (Search & Advanced Filter)

* **User Story:** Là một Cán bộ, tôi muốn lọc và sắp xếp danh sách Ticket theo nhiều tiêu chí nghiệp vụ để nhanh chóng tìm thấy các yêu cầu cần xử lý gấp.
* **Đặc tả logic (Specifications):**
  * Các tiêu chí lọc hỗ trợ: Trạng thái (Mới tạo, Đang xử lý, Cần bổ sung, Hoàn thành), Danh mục, Mức độ ưu tiên (Thấp, Trung bình, Cao, Khẩn cấp), Cán bộ phụ trách, Khoảng ngày tiếp nhận.
  * Sắp xếp theo: Hạn xử lý SLA (Gần nhất/Xa nhất), Ngày tạo (Mới nhất/Cũ nhất), Mức độ ưu tiên (Cao $\rightarrow$ Thấp).
  * Tìm kiếm tức thì theo mã định danh `AU-2026-XXXX`, tên sinh viên, mã số sinh viên (MSSV) hoặc từ khóa tiêu đề.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-15.1 (Tốc độ phản hồi tìm kiếm):** Kết quả tìm kiếm và áp dụng bộ lọc hiển thị chính xác trong thời gian $\le 1.0$ giây.
  * **AC-15.2 (Lưu trạng thái bộ lọc):** Khi cán bộ bấm vào xem chi tiết một Ticket và nhấn nút Quay lại, hệ thống giữ nguyên các điều kiện lọc và trang đang xem trước đó.

#### FR-16: Cập nhật trạng thái xử lý Ticket (Status Update)

* **User Story:** Là một Cán bộ, tôi muốn cập nhật trạng thái xử lý Ticket theo tiến độ thực tế để sinh viên và ban quản lý nắm bắt tình hình giải quyết.
* **Đặc tả logic (Specifications):**
  * Cán bộ có thể cập nhật trạng thái thông qua dropdown trên trang chi tiết Ticket.
  * Quy tắc chuyển đổi trạng thái (State Machine):
    * `Mới tạo` $\rightarrow$ `Đang xử lý`.
    * `Đang xử lý` $\rightarrow$ `Cần bổ sung` (khi cần sinh viên cung cấp thêm thông tin).
    * `Đang xử lý` $\rightarrow$ `Hoàn thành` (khi đã giải quyết xong).
  * Khi chuyển trạng thái sang `Hoàn thành`, hệ thống bắt buộc cán bộ phải gửi kèm nội dung giải quyết chính thức.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-16.1 (Chuyển trạng thái thành công):** Chọn trạng thái mới và bấm lưu $\rightarrow$ trạng thái cập nhật ngay lập tức, kích hoạt gửi email thông báo tương ứng cho sinh viên.
  * **AC-16.2 (Ràng buộc khi hoàn thành):** Nếu cán bộ chọn `Hoàn thành` nhưng chưa nhập nội dung phản hồi kết quả, hệ thống hiển thị thông báo lỗi yêu cầu nhập nội dung giải quyết trước khi đóng Ticket.

#### FR-17: Thiết lập và điều chỉnh mức độ ưu tiên (Priority Management)

* **User Story:** Là một Cán bộ, tôi muốn điều chỉnh mức độ ưu tiên của Ticket khi phát hiện vấn đề có tính cấp bách để điều chỉnh thời hạn giải quyết phù hợp.
* **Đặc tả logic (Specifications):**
  * 04 mức ưu tiên: `Thấp` (Low), `Trung bình` (Medium - Mặc định), `Cao` (High), `Khẩn cấp` (Urgent).
  * Khi thay đổi mức độ ưu tiên, hệ thống **tự động tính toán lại thời hạn xử lý (SLA Deadline)** của Ticket theo cấu hình tương ứng với mức ưu tiên mới.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-17.1 (Điều chỉnh Priority và cập nhật SLA):** Khi chuyển mức ưu tiên từ `Trung bình` sang `Khẩn cấp`, hệ thống rút ngắn hạn xử lý theo đúng cấu hình và hiển thị hạn chót mới ngay trên giao diện.

#### FR-18: Yêu cầu sinh viên bổ sung thông tin (Request Additional Information)

* **User Story:** Là một Cán bộ, tôi muốn gửi yêu cầu cho sinh viên bổ sung thông tin hoặc tài liệu còn thiếu để có đủ căn cứ giải quyết vấn đề.
* **Đặc tả logic (Specifications):**
  * Cán bộ nhập nội dung chi tiết cần bổ sung vào form "Yêu cầu bổ sung thông tin".
  * Khi nhấn gửi: Trạng thái Ticket tự động đổi sang `Cần bổ sung`.
  * Hệ thống tự động gửi email và thông báo In-app cho sinh viên kèm theo hướng dẫn của cán bộ.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-18.1 (Gửi yêu cầu bổ sung):** Ticket chuyển trạng thái sang `Cần bổ sung`, luồng tin nhắn hiển thị ghi chú yêu cầu bổ sung nổi bật và gửi email thông báo cho sinh viên trong vòng $\le 60$ giây.

#### FR-19: Thêm ghi chú nội bộ bảo mật (Internal Notes)

* **User Story:** Là một Cán bộ, tôi muốn ghi lại các trao đổi kỹ thuật hoặc ý kiến tham vấn với đồng nghiệp ngay trên Ticket mà không để sinh viên nhìn thấy.
* **Đặc tả logic (Specifications):**
  * Cung cấp Tab riêng biệt mang tên "Ghi chú nội bộ" trong khung trao đổi của Ticket.
  * Giao diện ghi chú có viền và màu nền phân biệt rõ (nền vàng nhạt) kèm nhãn "Chỉ nội bộ - Ẩn với sinh viên".
  * **Cơ chế bảo mật tuyệt đối:** Dữ liệu ghi chú nội bộ chỉ được gửi về Client khi người dùng đăng nhập có vai trò là *Cán bộ*, *Quản lý* hoặc *Quản trị viên*. Chặn hoàn toàn trường dữ liệu này ở API trả về cho vai trò *Sinh viên*.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-19.1 (Ghi chú nội bộ hiển thị với cán bộ):** Cán bộ nhập ghi chú và bấm lưu $\rightarrow$ ghi chú xuất hiện trên tab nội bộ với tên người ghi và thời gian.
  * **AC-19.2 (Ẩn hoàn toàn với sinh viên):** Khi đăng nhập tài khoản Sinh viên và mở cùng Ticket đó, sinh viên hoàn toàn không thấy tab hoặc bất kỳ nội dung nào của ghi chú nội bộ.

#### FR-20: Phản hồi chính thức cho sinh viên (Official Public Response)

* **User Story:** Là một Cán bộ, tôi muốn gửi câu trả lời chính thức kèm tài liệu đính kèm cho sinh viên để giải quyết dứt điểm yêu cầu hỗ trợ.
* **Đặc tả logic (Specifications):**
  * Cán bộ soạn nội dung phản hồi trong khung "Phản hồi chính thức".
  * Hỗ trợ đính kèm tối đa 03 tệp kết quả xử lý (ví dụ: file PDF giấy xác nhận, thông báo...).
  * Tin nhắn phản hồi được gửi vào luồng trao đổi công khai và kích hoạt thông báo qua email cho sinh viên.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-20.1 (Phản hồi thành công):** Nội dung phản hồi hiển thị trên trang của sinh viên, sinh viên có thể xem và tải các tệp đính kèm do cán bộ gửi về.

#### FR-21: Sử dụng mẫu phản hồi soạn sẵn (Canned Response Templates)

* **User Story:** Là một Cán bộ, tôi muốn chọn nhanh các câu trả lời mẫu cho các câu hỏi phổ biến để tiết kiệm thời gian soạn thảo và chuẩn hóa câu từ.
* **Đặc tả logic (Specifications):**
  * Nút "Chọn mẫu phản hồi" hiển thị ngay trong thanh công cụ của khung soạn thảo tin nhắn.
  * Cho phép tìm kiếm mẫu câu trả lời theo tên mẫu hoặc danh mục nghiệp vụ.
  * Tự động thay thế các biến thông tin (Placeholder) trong mẫu: `{ten_sinh_vien}` $\rightarrow$ Tên thật của SV, `{ma_ticket}` $\rightarrow$ Mã `AU-2026-XXXX`.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-21.1 (Điền nội dung mẫu tự động):** Khi cán bộ chọn một mẫu phản hồi, toàn bộ văn bản mẫu tự động điền vào khung soạn thảo kèm theo thông tin sinh viên đã được thay thế chính xác.

#### FR-22: Lưu nhật ký và lịch sử thao tác (Ticket Activity Log)

* **User Story:** Là một Cán bộ hoặc Quản lý, tôi muốn xem toàn bộ nhật ký thao tác trên Ticket để phục vụ kiểm soát chất lượng dịch vụ và truy vết khi có tranh chấp.
* **Đặc tả logic (Specifications):**
  * Hệ thống tự động ghi nhận không thể can thiệp (Immutable log) mọi thao tác: Tạo Ticket, Gán cán bộ, Đổi mức ưu tiên, Đổi trạng thái, Thêm ghi chú nội bộ, Gửi phản hồi, Điều chuyển phòng ban.
  * Cấu trúc mỗi bản ghi log: Thời gian (Timestamp chuẩn), Người thực hiện (Tên, Mã cán bộ), Hành động, Giá trị trước thay đổi $\rightarrow$ Giá trị sau thay đổi.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-22.1 (Ghi log đầy đủ):** Tab "Nhật ký hoạt động" hiển thị toàn bộ chuỗi sự kiện theo thứ tự thời gian giảm dần, không có tùy chọn sửa hoặc xóa log đối với bất kỳ người dùng nào.

---

### 6.3. Phân hệ Quản lý Hoạt động & Cấu hình Hệ thống (Dành cho Quản lý & Admin)

#### FR-23: Theo dõi khối lượng công việc & hoạt động phòng ban (Workload Monitoring)

* **User Story:** Là một Quản lý phòng ban, tôi muốn theo dõi khối lượng Ticket đang phân công cho từng cán bộ để nắm bắt tình hình phân bổ nhân lực và tránh quá tải.
* **Đặc tả logic (Specifications):**
  * Màn hình Workload hiển thị danh sách cán bộ trong phòng ban kèm các chỉ số:
    * Số Ticket đang xử lý (`In Progress`).
    * Số Ticket mới chưa xử lý.
    * Số Ticket sắp/đã quá hạn SLA.
    * Tổng số Ticket đã hoàn thành trong tháng.
  * Hỗ trợ thanh lọc dữ liệu theo khoảng thời gian tùy chọn.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-23.1 (Thống kê chính xác):** Các chỉ số số lượng Ticket trên bảng Workload phản ánh chính xác dữ liệu thực tế tại thời điểm xem.

#### FR-24: Điều chuyển và tái phân công Ticket (Ticket Reassignment)

* **User Story:** Là một Quản lý phòng ban, tôi muốn chủ động điều chuyển Ticket từ cán bộ đang quá tải sang cán bộ khác để đảm bảo tiến độ xử lý cam kết.
* **Đặc tả logic (Specifications):**
  * Quản lý có quyền chọn 1 Ticket hoặc tích chọn nhiều Ticket cùng lúc (Bulk Action).
  * Bấm nút "Phân công lại" $\rightarrow$ chọn cán bộ tiếp nhận mới từ danh sách nhân sự phòng ban $\rightarrow$ xác nhận.
  * Hệ thống cập nhật người phụ trách mới ngay lập tức và gửi thông báo cho cán bộ được bàn giao.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-24.1 (Phân công lại hàng loạt):** Quản lý chọn 5 Ticket và chuyển cho cán bộ B $\rightarrow$ cả 5 Ticket lập tức cập nhật Assignee thành cán bộ B và ghi nhận nhật ký người thực hiện là Quản lý.

#### FR-25: Thiết lập thời hạn xử lý & Cảnh báo SLA (SLA & Deadline Alerts)

* **User Story:** Là một Quản lý hoặc Quản trị viên, tôi muốn cấu hình thời hạn xử lý chuẩn (SLA) theo mức ưu tiên và danh mục, đồng thời nhận cảnh báo sớm để giảm thiểu Ticket quá hạn.
* **Đặc tả logic (Specifications):**
  * Cấu hình thời hạn giải quyết tiêu chuẩn theo mức ưu tiên:
    * *Khẩn cấp (Urgent):* Mặc định **04 giờ làm việc**.
    * *Cao (High):* Mặc định **12 giờ làm việc**.
    * *Trung bình (Medium):* Mặc định **24 giờ làm việc**.
    * *Thấp (Low):* Mặc định **48 giờ làm việc**.
  * Quy tắc cảnh báo tự động:
    * Cảnh báo vàng: Khi thời gian còn lại $\le 25\%$ tổng thời hạn.
    * Cảnh báo đỏ: Khi thời gian đã vượt quá thời hạn quy định (Overdue).
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-25.1 (Tính deadline chính xác):** Khi Ticket được tạo hoặc đổi mức ưu tiên, hệ thống tính toán chính xác thời điểm Deadline hiển thị trên Ticket.
  * **AC-25.2 (Bắn cảnh báo tự động):** Khi Ticket chạm ngưỡng cảnh báo vàng hoặc đỏ, hệ thống tự động đổi màu badge hiển thị và gửi thông báo cho Cán bộ thụ lý cùng Quản lý phòng ban.

#### FR-26: Quản lý danh mục yêu cầu (Category Management)

* **User Story:** Là một Quản trị viên, tôi muốn tạo mới, chỉnh sửa và quản lý danh sách các danh mục yêu cầu hỗ trợ để phù hợp với quy trình hoạt động của trường.
* **Đặc tả logic (Specifications):**
  * Mỗi danh mục bao gồm: Tên danh mục, Mô tả hướng dẫn, Phòng ban tiếp nhận mặc định, Trạng thái hoạt động (Kích hoạt / Tạm ngừng).
  * **Ràng buộc an toàn dữ liệu:** Không cho phép xóa cứng danh mục đã có phát sinh Ticket trong quá khứ (chỉ cho phép chuyển trạng thái sang Tạm ngừng / Inactive).
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-26.1 (Tạo và sửa danh mục):** Thêm mới danh mục thành công; danh mục được kích hoạt lập tức xuất hiện trong dropdown chọn danh mục của sinh viên.
  * **AC-26.2 (Bảo vệ dữ liệu lịch sử):** Nhấn xóa danh mục đã có dữ liệu $\rightarrow$ hệ thống chặn xóa và gợi ý chuyển sang trạng thái "Tạm ngừng hoạt động".

#### FR-27: Quản lý cơ cấu phòng ban (Department Management)

* **User Story:** Là một Quản trị viên, tôi muốn quản lý danh sách phòng ban hỗ trợ và gán cán bộ vào đúng phòng ban để đảm bảo tính phân luồng chính xác.
* **Đặc tả logic (Specifications):**
  * Thông tin phòng ban: Mã phòng ban, Tên phòng ban, Email liên hệ, Cán bộ quản lý phụ trách (Trưởng phòng), Danh sách nhân sự trực thuộc.
  * Cho phép thêm mới phòng ban, cập nhật thông tin và điều chuyển cán bộ giữa các phòng ban.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-27.1 (Thêm/Sửa phòng ban):** Tạo mới phòng ban thành công; danh sách phòng ban hiển thị đầy đủ trong các chức năng phân luồng và báo cáo.

#### FR-28: Quản lý mức độ ưu tiên (Priority Matrix Configuration)

* **User Story:** Là một Quản trị viên, tôi muốn quản lý các mức độ ưu tiên và thời gian xử lý mục tiêu để chuẩn hóa thời gian phản hồi toàn trường.
* **Đặc tả logic (Specifications):**
  * Quản lý 04 mức ưu tiên: Thấp, Trung bình, Cao, Khẩn cấp.
  * Cấu hình mã màu đại diện (Xanh lá, Xanh dương, Cam, Đỏ) và số giờ SLA tiêu chuẩn cho từng mức.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-28.1 (Cập nhật thời gian SLA):** Khi cập nhật số giờ SLA của mức "Cao", các Ticket mới được tạo ở mức "Cao" sẽ áp dụng theo số giờ mới này.

#### FR-29: Cấu hình quy tắc phân luồng tự động (Routing Rules Configuration)

* **User Story:** Là một Quản trị viên, tôi muốn thiết lập quy tắc tự động phân luồng để hệ thống tự chuyển Ticket đến đúng phòng ban hoặc cán bộ cụ thể mà không cần can thiệp thủ công.
* **Đặc tả logic (Specifications):**
  * Cấu trúc quy tắc dạng logic: `IF [Danh mục == X] THEN [Chuyển về Phòng ban Y] AND [Gán cho Cán bộ Z (tùy chọn)]`.
  * Hỗ trợ thiết lập thứ tự ưu tiên áp dụng giữa các quy tắc (Rule Execution Order).
  * Hỗ trợ bật/tắt từng quy tắc độc lập.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-29.1 (Áp dụng đúng quy tắc):** Tạo Ticket thuộc danh mục được cấu hình rule $\rightarrow$ Ticket tự động phân về đúng phòng ban và cán bộ quy định mà không cần thao tác phân loại thủ công.

#### FR-30: Quản lý người dùng và phân quyền vai trò (User & Role RBAC Management)

* **User Story:** Là một Quản trị viên, tôi muốn quản lý tài khoản người dùng và cấp phát vai trò để kiểm soát quyền hạn chặt chẽ trên toàn hệ thống.
* **Đặc tả logic (Specifications):**
  * 04 vai trò cố định: `Sinh viên`, `Cán bộ`, `Quản lý`, `Quản trị viên`.
  * Các chức năng quản trị: Tạo tài khoản cán bộ mới, Cập nhật thông tin, Khóa/Mở khóa tài khoản, Đặt lại mật khẩu mặc định.
  * Phân bổ phòng ban: Mỗi cán bộ/quản lý phải được gán vào ít nhất một phòng ban cụ thể.
  * Không cho phép tự khóa hoặc tự xóa tài khoản Quản trị viên đang đăng nhập.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-30.1 (Phân quyền có hiệu lực ngay):** Cập nhật vai trò của một tài khoản từ "Cán bộ" lên "Quản lý" $\rightarrow$ tài khoản đó có ngay quyền xem Workload và điều chuyển Ticket tại phiên làm việc tiếp theo.
  * **AC-30.2 (Khóa tài khoản):** Khi tài khoản bị khóa, người dùng đó lập tức bị đăng xuất và không thể đăng nhập lại vào hệ thống.

#### FR-31: Quản trị nội dung FAQ & Hướng dẫn (FAQ Management)

* **User Story:** Là một Quản lý hoặc Quản trị viên, tôi muốn tạo và xuất bản các bài viết hướng dẫn giải đáp thắc mắc để sinh viên tự tìm hiểu thông tin.
* **Đặc tả logic (Specifications):**
  * Trình soạn thảo văn bản hỗ trợ định dạng rich text (in đậm, nghiêng, danh sách số, bullet, chèn liên kết).
  * Thông tin bài viết: Tiêu đề bài viết, Chuyên mục, Nội dung chi tiết, Từ khóa tìm kiếm (Tags), Trạng thái (Bản nháp / Xuất bản).
  * Hỗ trợ sắp xếp thứ tự hiển thị ưu tiên của các bài viết nổi bật.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-31.1 (Xuất bản FAQ):** Bài viết sau khi nhấn "Xuất bản" sẽ lập tức hiển thị công khai trên cổng tra cứu FAQ của sinh viên.

#### FR-32: Quản lý mẫu phản hồi chuẩn (Response Template Management)

* **User Story:** Là một Quản lý phòng ban, tôi muốn tạo và chuẩn hóa các mẫu câu trả lời của phòng ban để nâng cao chất lượng và tính chuyên nghiệp trong giao tiếp với sinh viên.
* **Đặc tả logic (Specifications):**
  * Quản lý mẫu câu trả lời theo phạm vi: Mẫu dùng chung toàn trường (do Admin tạo) hoặc Mẫu riêng của phòng ban (do Quản lý phòng ban tạo).
  * Hỗ trợ chèn các trường dữ liệu động (Placeholder): `{ten_sinh_vien}`, `{ma_ticket}`, `{ten_can_bo}`.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-32.1 (Phân quyền mẫu trả lời):** Cán bộ phòng Đào tạo chỉ nhìn thấy mẫu dùng chung toàn trường và mẫu riêng của phòng Đào tạo; không thấy mẫu của phòng Kế toán.

---

### 6.4. Phân hệ Dashboard & Báo cáo Phân tích (Analytics & Reporting)

#### FR-33: Dashboard thống kê trạng thái thời gian thực (Real-time Status Dashboard)

* **User Story:** Là một Quản lý hoặc Quản trị viên, tôi muốn xem biểu đồ tổng quan số lượng Ticket theo trạng thái để nắm bắt nhanh tình hình vận hành của nhà trường.
* **Đặc tả logic (Specifications):**
  * Các thẻ chỉ số (Metric Cards): Tổng số tiếp nhận, Số Ticket Mới tạo, Số đang xử lý, Số chờ sinh viên bổ sung, Số đã hoàn thành.
  * Biểu đồ tròn thể hiện cơ cấu tỷ lệ % theo từng trạng thái.
  * Bộ lọc linh hoạt: Theo toàn trường / theo từng phòng ban; Theo mốc thời gian: Hôm nay, 7 ngày qua, 30 ngày qua, hoặc khoảng ngày tùy chọn.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-33.1 (Cập nhật số liệu thời gian thực):** Dữ liệu thống kê trên Dashboard cập nhật ngay khi có Ticket mới phát sinh hoặc có Ticket chuyển trạng thái.
  * **AC-33.2 (Lọc theo phòng ban):** Quản lý chọn xem phòng Đào tạo $\rightarrow$ toàn bộ số liệu và biểu đồ tự động chuyển đổi hiển thị riêng cho phòng Đào tạo.

#### FR-34: Theo dõi tỷ lệ hoàn thành & Ticket tồn đọng (Completion Rate & Backlog Tracking)

* **User Story:** Là một Quản lý, tôi muốn theo dõi tỷ lệ hoàn thành yêu cầu và lượng Ticket còn tồn đọng qua các ngày để đánh giá khả năng đáp ứng công việc của đội ngũ.
* **Đặc tả logic (Specifications):**
  * Tỷ lệ hoàn thành = $(Số\ Ticket\ Hoàn\ thành / Tổng\ Ticket\ tiếp\ nhận) \times 100\%$.
  * Chỉ số Backlog: Tổng số Ticket chưa hoàn thành đang tồn qua các ngày.
  * Danh sách cảnh báo Top Ticket tồn đọng lâu nhất chưa được xử lý xong.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-34.1 (Hiển thị tỷ lệ và so sánh):** Dashboard thể hiện tỷ lệ % hoàn thành kèm mũi tên chỉ số tăng/giảm so với chu kỳ trước đó.

#### FR-35: Theo dõi thời gian xử lý trung bình (MTTR Analytics)

* **User Story:** Là một Quản lý, tôi muốn biết thời gian trung bình để xử lý xong một Ticket theo từng phòng ban và mức ưu tiên để tìm ra các khâu còn chậm trễ.
* **Đặc tả logic (Specifications):**
  * Chỉ số MTTR (Mean Time To Resolve): Tính từ thời điểm sinh viên tạo Ticket đến thời điểm Ticket chuyển sang `Hoàn thành` lần đầu tiên.
  * Phân rã thời gian xử lý theo từng phòng ban và theo từng mức độ ưu tiên (đơn vị: Giờ).
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-35.1 (Báo cáo MTTR chi tiết):** Hiển thị bảng so sánh thời gian xử lý trung bình giữa các phòng ban, làm nổi bật phòng ban có thời gian xử lý nhanh nhất và chậm nhất.

#### FR-36: Thống kê hiệu suất theo phòng ban và cán bộ (Staff Performance Tracking)

* **User Story:** Là một Quản lý hoặc Quản trị viên, tôi muốn xem bảng tổng hợp hiệu suất của từng cán bộ để đánh giá chất lượng và khối lượng công việc hoàn thành.
* **Đặc tả logic (Specifications):**
  * Bảng danh sách cán bộ với các cột chỉ số:
    * Số Ticket được phân công thụ lý.
    * Số Ticket đã giải quyết hoàn tất.
    * Tỷ lệ giải quyết đúng hạn SLA (%).
    * Điểm đánh giá hài lòng trung bình (CSAT Score / 5 sao).
  * Hỗ trợ nhấp chuột vào từng cột để sắp xếp thứ hạng từ cao xuống thấp.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-36.1 (Bảng hiệu suất minh bạch):** Quản lý xem được đầy đủ số liệu của các nhân sự trực thuộc phòng ban mình, hỗ trợ sắp xếp theo tỷ lệ đúng hạn SLA để đánh giá thi đua.

#### FR-37: Thống kê các nhóm vấn đề phổ biến (Top Categories & Issues Report)

* **User Story:** Là một Quản lý, tôi muốn biết nhóm vấn đề hoặc danh mục nào phát sinh nhiều yêu cầu nhất để nhà trường có phương án truyền thông và cải tiến quy trình chủ động.
* **Đặc tả logic (Specifications):**
  * Biểu đồ cột ngang thể hiện Top 5 hoặc Top 10 danh mục có số lượng Ticket cao nhất trong học kỳ.
  * Nhấp chuột vào một danh mục trên biểu đồ sẽ mở ra danh sách các Ticket chi tiết thuộc danh mục đó.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-37.1 (Xếp hạng chính xác):** Biểu đồ hiển thị đúng thứ tự số lượng Ticket giảm dần của các danh mục theo bộ lọc thời gian đã chọn.

#### FR-38: Phân tích xu hướng Ticket theo thời gian (Ticket Trend Analysis)

* **User Story:** Là một Quản lý, tôi muốn xem biểu đồ xu hướng số lượng yêu cầu theo ngày/tuần/tháng để dự báo nguồn lực nhân sự cần thiết cho các đợt cao điểm.
* **Đặc tả logic (Specifications):**
  * Biểu đồ đường (Line chart) thể hiện tương quan 2 đường: Số lượng Ticket tạo mới và Số lượng Ticket đã hoàn thành theo chuỗi thời gian.
  * Tùy chọn hiển thị bước thời gian theo: Ngày, Tuần, hoặc Tháng.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-38.1 (Biểu đồ xu hướng trực quan):** Biểu đồ phản ánh rõ ràng các đỉnh cao điểm (ví dụ: tuần đăng ký môn học, tuần đóng học phí) với số liệu chính xác khi rê chuột vào từng điểm mốc.

#### FR-39: Báo cáo mức độ hài lòng của sinh viên (CSAT Reporting)

* **User Story:** Là một Quản lý hoặc Quản trị viên, tôi muốn xem báo cáo chi tiết điểm đánh giá hài lòng và nhận xét của sinh viên để nâng cao chất lượng dịch vụ hỗ trợ.
* **Đặc tả logic (Specifications):**
  * Điểm CSAT trung bình toàn trường và theo từng phòng ban (thang điểm 5).
  * Biểu đồ phân bổ tỷ lệ đánh giá: Rất hài lòng (5 sao), Hài lòng (4 sao), Bình thường (3 sao), Không hài lòng (1–2 sao).
  * Bảng trích xuất chi tiết nhận xét đóng góp của sinh viên kèm theo mã Ticket tương ứng.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-39.1 (Tổng hợp điểm CSAT chính xác):** Tỷ lệ % và điểm trung bình được tính toán tự động dựa trên toàn bộ các lượt đánh giá đã gửi.

#### FR-40: Xuất dữ liệu báo cáo định dạng CSV (CSV Data Export)

* **User Story:** Là một Quản lý hoặc Quản trị viên, tôi muốn xuất dữ liệu báo cáo ra tệp CSV để lưu trữ nội bộ và thực hiện các phân tích số liệu nâng cao trên Microsoft Excel.
* **Đặc tả logic (Specifications):**
  * Hỗ trợ xuất các loại báo cáo:
    1. Báo cáo danh sách Ticket chi tiết.
    2. Báo cáo hiệu suất cán bộ theo phòng ban.
    3. Báo cáo kết quả đánh giá hài lòng (CSAT).
  * Dữ liệu xuất theo đúng kết quả bộ lọc ngày và phòng ban đang chọn trên màn hình.
  * **Định dạng chuẩn:** Mã hóa `UTF-8 with BOM` để mở trực tiếp trên Microsoft Excel mà không bị lỗi font chữ Tiếng Việt.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-40.1 (Tải tệp CSV hợp lệ):** Nhấn nút "Xuất CSV" $\rightarrow$ trình duyệt tải về tệp `.csv` trong vòng $\le 3$ giây; mở trên Excel hiển thị đúng 100% tiếng Việt có dấu và đúng các cột dữ liệu.

---

### 6.5. Phân hệ Bảo mật, Xác thực & Trải nghiệm Người dùng (Security, Auth & UX)

#### FR-41: Xác thực tài khoản & Quản lý phiên làm việc (Authentication & Session Management)

* **User Story:** Là một Người dùng (Sinh viên, Cán bộ, Quản lý, Admin), tôi muốn đăng nhập an toàn bằng tài khoản hệ thống để truy cập đúng các tính năng theo quyền hạn của mình.
* **Đặc tả logic (Specifications):**
  * Đăng nhập cục bộ bằng Tên đăng nhập / Email và Mật khẩu.
  * Cơ chế bảo vệ Brute-force: Tự động khóa đăng nhập tạm thời **15 phút** nếu nhập sai mật khẩu liên tiếp **05 lần**.
  * Thời gian hết hạn phiên làm việc (Session Timeout): Tự động đăng xuất sau **08 giờ** liên tục không có thao tác.
  * Điều hướng sau đăng nhập dựa trên vai trò (Role-based Redirect):
    * Sinh viên $\rightarrow$ Cổng tiếp nhận và danh sách Ticket của sinh viên.
    * Cán bộ $\rightarrow$ Hàng đợi Ticket của cán bộ.
    * Quản lý / Admin $\rightarrow$ Màn hình Dashboard quản lý.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-41.1 (Đăng nhập đúng vai trò):** Đăng nhập thành công chuyển hướng đến đúng trang chủ tương ứng với vai trò của người dùng.
  * **AC-41.2 (Khóa tạm thời khi sai mật khẩu):** Nhập sai mật khẩu lần thứ 5 $\rightarrow$ hệ thống hiển thị cảnh báo khóa tài khoản 15 phút và từ chối các yêu cầu đăng nhập tiếp theo trong thời gian này.

#### FR-42: Đặt lại mật khẩu an toàn (Password Reset)

* **User Story:** Là một Người dùng, tôi muốn tự đặt lại mật khẩu qua email khi bị quên để có thể tiếp tục sử dụng hệ thống một cách nhanh chóng và an toàn.
* **Đặc tả logic (Specifications):**
  * Người dùng nhập địa chỉ Email đã đăng ký để yêu cầu đặt lại mật khẩu.
  * Hệ thống gửi một email chứa mã Token/Link đặt lại mật khẩu có thời hạn sử dụng trong vòng **15 phút** và chỉ dùng được **01 lần duy nhất**.
  * Quy chuẩn mật khẩu mới: Tối thiểu 08 ký tự, bao gồm ít nhất chữ hoa, chữ thường và chữ số.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-42.1 (Gửi link đặt lại mật khẩu):** Nhập email hợp lệ $\rightarrow$ hệ thống gửi email xác thực trong vòng $\le 60$ giây.
  * **AC-42.2 (Kiểm tra độ phức tạp mật khẩu):** Hệ thống chặn lưu và báo lỗi nếu mật khẩu mới không đạt độ dài tối thiểu 8 ký tự hoặc thiếu chữ hoa/chữ số.

#### FR-43: Phân quyền truy cập theo 04 vai trò (Role-Based Access Control - RBAC)

* **User Story:** Là một Quản trị viên, tôi muốn hệ thống thực thi kiểm soát truy cập nghiêm ngặt theo 04 vai trò để bảo vệ tính toàn vẹn và bí mật của dữ liệu.
* **Đặc tả logic (Specifications):**
  * Hệ thống phân quyền chặt chẽ cho 04 vai trò:
    * *Sinh viên:* Tạo, theo dõi, trao đổi Ticket của chính mình; tra cứu FAQ; đánh giá CSAT.
    * *Cán bộ xử lý:* Xử lý Ticket thuộc phòng ban mình; cập nhật trạng thái/priority; ghi chú nội bộ; phản hồi sinh viên.
    * *Quản lý phòng ban:* Toàn quyền trong phạm vi phòng ban; theo dõi workload; tái phân công ticket; duyệt FAQ; xem báo cáo.
    * *Quản trị viên (Admin):* Toàn quyền cấu hình hệ thống, người dùng, phòng ban, danh mục, routing rules và báo cáo toàn trường.
  * Kiểm soát ở cả 2 tầng: Tầng Giao diện (Ẩn menu/nút không có quyền) và Tầng API (Trả về mã lỗi `HTTP 403 Forbidden` nếu gọi trái thẩm quyền).
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-43.1 (Chặn truy cập trái phép):** Sinh viên cố tình nhập URL trang quản trị của Cán bộ hoặc gọi API lấy Ticket người khác $\rightarrow$ hệ thống chặn ngay và trả về lỗi 403 Forbidden.

#### FR-44: Kiểm soát quyền truy cập dữ liệu & tệp đính kèm (File Access Security)

* **User Story:** Là một Người dùng, tôi muốn các tài liệu và tệp đính kèm trên Ticket được bảo mật, chỉ những người có trách nhiệm mới có thể truy cập và tải về.
* **Đặc tả logic (Specifications):**
  * Tệp đính kèm không được lưu trữ trong thư mục tĩnh có thể truy cập công khai (No Public URL).
  * Mọi yêu cầu tải tệp phải đi qua API kiểm tra phiên đăng nhập và quyền truy cập đối với Ticket tương ứng, hoặc thông qua Signed URL có thời gian sống ngắn (ví dụ: 05 phút).
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-44.1 (Bảo vệ đường dẫn tệp):** Người dùng chưa đăng nhập hoặc không liên quan đến Ticket khi truy cập đường link tệp đính kèm sẽ nhận thông báo lỗi từ chối truy cập.

#### FR-45: Ghi nhận nhật ký kiểm toán hệ thống (System Audit Trail)

* **User Story:** Là một Quản trị viên, tôi muốn hệ thống tự động ghi nhận các thao tác quản trị và an ninh quan trọng để phục vụ kiểm tra bảo mật và giải quyết sự cố.
* **Đặc tả logic (Specifications):**
  * Hệ thống tự động ghi nhận vào Audit Log các sự kiện:
    * Đăng nhập thất bại liên tiếp nhiều lần.
    * Thay đổi vai trò hoặc thông tin tài khoản người dùng.
    * Thêm, sửa, tắt các Danh mục hoặc Phòng ban.
    * Cập nhật các quy tắc phân luồng (Routing Rules) và cấu hình SLA.
  * Thông tin bản ghi: Timestamp chính xác, User ID thực hiện, Địa chỉ IP, Tên hành động, Chi tiết dữ liệu trước và sau thay đổi.
  * Dữ liệu Audit Log là dữ liệu chỉ đọc (Read-only), không cho phép chỉnh sửa hoặc xóa bởi bất kỳ người dùng nào.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-45.1 (Ghi vết kiểm toán chuẩn xác):** Mọi thao tác cấu hình hệ thống của Admin đều được ghi nhận ngay vào bảng Audit Log với đầy đủ thông tin IP và người thực hiện.

#### FR-46: Sử dụng dữ liệu giả lập trong môi trường phát triển & kiểm thử (Mock Data Enforcement)

* **User Story:** Là một Quản lý dự án, tôi muốn toàn bộ quá trình phát triển, kiểm thử và nghiệm thu chỉ sử dụng dữ liệu giả lập để đảm bảo tuyệt đối an toàn thông tin cá nhân của sinh viên.
* **Đặc tả logic (Specifications):**
  * Tuân thủ đúng Assumption của dự án: Toàn bộ dữ liệu tài khoản sinh viên, email, số điện thoại, MSSV và nội dung ticket trên các môi trường Development, Staging và UAT đều là Mock Data (dữ liệu được sinh ngẫu nhiên).
  * Bộ dữ liệu Seed / Mock Data chuẩn phục vụ kiểm thử và nghiệm thu tối thiểu gồm:
    * **500** tài khoản sinh viên giả lập.
    * **20** tài khoản cán bộ và quản lý thuộc 4 phòng ban.
    * **500** Ticket mẫu ở đầy đủ các trạng thái và danh mục khác nhau.
  * Tuyệt đối không import hoặc sao chép dữ liệu thật của Aurora University vào môi trường kiểm thử.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-46.1 (Nghiệm thu trên Mock Data):** Buổi Demo nghiệm thu chức năng tổng thể với đại diện Aurora University chạy hoàn toàn trên bộ dữ liệu giả lập đã được chuẩn bị trước.

#### FR-47: Giao diện hỗ trợ song ngữ Tiếng Việt & Tiếng Anh (i18n Support)

* **User Story:** Là một Người dùng, tôi muốn dễ dàng chuyển đổi giao diện giữa Tiếng Việt và Tiếng Anh để sử dụng hệ thống thuận tiện theo ngôn ngữ phù hợp.
* **Đặc tả logic (Specifications):**
  * Ngôn ngữ mặc định của hệ thống: **Tiếng Việt**.
  * Cung cấp nút chuyển đổi nhanh ngôn ngữ (VI / EN) tại vị trí cố định trên thanh điều hướng Header.
  * Tùy chọn ngôn ngữ của người dùng được lưu trữ vào LocalStorage/Cookie để giữ nguyên trạng thái cho các lần truy cập sau.
  * Hỗ trợ chuyển đổi 100% các nhãn nút bấm, tiêu đề menu, thông báo lỗi, trạng thái và email mẫu.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-47.1 (Chuyển đổi tức thì):** Khi bấm nút chọn "EN", toàn bộ giao diện lập tức chuyển sang Tiếng Anh mà không cần tải lại toàn bộ trang web.

#### FR-48: Giao diện thích ứng trên Desktop và Mobile Web (Responsive UI)

* **User Story:** Là một Sinh viên hoặc Cán bộ, tôi muốn sử dụng hệ thống một cách mượt mà trên điện thoại di động và máy tính bảng mà không bị vỡ giao diện hay khó thao tác.
* **Đặc tả logic (Specifications):**
  * Thiết kế giao diện tương thích hoàn hảo (Fully Responsive) theo các dải màn hình:
    * Mobile: Độ rộng màn hình $< 768px$.
    * Tablet: Độ rộng màn hình từ $768px$ đến $1023px$.
    * Desktop: Độ rộng màn hình $\ge 1024px$.
  * Trên màn hình di động: Thanh điều hướng chuyển thành menu trượt (Drawer / Hamburger), bảng dữ liệu tự động chuyển thành dạng thẻ (Card view), các nút bấm đạt kích thước tối thiểu $44 \times 44px$ để bấm dễ dàng bằng ngón tay.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-48.1 (Thao tác di động hoàn chỉnh):** Sinh viên có thể hoàn thành toàn bộ luồng tạo Ticket, tra cứu FAQ, đính kèm ảnh chụp từ điện thoại và gửi tin nhắn trao đổi trên các trình duyệt di động (iOS Safari, Android Chrome) mà không gặp lỗi hiển thị hay tràn khung hình.

---

## 7. Technical Specifications

### 7.1. System Architecture

Kiến trúc hệ thống sẽ được thiết kế trong giai đoạn **Tuần 3–5**.

**Chi tiết Architecture:** TBD.

### 7.2. Data Model

Các entity dự kiến:

- User
- Role
- Ticket
- Category
- Department
- Attachment
- Ticket Message
- Internal Note
- Priority
- Routing Rule
- FAQ
- Response Template
- Satisfaction Rating

Schema chi tiết: **TBD**.

### 7.3. API Requirements

Danh sách endpoint cụ thể chưa được Proposal xác định.

**Trạng thái:** TBD – Technical Design.

### 7.4. Third-Party Integrations

- Email Notification.
- Không tích hợp SSO.
- Không tích hợp hệ thống bên thứ ba khác ngoài phạm vi được thống nhất.

### 7.5. Technical Constraints

- Không yêu cầu Aurora University nâng cấp hạ tầng phần cứng/mạng trong phạm vi dự án.
- Không sử dụng dữ liệu thật trong Development/Test nếu chưa được phê duyệt.
- Không triển khai AI/ML hoặc Chatbot trong phiên bản hiện tại.

---

## 8. Dependencies & Risks

### 8.1. Dependencies

Dự án phụ thuộc vào:

- Aurora University cung cấp requirement và quy trình nghiệp vụ đúng thời hạn.
- Aurora University phản hồi và phê duyệt các nội dung cần xác nhận.
- Các phòng ban tham gia UAT.
- Requirement/Scope được khóa theo kế hoạch.

### 8.2. Risks & Mitigation

#### Thay đổi yêu cầu nghiệp vụ

- **Rủi ro:** Thay đổi yêu cầu sau khi phạm vi đã được xác nhận.
- **Xử lý:** Thực hiện Change Request và đánh giá Scope, Timeline, Cost, Resource trước khi triển khai.

#### Yêu cầu ngoài phạm vi

- **Rủi ro:** Phát sinh chức năng không thuộc In-Scope.
- **Xử lý:** Chỉ thực hiện sau khi hai bên thống nhất phạm vi, thời gian và ngân sách bổ sung.

#### Chậm phản hồi từ khách hàng

- **Rủi ro:** Chậm xác nhận Requirement hoặc UAT.
- **Xử lý:** Điều chỉnh kế hoạch tương ứng nếu ảnh hưởng tiến độ.

#### Lỗi kỹ thuật

- **Rủi ro:** Lỗi phát sinh trong development.
- **Xử lý:** Kiểm thử song song và xử lý lỗi sớm.

#### Rủi ro tích hợp

- **Rủi ro:** Lỗi giữa các module.
- **Xử lý:** Kiểm thử từng module trước khi tích hợp toàn hệ thống.

### 8.3. Open Questions

- [ ] Chi tiết Ticket Category?
- [ ] Mapping Category → Department?
- [ ] Các mức Priority cụ thể?
- [ ] Deadline theo từng loại Ticket/Priority?
- [ ] Thời gian cho phép Reopen Ticket?
- [ ] Sự kiện nào kích hoạt Email Notification?
- [ ] Quy tắc Password?
- [ ] Browser/version được hỗ trợ?
- [ ] KPI định lượng cho Success Metrics?

---

## 9. Timeline & Milestones

### 9.1. Development Phases

- **P1 – Tuần 1–2:** Khởi động và xác định yêu cầu.
- **P2 – Tuần 3–5:** Phân tích, Architecture, Database và UI/UX Prototype.
- **P3 – Tuần 6–8:** Nền tảng giao diện, Authentication và RBAC cơ bản.
- **P4 – Tuần 9–12:** Phát triển Core Ticket Workflow.
- **P5 – Tuần 13–15:** Management & Administration.
- **P6 – Tuần 16–18:** Dashboard, Reporting và UX.
- **P7 – Tuần 19–20:** Integration, System Testing và Security Review.
- **P8 – Tuần 21–22:** UAT và hoàn thiện.
- **P9 – Tuần 23:** Go-live và bàn giao.

### 9.2. Kế hoạch Cột mốc & Thanh toán (Key Milestones & Deliverables)

Tổng ngân sách dự án: **700.000.000 VNĐ**. Tiến độ giải ngân và nghiệm thu gắn liền với 05 mốc bàn giao:

| Cột mốc | Thời điểm | Nội dung bàn giao & Tiêu chí đạt | Tỷ lệ | Giá trị (VNĐ) |
| :--- | :--- | :--- | :---: | :---: |
| **Khởi động dự án** | Ký hợp đồng | Ký kết hợp đồng và xác nhận khởi động dự án chính thức. | 30% | 210.000.000 |
| **M1** | Tuần 5 | Hoàn thành UI/UX Prototype, tài liệu phân tích hệ thống và **khóa phạm vi dự án (Scope Baseline Freeze)**. | 20% | 140.000.000 |
| **M2** | Tuần 19–20 | Hoàn tất tích hợp toàn bộ các module và kiểm thử hệ thống (System Testing & Security Review). | 20% | 140.000.000 |
| **M3** | Tuần 21–22 | Đào tạo vận hành, Demo tổng thể hệ thống trên Mock Data, hoàn thành UAT và **Xác nhận Sẵn sàng Go-live (Release Sign-off)**. | 20% | 140.000.000 |
| **M4** | Tuần 23 | Triển khai Production chính thức (Go-live), bàn giao toàn bộ mã nguồn và bộ tài liệu hướng dẫn vận hành. | 10% | 70.000.000 |
| **Tổng cộng** | **23 Tuần** | **Toàn bộ phạm vi In-Scope đã thống nhất** | **100%** | **700.000.000** |

---

## 10. Resources & Team

Core Team gồm:

- Project Manager / BA
- Tech Lead / Solution Architect
- Senior Backend Developer
- Junior Backend Developer
- Senior Frontend Developer
- Junior Frontend Developer
- UI/UX Designer
- QA / Tester
- DevOps Engineer

---

## 11. Nghiệm thu, Bàn giao và Bảo hành (Acceptance & Warranty)

### 11.1. Điều kiện nghiệm thu (UAT & Acceptance Criteria)

Aurora University thực hiện đánh giá phiên bản nghiệm thu dựa trên bộ 03 căn cứ bàn giao chính thức:
1. **Buổi Demo hệ thống tổng thể** chạy trên bộ dữ liệu giả lập (Mock Data).
2. **Báo cáo kết quả kiểm thử hệ thống (QA System Test Summary Report)** xác nhận 100% test case P0 Pass.
3. **Bộ tài liệu bàn giao** (Tài liệu kỹ thuật, Hướng dẫn sử dụng cho Quản trị viên và Cán bộ).

**Quy tắc nghiệm thu:**
- **Thời hạn phản hồi:** Aurora University phản hồi kết quả đánh giá trong vòng **05 ngày làm việc** kể từ khi nhận được thông báo sẵn sàng nghiệm thu kèm tài liệu.
- **Xử lý lỗi In-Scope:** Trường hợp phát hiện lỗi ảnh hưởng đến chức năng thuộc In-Scope, Project Team có trách nhiệm khắc phục và gửi lại phiên bản nghiệm thu để kiểm tra lại.
- **Quy định từ chối:** Việc từ chối nghiệm thu phải được thông báo bằng văn bản chính thức và nêu rõ các nội dung chưa đáp ứng so với phạm vi đã thống nhất.
- **Phân loại lỗi nhỏ (Minor Defects):** Các lỗi nhỏ, lỗi giao diện hoặc lỗi không ảnh hưởng đến chức năng chính **không phải là cơ sở để trì hoãn toàn bộ việc nghiệm thu**; các lỗi này được ghi nhận vào danh sách thống nhất và xử lý trong thời gian bảo hành.
- **Miễn trừ chậm trễ:** Nếu Aurora University không phản hồi trong thời hạn 05 ngày làm việc mà không có lý do bằng văn bản hợp lý, hai bên sẽ xem xét hệ thống đã **đủ điều kiện nghiệm thu** theo các tiêu chí đã thống nhất.

### 11.2. Bàn giao (Deliverables)

Bao gồm:
- Hệ thống phần mềm UniSupport phiên bản chính thức hoạt động trên môi trường triển khai.
- Toàn bộ mã nguồn (Source Code) của dự án.
- Bộ tài liệu kỹ thuật (Architecture, Database Schema, API Docs).
- Tài liệu Hướng dẫn sử dụng cho Cán bộ và Quản trị viên.
- Buổi đào tạo và chuyển giao vận hành trực tiếp cho đại diện Aurora University.

### 11.3. Bảo hành (Warranty Support)

- **Thời gian bảo hành:** **30 ngày** kể từ ngày hai bên ký Biên bản Nghiệm thu và Bàn giao (M4).
- **Phạm vi bảo hành:** Khắc phục các lỗi kỹ thuật phát sinh thuộc phạm vi In-Scope đã bàn giao.
- **Ngoài bảo hành:** Không bao gồm phát triển tính năng mới, chỉnh sửa quy trình ngoài thỏa thuận ban đầu, hoặc các vấn đề do hạ tầng máy chủ của trường gây ra. Mọi yêu cầu mới sẽ được thực hiện qua quy trình Change Request.

---

## 12. Quản lý thay đổi

Mọi thay đổi ngoài phạm vi đã chốt phải tuân theo quy trình:

**Change Request → Phân tích tác động → Đánh giá Scope/Timeline/Cost/Resource → Phê duyệt → Triển khai**

Không đưa requirement mới vào Development nếu chưa được phê duyệt.

---

## 13. Appendix

### 13.1. Tài liệu tham chiếu

- UniSupport Project Proposal.
- UI/UX Prototype – TBD.
- Technical Design Document – TBD.
- Database Design – TBD.
- Team Charter – TBD.

### 13.2. Changelog

- **02/10/2026 – v1.0:** Khởi tạo PRD UniSupport dựa trên Proposal đã thống nhất.
- **03/10/2026 – v1.1:** Chuẩn hóa toàn diện PRD, bổ sung đầy đủ User Stories, Business Rules, AC, NFR và Kế hoạch Milestones & Nghiệm thu từ Proposal.
- **03/10/2026 – v1.2:** Tái cấu trúc toàn bộ Mục 6 sang định dạng phân cấp chuẩn FSD/PRD chuyên nghiệp (User Story, Đặc tả logic, Tiêu chí chấp nhận AC-XX.1, AC-XX.2...) đồng nhất theo mẫu thiết kế được phê duyệt.

### 13.3. Stakeholder Approval

- [ ] Project Manager / BA – TBD
- [ ] Tech Lead – TBD
- [ ] Aurora University Representative – TBD
- [ ] QA Lead – TBD