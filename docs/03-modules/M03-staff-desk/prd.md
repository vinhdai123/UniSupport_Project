# MODULE M03: STAFF DESK (KHÔNG GIAN CÁN BỘ)

# 1. Functional Requirements

## FR-STF-01 – Hàng đợi xử lý tập trung

### User Story

Là **Cán bộ xử lý**, tôi muốn xem tập trung các Ticket thuộc phạm vi xử lý của mình để có thể theo dõi, tìm kiếm và lựa chọn Ticket cần xử lý.

### Input

- Người dùng Staff hiện tại.
- Trạng thái Ticket.
- Danh mục Ticket.
- Mức độ ưu tiên.
- Thời gian.
- Từ khóa tìm kiếm.

> Các trường hiển thị cụ thể trên Ticket Queue và Default Sorting: **TBD – Pending Confirmation**.

### Processing

1. Staff truy cập Staff Desk.
2. Hệ thống xác định Staff đang đăng nhập.
3. Hệ thống xác định phạm vi dữ liệu Staff được phép truy cập.
4. Hệ thống lấy danh sách Ticket thuộc phạm vi đó.
5. Hệ thống hiển thị danh sách Ticket cần xử lý.
6. Staff có thể nhập từ khóa để tìm kiếm Ticket.
7. Staff có thể lọc Ticket theo:
   - Trạng thái.
   - Danh mục.
   - Mức độ ưu tiên.
   - Thời gian.
8. Staff có thể sắp xếp Ticket theo thời gian.
9. Khi Staff thay đổi điều kiện tìm kiếm/lọc/sắp xếp, hệ thống cập nhật danh sách tương ứng.
10. Staff có thể chọn một Ticket để mở chi tiết và tiếp tục xử lý.

### Output

Danh sách Ticket thuộc phạm vi Staff được phép truy cập.

Thông tin hiển thị phải đủ để Staff nhận diện và lựa chọn Ticket cần xử lý.

### Acceptance Criteria

**AC1 – Hiển thị Ticket Queue**

- Given: Staff đã đăng nhập và có quyền sử dụng Staff Desk.
- When: Staff truy cập Ticket Queue.
- Then: Hệ thống hiển thị danh sách Ticket thuộc phạm vi dữ liệu được cấp quyền.

**AC2 – Data Scope**

- Given: Staff đang xem Ticket Queue.
- When: Hệ thống tải danh sách.
- Then: Không hiển thị Ticket ngoài phạm vi dữ liệu Staff được phép truy cập.

**AC3 – Search**

- Given: Ticket Queue đang được hiển thị.
- When: Staff nhập từ khóa tìm kiếm.
- Then: Hệ thống trả về các Ticket phù hợp với điều kiện tìm kiếm.

**AC4 – Filter theo trạng thái**

- Given: Staff chọn một trạng thái.
- When: Bộ lọc được áp dụng.
- Then: Danh sách chỉ hiển thị Ticket phù hợp với trạng thái được chọn.

**AC5 – Filter theo danh mục**

- Given: Staff chọn một Category.
- When: Bộ lọc được áp dụng.
- Then: Danh sách chỉ hiển thị Ticket thuộc Category tương ứng.

**AC6 – Filter theo Priority**

- Given: Staff chọn một Priority.
- When: Bộ lọc được áp dụng.
- Then: Danh sách chỉ hiển thị Ticket có Priority phù hợp.

**AC7 – Sort theo thời gian**

- Given: Staff chọn điều kiện sắp xếp theo thời gian.
- When: Điều kiện được áp dụng.
- Then: Danh sách Ticket được sắp xếp tương ứng.

---

## FR-STF-02 – Tự động phân luồng Ticket

### User Story

Là **Cán bộ xử lý**, tôi muốn Ticket được tự động phân luồng theo danh mục và phòng ban để yêu cầu được chuyển đến đúng đơn vị phụ trách.

### Input

- Ticket.
- Danh mục của Ticket.
- Routing Rule đã được cấu hình.
- Danh sách phòng ban trong hệ thống.

> Quan hệ cụ thể giữa Category và Department: **TBD – Pending Confirmation**.

### Processing

1. Ticket được tạo thành công.
2. Hệ thống đọc Category của Ticket.
3. Hệ thống tìm Routing Rule tương ứng với Category.
4. Hệ thống xác định Department phù hợp.
5. Ticket được liên kết với Department được xác định.
6. Ticket xuất hiện trong phạm vi xử lý của đơn vị tương ứng.

### Output

- Ticket được xác định phòng ban xử lý.
- Thông tin Department phụ trách được liên kết với Ticket.

### Acceptance Criteria

**AC1 – Routing theo Category**

- Given: Ticket có Category hợp lệ.
- When: Routing Process được thực hiện.
- Then: Hệ thống sử dụng Routing Rule tương ứng với Category.

**AC2 – Gán Department**

- Given: Có Routing Rule phù hợp.
- When: Hệ thống hoàn tất Routing.
- Then: Ticket được gắn với Department tương ứng.

**AC3 – Sử dụng cấu hình Routing**

- Given: Routing Rule đã được Administrator cấu hình.
- When: Ticket mới cần phân luồng.
- Then: Hệ thống sử dụng Routing Rule đang có hiệu lực.

> Cách xử lý khi không tìm thấy Routing Rule: **TBD – Pending Confirmation**.

---

## FR-STF-03 – Phân công Ticket cho cán bộ

### User Story

Là **Cán bộ có quyền phân công**, tôi muốn giao Ticket cho cán bộ xử lý phù hợp để xác định rõ người chịu trách nhiệm xử lý yêu cầu.

### Input

- Ticket cần phân công.
- Cán bộ được chọn làm người phụ trách.

> Đối tượng cụ thể có quyền thực hiện Assignment: **TBD – Pending Confirmation**.

### Processing

1. Người dùng có quyền mở Ticket cần phân công.
2. Chọn chức năng phân công Ticket.
3. Hệ thống hiển thị các Staff có thể được lựa chọn theo phạm vi phù hợp.
4. Người dùng chọn Staff nhận xử lý.
5. Hệ thống kiểm tra quyền thực hiện Assignment.
6. Nếu hợp lệ:
   - Cập nhật người phụ trách Ticket.
   - Ghi nhận thay đổi vào lịch sử Ticket.
7. Ticket được hiển thị với Staff đang phụ trách hiện tại.

### Output

- Ticket có Assignee.
- Thông tin Staff phụ trách hiện tại được cập nhật.

### Acceptance Criteria

**AC1 – Phân công thành công**

- Given: Người dùng có quyền phân công.
- When: Chọn Ticket và Staff hợp lệ.
- Then: Ticket được giao cho Staff được chọn.

**AC2 – Hiển thị Assignee**

- Given: Ticket đã được phân công.
- When: Mở Ticket.
- Then: Hệ thống hiển thị Staff đang phụ trách.

**AC3 – Ghi nhận lịch sử**

- Given: Assignment được thay đổi.
- When: Hệ thống lưu thay đổi.
- Then: Hoạt động phân công được ghi nhận trong lịch sử Ticket.

---

## FR-STF-04 – Chuyển tiếp / Chuyển cấp Ticket

### User Story

Là **Cán bộ xử lý**, tôi muốn chuyển tiếp hoặc chuyển cấp Ticket khi yêu cầu cần được xử lý bởi đơn vị hoặc cấp phù hợp hơn.

### Input

- Ticket.
- Loại thao tác:
  - Chuyển tiếp.
  - Chuyển cấp.
- Đơn vị hoặc đối tượng tiếp nhận.

> Danh sách đối tượng có thể nhận Transfer/Escalation và việc có bắt buộc nhập lý do hay không: **TBD – Pending Confirmation**.

### Processing

1. Staff mở Ticket.
2. Staff chọn chức năng Chuyển tiếp hoặc Chuyển cấp.
3. Staff chọn đơn vị hoặc đối tượng tiếp nhận.
4. Hệ thống kiểm tra quyền thực hiện.
5. Nếu hợp lệ:
   - Cập nhật nơi/người tiếp nhận Ticket.
   - Ticket tiếp tục được xử lý dưới đối tượng mới.
6. Hệ thống ghi nhận thao tác vào lịch sử Ticket.

### Output

- Ticket được chuyển đến đối tượng xử lý mới.
- Thông tin nơi/người xử lý hiện tại được cập nhật.
- Lịch sử Ticket ghi nhận việc chuyển.

### Acceptance Criteria

**AC1 – Chuyển tiếp Ticket**

- Given: Staff có quyền thao tác trên Ticket.
- When: Staff thực hiện Transfer tới đối tượng hợp lệ.
- Then: Ticket được chuyển tới đối tượng đó.

**AC2 – Chuyển cấp Ticket**

- Given: Staff có quyền thao tác trên Ticket.
- When: Staff thực hiện Escalation.
- Then: Ticket được chuyển tới cấp xử lý phù hợp.

**AC3 – Không tạo Ticket mới**

- Given: Ticket được Transfer hoặc Escalate.
- Then: Hệ thống tiếp tục sử dụng Ticket hiện tại, không tạo Ticket mới.

**AC4 – Lưu lịch sử**

- Given: Transfer/Escalation thành công.
- Then: Thao tác được ghi nhận trong Ticket History.

---

## FR-STF-05 – Cập nhật trạng thái Ticket

### User Story

Là **Cán bộ xử lý**, tôi muốn cập nhật trạng thái Ticket để phản ánh đúng tiến trình xử lý hiện tại của yêu cầu.

### Input

- Ticket.
- Trạng thái mới.

Các trạng thái thuộc phạm vi Proposal:

- `Mới tạo`
- `Đang xử lý`
- `Cần bổ sung`
- `Hoàn thành`

### Processing

1. Staff mở Ticket cần xử lý.
2. Hệ thống hiển thị trạng thái hiện tại.
3. Staff chọn trạng thái mới.
4. Hệ thống kiểm tra quyền cập nhật Ticket.
5. Nếu hợp lệ:
   - Hệ thống cập nhật trạng thái mới.
   - Ghi nhận thời điểm thay đổi.
   - Ghi nhận thay đổi vào lịch sử Ticket.
6. Nếu thay đổi trạng thái được xác định là cập nhật quan trọng:
   - Hệ thống thực hiện Notification cho Student theo Module M02.

### Output

- Trạng thái Ticket mới.
- Ticket History được cập nhật.

### Acceptance Criteria

**AC1 – Update Status**

- Given: Staff có quyền xử lý Ticket.
- When: Staff chọn trạng thái hợp lệ.
- Then: Ticket được cập nhật sang trạng thái mới.

**AC2 – Status History**

- Given: Trạng thái Ticket thay đổi.
- Then: Hệ thống lưu thay đổi vào lịch sử Ticket.

**AC3 – Invalid Status**

- Given: Giá trị trạng thái không thuộc trạng thái được hệ thống hỗ trợ.
- When: Staff yêu cầu cập nhật.
- Then: Hệ thống không cập nhật Ticket.

> State Transition Matrix cụ thể giữa các trạng thái: **TBD – Pending Confirmation**.

---

## FR-STF-06 – Thiết lập / Cập nhật mức độ ưu tiên

### User Story

Là **Cán bộ xử lý**, tôi muốn thiết lập hoặc cập nhật mức độ ưu tiên của Ticket để phản ánh mức ưu tiên xử lý của yêu cầu.

### Input

- Ticket.
- Priority được chọn.

> Danh sách mức Priority cụ thể: **TBD – Pending Confirmation**.

### Processing

1. Staff mở Ticket.
2. Hệ thống hiển thị Priority hiện tại nếu đã được thiết lập.
3. Staff chọn Priority.
4. Hệ thống kiểm tra quyền cập nhật.
5. Nếu hợp lệ:
   - Lưu Priority vào Ticket.
6. Nếu Staff thay đổi Priority:
   - Hệ thống cập nhật giá trị mới.
   - Ghi nhận thay đổi nếu thuộc nhóm thao tác cần lưu History.

### Output

- Priority hiện tại của Ticket.

### Acceptance Criteria

**AC1 – Thiết lập Priority**

- Given: Ticket chưa có Priority hoặc cần được thiết lập.
- When: Staff chọn Priority hợp lệ.
- Then: Priority được lưu vào Ticket.

**AC2 – Cập nhật Priority**

- Given: Ticket đã có Priority.
- When: Staff thay đổi sang Priority khác.
- Then: Giá trị mới được lưu.

**AC3 – Priority từ cấu hình hệ thống**

- Given: Hệ thống có danh sách Priority được cấu hình.
- When: Staff chọn Priority.
- Then: Chỉ các giá trị Priority hợp lệ được sử dụng.

---

## FR-STF-07 – Yêu cầu Sinh viên bổ sung thông tin

### User Story

Là **Cán bộ xử lý**, tôi muốn yêu cầu Sinh viên bổ sung thông tin hoặc tài liệu khi Ticket chưa đủ dữ liệu để tiếp tục xử lý.

### Input

- Ticket.
- Nội dung yêu cầu bổ sung.

### Processing

1. Staff mở Ticket.
2. Staff chọn chức năng yêu cầu bổ sung thông tin.
3. Staff nhập nội dung cần Sinh viên bổ sung.
4. Hệ thống kiểm tra nội dung yêu cầu.
5. Hệ thống lưu yêu cầu vào Ticket.
6. Hệ thống thông báo cho Sinh viên.
7. Sinh viên có thể bổ sung thông tin theo chức năng tương ứng trong M02.

### Output

- Yêu cầu bổ sung được lưu trên Ticket.
- Student nhận được thông báo.

### Acceptance Criteria

**AC1 – Gửi yêu cầu bổ sung**

- Given: Staff đang xử lý Ticket.
- When: Staff nhập nội dung và gửi yêu cầu bổ sung.
- Then: Hệ thống ghi nhận yêu cầu trên đúng Ticket.

**AC2 – Notification**

- Given: Yêu cầu bổ sung được gửi thành công.
- Then: Sinh viên được thông báo.

**AC3 – Nội dung yêu cầu**

- Given: Staff chưa nhập nội dung yêu cầu bổ sung.
- When: Gửi yêu cầu.
- Then: Hệ thống không ghi nhận yêu cầu không có nội dung.

> Việc tự động chuyển Ticket sang trạng thái `Cần bổ sung`: **TBD – Pending Confirmation**.

---

## FR-STF-08 – Ghi chú nội bộ

### User Story

Là **Cán bộ xử lý**, tôi muốn thêm ghi chú nội bộ vào Ticket để lưu thông tin phục vụ quá trình xử lý mà không hiển thị nội dung đó cho Sinh viên.

### Input

- Ticket.
- Nội dung Internal Note.

### Processing

1. Staff mở Ticket.
2. Staff chọn chức năng thêm Internal Note.
3. Staff nhập nội dung ghi chú.
4. Hệ thống kiểm tra quyền.
5. Hệ thống lưu Internal Note vào Ticket.
6. Internal Note chỉ được hiển thị cho các Role có quyền truy cập nội dung nội bộ.

### Output

- Internal Note được lưu với Ticket.

### Acceptance Criteria

**AC1 – Thêm Internal Note**

- Given: Staff có quyền xử lý Ticket.
- When: Staff nhập Internal Note và lưu.
- Then: Note được liên kết với đúng Ticket.

**AC2 – Không hiển thị cho Student**

- Given: Ticket có Internal Note.
- When: Student xem Ticket.
- Then: Student không được xem Internal Note.

**AC3 – Data Authorization**

- Given: Người dùng yêu cầu xem Internal Note.
- Then: Hệ thống kiểm tra quyền trước khi cung cấp nội dung.

> Các Role được phép xem Internal Note ngoài Staff: **TBD – Pending Confirmation**.

---

## FR-STF-09 – Phản hồi chính thức cho Sinh viên

### User Story

Là **Cán bộ xử lý**, tôi muốn gửi phản hồi chính thức trên Ticket để cung cấp thông tin xử lý hoặc kết quả cho Sinh viên.

### Input

- Ticket.
- Nội dung phản hồi.

### Processing

1. Staff mở Ticket.
2. Staff chọn chức năng phản hồi.
3. Staff nhập nội dung phản hồi.
4. Hệ thống kiểm tra nội dung bắt buộc.
5. Nếu hợp lệ:
   - Lưu phản hồi vào Ticket.
   - Liên kết phản hồi với Staff gửi.
   - Ghi nhận thời điểm phản hồi.
6. Sinh viên có thể xem phản hồi trên Ticket.
7. Nếu phản hồi được xác định là cập nhật quan trọng:
   - Hệ thống thực hiện Notification theo M02.

### Output

- Official Response được lưu trên Ticket.
- Sinh viên có thể xem nội dung phản hồi.

### Acceptance Criteria

**AC1 – Gửi phản hồi**

- Given: Staff có quyền xử lý Ticket.
- When: Staff nhập nội dung hợp lệ và gửi.
- Then: Response được lưu trên Ticket.

**AC2 – Sinh viên xem phản hồi**

- Given: Response đã được gửi.
- When: Student mở Ticket.
- Then: Student có thể xem Official Response.

**AC3 – Đúng Ticket**

- Given: Staff gửi Response.
- Then: Response phải liên kết với đúng Ticket.

---

## FR-STF-10 – Sử dụng mẫu phản hồi

### User Story

Là **Cán bộ xử lý**, tôi muốn sử dụng các mẫu phản hồi có sẵn để hỗ trợ phản hồi Ticket nhanh và nhất quán hơn.

### Input

- Ticket.
- Response Template được chọn.

### Processing

1. Staff mở chức năng phản hồi trên Ticket.
2. Hệ thống cung cấp danh sách Response Template có thể sử dụng.
3. Staff chọn một Template.
4. Hệ thống đưa nội dung Template vào nội dung phản hồi.
5. Staff có thể sử dụng nội dung này để thực hiện phản hồi chính thức.
6. Việc gửi phản hồi cuối cùng được xử lý theo FR-STF-09.

### Output

- Nội dung phản hồi được tạo dựa trên Response Template.

### Acceptance Criteria

**AC1 – Hiển thị Template**

- Given: Có Response Template đã được cấu hình.
- When: Staff mở chức năng chọn Template.
- Then: Hệ thống hiển thị các Template khả dụng.

**AC2 – Sử dụng Template**

- Given: Staff chọn một Template.
- When: Template được áp dụng.
- Then: Nội dung Template được đưa vào nội dung phản hồi.

**AC3 – Quản lý Template**

- Given: Response Template được cấu hình trong Module M04.
- Then: Staff sử dụng được Template tương ứng trong Staff Desk.

> Cấu trúc Template và Placeholder cụ thể: **TBD – Pending Confirmation**.

---

## FR-STF-11 – Lịch sử thao tác và thay đổi trạng thái Ticket

### User Story

Là **Cán bộ xử lý**, tôi muốn các thao tác xử lý và thay đổi trạng thái của Ticket được lưu lại để có thể theo dõi quá trình xử lý yêu cầu.

### Input

- Ticket.
- Người thực hiện thao tác.
- Loại thao tác.
- Thông tin thay đổi.
- Thời điểm thao tác.

### Processing

1. Một thao tác xử lý Ticket được thực hiện.
2. Hệ thống xác định Ticket liên quan.
3. Hệ thống xác định người thực hiện.
4. Hệ thống xác định loại thao tác.
5. Nếu thao tác làm thay đổi trạng thái:
   - Ghi nhận trạng thái trước và trạng thái sau.
6. Hệ thống ghi nhận thời điểm thao tác.
7. Thông tin được lưu vào Ticket History.
8. Khi người dùng có quyền xem History:
   - Hệ thống trả về các thông tin được phép hiển thị.

### Output

Ticket History có khả năng thể hiện tối thiểu:

- Ticket liên quan.
- Người thực hiện.
- Loại thao tác.
- Thời điểm thao tác.
- Thay đổi trạng thái nếu có.

### Acceptance Criteria

**AC1 – Lưu thao tác xử lý**

- Given: Một thao tác được xác định cần lưu History.
- When: Thao tác hoàn tất.
- Then: Hệ thống ghi nhận thao tác vào Ticket History.

**AC2 – Lưu thay đổi trạng thái**

- Given: Status của Ticket thay đổi.
- When: Hệ thống cập nhật Status.
- Then: Thay đổi được lưu trong Ticket History.

**AC3 – Liên kết Ticket**

- Given: Một History Record được tạo.
- Then: Record phải liên kết với đúng Ticket.

**AC4 – Actor**

- Given: Một thao tác được ghi nhận.
- Then: History phải xác định được người thực hiện.

**AC5 – Timestamp**

- Given: Một thao tác được ghi nhận.
- Then: History phải xác định được thời điểm xảy ra.

> Danh sách đầy đủ các Action cần lưu Ticket History: **TBD – Pending Confirmation**.


