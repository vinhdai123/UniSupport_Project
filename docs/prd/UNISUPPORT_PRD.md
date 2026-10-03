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

## 4. User Personas và Use Cases

### 4.1. Persona 1 – Sinh viên

- **Vai trò:** Người gửi yêu cầu hỗ trợ.
- **Mục tiêu:** Gửi, theo dõi và trao đổi Ticket nhanh chóng.
- **Khó khăn hiện tại:** Không biết yêu cầu đang được xử lý ở đâu hoặc bởi ai.
- **Mức độ kỹ thuật:** Cơ bản đến trung bình.
- **Bối cảnh sử dụng:** Trình duyệt trên Desktop hoặc Mobile.

### 4.2. Persona 2 – Cán bộ xử lý

- **Vai trò:** Người tiếp nhận và xử lý Ticket.
- **Mục tiêu:** Quản lý Ticket được phân công và phản hồi sinh viên.
- **Khó khăn hiện tại:** Yêu cầu phân tán, khó theo dõi và dễ bỏ sót.
- **Mức độ kỹ thuật:** Trung bình.

### 4.3. Persona 3 – Quản lý

- **Vai trò:** Theo dõi hoạt động hỗ trợ.
- **Mục tiêu:** Theo dõi workload, backlog, deadline và hiệu suất.
- **Mức độ kỹ thuật:** Trung bình.

### 4.4. Persona 4 – Quản trị viên

- **Vai trò:** Quản lý cấu hình hệ thống.
- **Mục tiêu:** Quản lý người dùng, vai trò, danh mục, phòng ban và quy tắc hệ thống.
- **Mức độ kỹ thuật:** Trung bình đến nâng cao.

### 4.5. Use Case chính – Sinh viên tạo Ticket

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

## 5. Yêu cầu sản phẩm

### 5.1. Functional Requirements – Must Have (P0)

#### FR-01 – Tạo Ticket

- **Mô tả:** Cho phép sinh viên tạo yêu cầu hỗ trợ theo danh mục.
- **User Story:** Là Sinh viên, tôi muốn tạo Ticket theo danh mục để yêu cầu của tôi được ghi nhận đúng trên hệ thống.
- **Acceptance Criteria:**
  - [ ] Sinh viên có thể chọn danh mục và gửi Ticket.
  - [ ] Hệ thống tự động tạo Ticket ID sau khi tạo thành công.

#### FR-02 – Đính kèm tài liệu

- **Mô tả:** Cho phép sinh viên đính kèm tài liệu hoặc hình ảnh vào Ticket.
- **Acceptance Criteria:**
  - [ ] Người dùng có thể thêm tệp đính kèm vào Ticket.
  - [ ] Tệp đính kèm được liên kết đúng với Ticket tương ứng.

#### FR-03 – Thông báo Ticket

- **Mô tả:** Gửi thông báo khi Ticket có cập nhật quan trọng.
- **Acceptance Criteria:**
  - [ ] Hệ thống gửi thông báo trên UniSupport.
  - [ ] Hệ thống gửi Email đối với các cập nhật quan trọng.

#### FR-04 – Theo dõi trạng thái Ticket

- **Mô tả:** Cho phép sinh viên theo dõi trạng thái xử lý.
- **Acceptance Criteria:**
  - [ ] Hiển thị các trạng thái: Mới tạo, Đang xử lý, Cần bổ sung, Hoàn thành.

#### FR-05 – Trao đổi trên Ticket

- **Mô tả:** Cho phép sinh viên và cán bộ trao đổi trực tiếp trên Ticket.
- **Acceptance Criteria:**
  - [ ] Sinh viên có thể gửi nội dung trao đổi.
  - [ ] Cán bộ có thể phản hồi trên cùng Ticket.

#### FR-06 – Bổ sung thông tin

- **Mô tả:** Cho phép sinh viên bổ sung thông tin hoặc tài liệu khi được yêu cầu.
- **Acceptance Criteria:**
  - [ ] Sinh viên có thể bổ sung nội dung hoặc tài liệu vào Ticket đang xử lý.

#### FR-07 – Mở lại Ticket

- **Mô tả:** Cho phép sinh viên mở lại Ticket trong thời gian quy định.
- **Acceptance Criteria:**
  - [ ] Ticket đủ điều kiện có thể được mở lại.
  - [ ] Thời gian cho phép mở lại: **TBD**.

#### FR-08 – Lịch sử Ticket

- **Mô tả:** Hiển thị lịch sử xử lý Ticket.
- **Acceptance Criteria:**
  - [ ] Người dùng có thể xem các thay đổi trạng thái và hoạt động liên quan đến Ticket theo quyền được cấp.

#### FR-09 – FAQ / Knowledge Base

- **Mô tả:** Cho phép sinh viên tra cứu hướng dẫn trước khi tạo Ticket.
- **Acceptance Criteria:**
  - [ ] Sinh viên có thể xem FAQ theo chủ đề.
  - [ ] Sinh viên có thể tìm kiếm hướng dẫn.

#### FR-10 – Đánh giá mức độ hài lòng

- **Mô tả:** Cho phép sinh viên đánh giá sau khi Ticket hoàn thành.
- **Acceptance Criteria:**
  - [ ] Chức năng đánh giá chỉ khả dụng sau khi Ticket hoàn thành.

---

### 5.2. Staff Module

#### FR-11 – Ticket Queue

- Hiển thị danh sách Ticket cần xử lý.

#### FR-12 – Phân luồng Ticket

- Tự động phân luồng Ticket theo danh mục/phòng ban đã cấu hình.

#### FR-13 – Phân công Ticket

- Cho phép phân công Ticket cho cán bộ xử lý.

#### FR-14 – Chuyển tiếp / Chuyển cấp

- Cho phép chuyển Ticket sang phòng ban khác hoặc chuyển cấp xử lý.

#### FR-15 – Tìm kiếm và lọc

- Cho phép tìm kiếm, lọc và sắp xếp Ticket theo trạng thái, danh mục, Priority và thời gian.

#### FR-16 – Cập nhật trạng thái

- Cho phép cán bộ thay đổi trạng thái Ticket.

#### FR-17 – Priority

- Cho phép thiết lập hoặc cập nhật mức độ ưu tiên.

#### FR-18 – Yêu cầu bổ sung

- Cho phép cán bộ yêu cầu sinh viên bổ sung thông tin.

#### FR-19 – Ghi chú nội bộ

- Cho phép cán bộ thêm ghi chú nội bộ trên Ticket.

#### FR-20 – Phản hồi Ticket

- Cho phép cán bộ gửi phản hồi chính thức cho sinh viên.

#### FR-21 – Mẫu phản hồi

- Cho phép cán bộ sử dụng Response Template có sẵn.

#### FR-22 – Nhật ký Ticket

- Lưu lịch sử thao tác và thay đổi trạng thái.

---

### 5.3. Management & Administration Module

#### FR-23 – Theo dõi hoạt động

- Theo dõi Ticket theo phòng ban/cán bộ.
- Theo dõi backlog và workload.

#### FR-24 – Phân công lại

- Cho phép quản lý điều chuyển hoặc phân công lại Ticket.

#### FR-25 – Quản lý thời hạn

- Thiết lập thời hạn theo loại Ticket hoặc Priority.
- Theo dõi thời gian xử lý.
- Cảnh báo Ticket sắp đến hạn hoặc quá hạn.

#### FR-26 – Cấu hình hệ thống

- Quản lý danh mục yêu cầu.
- Quản lý phòng ban.
- Quản lý Priority.
- Cấu hình Routing Rule.
- Quản lý tài khoản và vai trò.
- Quản lý FAQ / Knowledge Base.
- Quản lý Response Template.

---

### 5.4. Dashboard & Reporting

#### FR-27 – Dashboard

- Thống kê Ticket theo trạng thái.
- Theo dõi tỷ lệ hoàn thành và backlog.
- Theo dõi thời gian xử lý trung bình.
- Theo dõi hiệu suất theo phòng ban/cán bộ.

#### FR-28 – Reporting

- Thống kê nhóm vấn đề phổ biến.
- Phân tích xu hướng Ticket theo thời gian.
- Báo cáo mức độ hài lòng.
- Xuất báo cáo CSV.

---

### 5.5. Authentication & Security

#### FR-29 – Authentication

- Đăng nhập bằng tài khoản UniSupport.
- Hỗ trợ đặt lại mật khẩu.

#### FR-30 – RBAC

- Hỗ trợ 4 vai trò: Sinh viên, Cán bộ, Quản lý, Quản trị viên.
- Phân quyền chức năng và dữ liệu theo vai trò.

#### FR-31 – Security

- Kiểm soát quyền truy cập dữ liệu.
- Kiểm soát quyền truy cập tệp đính kèm.
- Ghi nhận các thao tác quan trọng.

---

## 6. Non-Functional Requirements

### 6.1. Giao diện và khả năng sử dụng

- Hỗ trợ Tiếng Việt và Tiếng Anh.
- Responsive trên Desktop và Mobile.
- Giao diện đơn giản, nhất quán và dễ sử dụng.

### 6.2. Bảo mật và quyền riêng tư

- Kiểm soát quyền truy cập theo vai trò.
- Kiểm soát truy cập dữ liệu và file đính kèm.
- Ghi nhận các thao tác quan trọng.
- Quy chuẩn mã hóa và chính sách dữ liệu chi tiết: **TBD**.

### 6.3. Hiệu năng

Các chỉ số cụ thể như thời gian phản hồi, thời gian tải trang và số người dùng đồng thời chưa được Proposal xác định.

**Trạng thái:** TBD.

### 6.4. Khả năng mở rộng

Hệ thống được xây dựng để phục vụ quy mô khoảng **3.000 sinh viên** ở phiên bản hiện tại.

Yêu cầu mở rộng vượt quy mô trên: **TBD**.

### 6.5. Nền tảng hỗ trợ

- Web Responsive trên Desktop và Mobile.
- Không phát triển Native Mobile App.
- Danh sách browser/version chính thức: **TBD**.

---

## 7. User Personas, Use Cases & Product Requirements

### 7.1. User Personas & Use Cases

#### 7.1.1. Persona 1 – Sinh viên

- **Vai trò:** Người gửi yêu cầu hỗ trợ.
- **Mục tiêu:** Gửi, theo dõi và trao đổi Ticket nhanh chóng.
- **Khó khăn hiện tại:** Không biết yêu cầu đang được xử lý ở đâu hoặc bởi ai.
- **Mức độ kỹ thuật:** Cơ bản đến trung bình.
- **Bối cảnh sử dụng:** Trình duyệt trên Desktop hoặc Mobile.

#### 7.1.2. Persona 2 – Cán bộ xử lý

- **Vai trò:** Người tiếp nhận và xử lý Ticket.
- **Mục tiêu:** Quản lý Ticket được phân công và phản hồi sinh viên.
- **Khó khăn hiện tại:** Yêu cầu phân tán, khó theo dõi và dễ bỏ sót.
- **Mức độ kỹ thuật:** Trung bình.

#### 7.1.3. Persona 3 – Quản lý

- **Vai trò:** Theo dõi hoạt động hỗ trợ.
- **Mục tiêu:** Theo dõi workload, backlog, deadline và hiệu suất.
- **Mức độ kỹ thuật:** Trung bình.

#### 7.1.4. Persona 4 – Quản trị viên

- **Vai trò:** Quản lý cấu hình hệ thống.
- **Mục tiêu:** Quản lý người dùng, vai trò, danh mục, phòng ban và quy tắc hệ thống.
- **Mức độ kỹ thuật:** Trung bình đến nâng cao.

#### 7.1.5. Use Case chính – Sinh viên tạo Ticket

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

### 7.2. Functional Requirements – Must Have (P0)

#### FR-01 – Tạo Ticket

- **Mô tả:** Cho phép sinh viên tạo yêu cầu hỗ trợ theo danh mục.
- **User Story:** Là Sinh viên, tôi muốn tạo Ticket theo danh mục để yêu cầu của tôi được ghi nhận đúng trên hệ thống.
- **Acceptance Criteria:**
  - [ ] Sinh viên có thể chọn danh mục và gửi Ticket.
  - [ ] Hệ thống tự động tạo Ticket ID sau khi tạo thành công.

#### FR-02 – Đính kèm tài liệu

- **Mô tả:** Cho phép sinh viên đính kèm tài liệu hoặc hình ảnh vào Ticket.
- **Acceptance Criteria:**
  - [ ] Người dùng có thể thêm tệp đính kèm vào Ticket.
  - [ ] Tệp đính kèm được liên kết đúng với Ticket tương ứng.

#### FR-03 – Thông báo Ticket

- **Mô tả:** Gửi thông báo khi Ticket có cập nhật quan trọng.
- **Acceptance Criteria:**
  - [ ] Hệ thống gửi thông báo trên UniSupport.
  - [ ] Hệ thống gửi Email đối với các cập nhật quan trọng.

#### FR-04 – Theo dõi trạng thái Ticket

- **Mô tả:** Cho phép sinh viên theo dõi trạng thái xử lý.
- **Acceptance Criteria:**
  - [ ] Hiển thị các trạng thái: Mới tạo, Đang xử lý, Cần bổ sung, Hoàn thành.

#### FR-05 – Trao đổi trên Ticket

- **Mô tả:** Cho phép sinh viên và cán bộ trao đổi trực tiếp trên Ticket.
- **Acceptance Criteria:**
  - [ ] Sinh viên có thể gửi nội dung trao đổi.
  - [ ] Cán bộ có thể phản hồi trên cùng Ticket.

#### FR-06 – Bổ sung thông tin

- **Mô tả:** Cho phép sinh viên bổ sung thông tin hoặc tài liệu khi được yêu cầu.
- **Acceptance Criteria:**
  - [ ] Sinh viên có thể bổ sung nội dung hoặc tài liệu vào Ticket đang xử lý.

#### FR-07 – Mở lại Ticket

- **Mô tả:** Cho phép sinh viên mở lại Ticket trong thời gian quy định.
- **Acceptance Criteria:**
  - [ ] Ticket đủ điều kiện có thể được mở lại.
  - [ ] Thời gian cho phép mở lại: **TBD**.

#### FR-08 – Lịch sử Ticket

- **Mô tả:** Hiển thị lịch sử xử lý Ticket.
- **Acceptance Criteria:**
  - [ ] Người dùng có thể xem các thay đổi trạng thái và hoạt động liên quan đến Ticket theo quyền được cấp.

#### FR-09 – FAQ / Knowledge Base

- **Mô tả:** Cho phép sinh viên tra cứu hướng dẫn trước khi tạo Ticket.
- **Acceptance Criteria:**
  - [ ] Sinh viên có thể xem FAQ theo chủ đề.
  - [ ] Sinh viên có thể tìm kiếm hướng dẫn.

#### FR-10 – Đánh giá mức độ hài lòng

- **Mô tả:** Cho phép sinh viên đánh giá sau khi Ticket hoàn thành.
- **Acceptance Criteria:**
  - [ ] Chức năng đánh giá chỉ khả dụng sau khi Ticket hoàn thành.

---

### 7.3. Staff Module

#### FR-11 – Ticket Queue

- Hiển thị danh sách Ticket cần xử lý.

#### FR-12 – Phân luồng Ticket

- Tự động phân luồng Ticket theo danh mục/phòng ban đã cấu hình.

#### FR-13 – Phân công Ticket

- Cho phép phân công Ticket cho cán bộ xử lý.

#### FR-14 – Chuyển tiếp / Chuyển cấp

- Cho phép chuyển Ticket sang phòng ban khác hoặc chuyển cấp xử lý.

#### FR-15 – Tìm kiếm và lọc

- Cho phép tìm kiếm, lọc và sắp xếp Ticket theo trạng thái, danh mục, Priority và thời gian.

#### FR-16 – Cập nhật trạng thái

- Cho phép cán bộ thay đổi trạng thái Ticket.

#### FR-17 – Priority

- Cho phép thiết lập hoặc cập nhật mức độ ưu tiên.

#### FR-18 – Yêu cầu bổ sung

- Cho phép cán bộ yêu cầu sinh viên bổ sung thông tin.

#### FR-19 – Ghi chú nội bộ

- Cho phép cán bộ thêm ghi chú nội bộ trên Ticket.

#### FR-20 – Phản hồi Ticket

- Cho phép cán bộ gửi phản hồi chính thức cho sinh viên.

#### FR-21 – Mẫu phản hồi

- Cho phép cán bộ sử dụng Response Template có sẵn.

#### FR-22 – Nhật ký Ticket

- Lưu lịch sử thao tác và thay đổi trạng thái.

---

### 7.4. Management & Administration Module

#### FR-23 – Theo dõi hoạt động

- Theo dõi Ticket theo phòng ban/cán bộ.
- Theo dõi backlog và workload.

#### FR-24 – Phân công lại

- Cho phép quản lý điều chuyển hoặc phân công lại Ticket.

#### FR-25 – Quản lý thời hạn

- Thiết lập thời hạn theo loại Ticket hoặc Priority.
- Theo dõi thời gian xử lý.
- Cảnh báo Ticket sắp đến hạn hoặc quá hạn.

#### FR-26 – Cấu hình hệ thống

- Quản lý danh mục yêu cầu.
- Quản lý phòng ban.
- Quản lý Priority.
- Cấu hình Routing Rule.
- Quản lý tài khoản và vai trò.
- Quản lý FAQ / Knowledge Base.
- Quản lý Response Template.

---

### 7.5. Dashboard & Reporting

#### FR-27 – Dashboard

- Thống kê Ticket theo trạng thái.
- Theo dõi tỷ lệ hoàn thành và backlog.
- Theo dõi thời gian xử lý trung bình.
- Theo dõi hiệu suất theo phòng ban/cán bộ.

#### FR-28 – Reporting

- Thống kê nhóm vấn đề phổ biến.
- Phân tích xu hướng Ticket theo thời gian.
- Báo cáo mức độ hài lòng.
- Xuất báo cáo CSV.

---

### 7.6. Authentication & Security

#### FR-29 – Authentication

- Đăng nhập bằng tài khoản UniSupport.
- Hỗ trợ đặt lại mật khẩu.

#### FR-30 – RBAC

- Hỗ trợ 4 vai trò: Sinh viên, Cán bộ, Quản lý, Quản trị viên.
- Phân quyền chức năng và dữ liệu theo vai trò.

#### FR-31 – Security

- Kiểm soát quyền truy cập dữ liệu.
- Kiểm soát quyền truy cập tệp đính kèm.
- Ghi nhận các thao tác quan trọng.

---

## 8. Technical Specifications

### 8.1. System Architecture

Kiến trúc hệ thống sẽ được thiết kế trong giai đoạn **Tuần 3–5**.

**Chi tiết Architecture:** TBD.

### 8.2. Data Model

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

### 8.3. API Requirements

Danh sách endpoint cụ thể chưa được Proposal xác định.

**Trạng thái:** TBD – Technical Design.

### 8.4. Third-Party Integrations

- Email Notification.
- Không tích hợp SSO.
- Không tích hợp hệ thống bên thứ ba khác ngoài phạm vi được thống nhất.

### 8.5. Technical Constraints

- Không yêu cầu Aurora University nâng cấp hạ tầng phần cứng/mạng trong phạm vi dự án.
- Không sử dụng dữ liệu thật trong Development/Test nếu chưa được phê duyệt.
- Không triển khai AI/ML hoặc Chatbot trong phiên bản hiện tại.

---

## 9. Dependencies & Risks

### 9.1. Dependencies

Dự án phụ thuộc vào:

- Aurora University cung cấp requirement và quy trình nghiệp vụ đúng thời hạn.
- Aurora University phản hồi và phê duyệt các nội dung cần xác nhận.
- Các phòng ban tham gia UAT.
- Requirement/Scope được khóa theo kế hoạch.

### 9.2. Risks & Mitigation

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

### 9.3. Open Questions

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

## 10. Timeline & Milestones

### 10.1. Development Phases

- **P1 – Tuần 1–2:** Khởi động và xác định yêu cầu.
- **P2 – Tuần 3–5:** Phân tích, Architecture, Database và UI/UX Prototype.
- **P3 – Tuần 6–8:** Nền tảng giao diện, Authentication và RBAC cơ bản.
- **P4 – Tuần 9–12:** Phát triển Core Ticket Workflow.
- **P5 – Tuần 13–15:** Management & Administration.
- **P6 – Tuần 16–18:** Dashboard, Reporting và UX.
- **P7 – Tuần 19–20:** Integration, System Testing và Security Review.
- **P8 – Tuần 21–22:** UAT và hoàn thiện.
- **P9 – Tuần 23:** Go-live và bàn giao.

### 10.2. Key Milestones

- **M1 – Tuần 5:** Hoàn thành Prototype và khóa phạm vi.
- **M2 – Tuần 19–20:** Hoàn tất Integration và System Testing.
- **M3 – Tuần 21–22:** UAT và nghiệm thu.
- **M4 – Tuần 23:** Go-live và bàn giao.

---

## 11. Resources & Team

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

## 12. Nghiệm thu, Go-live và Post-Launch

### 12.1. UAT

- Aurora University thực hiện UAT trong Tuần 21–22.
- Phản hồi UAT trong vòng **05 ngày làm việc** kể từ khi nhận phiên bản nghiệm thu.
- Lỗi thuộc In-Scope phải được Project Team xử lý và gửi lại phiên bản nghiệm thu.

### 12.2. Bàn giao

Bao gồm:

- Hệ thống UniSupport phiên bản chính thức.
- Mã nguồn.
- Tài liệu kỹ thuật.
- Hướng dẫn sử dụng.
- Hướng dẫn sử dụng cho đại diện Aurora University.

### 12.3. Warranty

**30 ngày kể từ ngày ký biên bản nghiệm thu và bàn giao.**

### 12.4. Post-Launch

Trong thời gian Warranty:

- Theo dõi lỗi thuộc phạm vi đã bàn giao.
- Sửa lỗi thuộc In-Scope.
- Các yêu cầu chức năng mới được xử lý thông qua Change Request.

---

## 13. Quản lý thay đổi

Mọi thay đổi ngoài phạm vi đã chốt phải tuân theo quy trình:

**Change Request → Phân tích tác động → Đánh giá Scope/Timeline/Cost/Resource → Phê duyệt → Triển khai**

Không đưa requirement mới vào Development nếu chưa được phê duyệt.

---


## 14. Appendix

### 14.1. Tài liệu tham chiếu

- UniSupport Project Proposal.
- UI/UX Prototype – TBD.
- Technical Design Document – TBD.
- Database Design – TBD.
- Team Charter – TBD.


### 14.2. Changelog

- **02/10/2026 – v1.0:** Khởi tạo PRD UniSupport dựa trên Proposal đã thống nhất.


### 14.3. Stakeholder Approval

- [ ] Project Manager / BA – TBD
- [ ] Tech Lead – TBD
- [ ] Aurora University Representative – TBD
- [ ] QA Lead – TBD



