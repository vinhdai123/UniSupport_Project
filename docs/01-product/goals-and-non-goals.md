# GOALS & NON-GOALS – UNISUPPORT

## 1. Mục tiêu dự án (Goals)

### 1.1. Mục tiêu nghiệp vụ (Business Goals)

#### BG-01 – Quản lý tập trung yêu cầu hỗ trợ

Xây dựng cổng hỗ trợ trực tuyến tập trung để tiếp nhận, phân loại,
phân luồng và quản lý yêu cầu hỗ trợ cho quy mô khoảng 3.000 sinh viên
Aurora University.

#### BG-02 – Hỗ trợ quy trình xử lý Ticket tập trung

Số hóa và hỗ trợ việc tiếp nhận, phân loại, phân luồng và theo dõi
quá trình xử lý Ticket giữa các phòng ban trên một hệ thống thống nhất.

UniSupport hỗ trợ quy trình nghiệp vụ hiện tại và không thay thế
hoặc tái thiết kế quy trình chuyên môn của Aurora University.

#### BG-03 – Nâng cao khả năng giám sát

Hỗ trợ nhà trường theo dõi:

- Ticket tồn đọng.
- Ticket sắp đến hạn hoặc quá hạn.
- Khối lượng công việc của cán bộ.
- Thời gian xử lý.
- Hiệu suất xử lý theo phòng ban và cán bộ.

#### BG-04 – Hỗ trợ báo cáo và ra quyết định

Cung cấp Dashboard và báo cáo phục vụ công tác quản lý, bao gồm:

- Tình trạng Ticket.
- Tỷ lệ hoàn thành.
- Thời gian xử lý trung bình.
- Các nhóm vấn đề phổ biến.
- Xu hướng Ticket theo thời gian.
- Mức độ hài lòng của sinh viên.

---

### 1.2. Mục tiêu người dùng (User Goals)

#### UG-01 – Student

Sinh viên có thể gửi, theo dõi và trao đổi về yêu cầu hỗ trợ trên
một hệ thống tập trung, đồng thời tra cứu thông tin tự hỗ trợ khi cần.

#### UG-02 – Staff

Cán bộ có thể tiếp nhận, xử lý và phối hợp xử lý Ticket trong phạm vi
được phân công trên một giao diện tập trung.

#### UG-03 – Manager

Quản lý có thể giám sát tiến độ, workload, thời hạn xử lý và hiệu suất
trong phạm vi quản lý để hỗ trợ điều phối công việc.

#### UG-04 – Administrator

Quản trị viên có thể quản lý các cấu hình và dữ liệu nền cần thiết
để hệ thống UniSupport hoạt động nhất quán.

> Chi tiết trách nhiệm, phạm vi sử dụng và chức năng của từng Role
> được mô tả tại `actors-roles.md` và các PRD Module tương ứng.

---

## 2. Mục tiêu ngoài phạm vi (Non-Goals)

### NG-01 – Không thay đổi quy trình nghiệp vụ

UniSupport không xây dựng lại hoặc thay đổi các quy trình nghiệp vụ
hiện có của Aurora University.

---

### NG-02 – Không phát triển Mobile App riêng

Không phát triển Native Mobile App cho iOS hoặc Android.

UniSupport cung cấp giao diện Web Responsive trên Desktop và Mobile.

---

### NG-03 – Không tích hợp xác thực bên ngoài

Không tích hợp:

- Single Sign-On (SSO).
- External Authentication Provider.

UniSupport sử dụng tài khoản nội bộ của hệ thống.

---

### NG-04 – Không triển khai AI / ML / Chatbot

Không phát triển:

- AI.
- Machine Learning.
- Chatbot.
- Các chức năng thông minh ngoài phạm vi đã thống nhất.

---

### NG-05 – Không chuyển đổi toàn bộ dữ liệu lịch sử

Project Team không chịu trách nhiệm:

- Thu thập.
- Làm sạch.
- Chuẩn hóa.
- Chuyển đổi toàn bộ dữ liệu lịch sử

thay cho Aurora University.

---

### NG-06 – Không cung cấp hạ tầng phần cứng

Dự án không bao gồm việc cung cấp hoặc nâng cấp:

- Phần cứng.
- Máy chủ vật lý.
- Hạ tầng mạng của Aurora University.

---

### NG-07 – Không tích hợp hệ thống bên thứ ba ngoài phạm vi

Không tích hợp các hệ thống bên thứ ba ngoài những hệ thống
đã được thống nhất trong phạm vi dự án.

---

### NG-08 – Không thay thế nghiệp vụ chuyên môn của phòng ban

UniSupport hỗ trợ tiếp nhận, quản lý và theo dõi yêu cầu.

Hệ thống không trực tiếp thực hiện nghiệp vụ chuyên môn
thay cho các phòng ban của Aurora University.

---

### NG-09 – Không vận hành dài hạn

Dự án không bao gồm hoạt động vận hành, bảo trì và hỗ trợ dài hạn
sau bàn giao.

Phạm vi hỗ trợ sau bàn giao chỉ áp dụng trong thời gian bảo hành
30 ngày theo Proposal.

---

## 3. Nguyên tắc quản lý phạm vi mục tiêu

- Goals phải được triển khai trong phạm vi In-Scope đã thống nhất.
- Non-Goals không thuộc trách nhiệm triển khai của Project Team.
- Các yêu cầu ngoài In-Scope phải được xử lý thông qua Change Request.
- Change Request phải được đánh giá tác động đến:
  - Phạm vi.
  - Tiến độ.
  - Chi phí.
  - Nguồn lực.
- Chỉ triển khai thay đổi sau khi các bên liên quan thống nhất.