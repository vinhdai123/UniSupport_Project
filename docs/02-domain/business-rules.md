# Business Rules – UniSupport

## 1. Tổng quan (Overview)

Tài liệu mô tả các quy tắc nghiệp vụ áp dụng cho quá trình tạo, xử lý, theo dõi và quản lý Ticket trong hệ thống UniSupport.

Các quy tắc nhằm đảm bảo:

- Ticket được định danh và quản lý nhất quán.
- Tệp đính kèm tuân thủ các giới hạn cho phép.
- Thời hạn xử lý được xác định theo mức độ ưu tiên.
- Ticket sắp quá hạn hoặc quá hạn được nhận diện.
- Việc mở lại Ticket tuân thủ thời gian quy định.

Các thông số nghiệp vụ cụ thể trong tài liệu cần được Aurora University xác nhận trước khi đưa vào Requirement Baseline.

## 2. Danh sách quy tắc nghiệp vụ (Business Rules)

### BR-01 – Định danh Ticket (Ticket Identification)

**Mô tả**

Mỗi Ticket được tạo thành công phải có một mã định danh duy nhất để phục vụ việc tra cứu, theo dõi và quản lý.

**Quy tắc**

- Mỗi Ticket chỉ có một Ticket ID.
- Ticket ID không được trùng lặp trong toàn hệ thống.
- Ticket ID được cấp khi Ticket được tạo thành công.
- Ticket ID không thay đổi trong suốt vòng đời Ticket.

**Định dạng chuẩn:**

`AU-YYYY-XXXX`

Trong đó:
- `AU`: Mã định danh Aurora University.
- `YYYY`: Năm tạo Ticket.
- `XXXX`: Số thứ tự tăng dần, bắt đầu từ `0001` cho mỗi năm.
**Ví dụ:** `AU-2026-0001`

---

### BR-02 – Quy định tệp đính kèm (Attachment Rules)

**Mô tả**

Sinh viên có thể đính kèm tài liệu hoặc hình ảnh khi tạo Ticket hoặc bổ sung thông tin.

**Quy tắc**

| Thuộc tính | Giá trị quy định |
|---|---|
| Số lượng tối đa | 03 tệp mỗi lần gửi hoặc bổ sung |
| Dung lượng tối đa | 5 MB/tệp |
| Định dạng cho phép | `.pdf`, `.jpg`, `.jpeg`, `.png` |

**Điều kiện nghiệp vụ**

- Không chấp nhận tệp vượt quá dung lượng quy định.
- Không chấp nhận định dạng nằm ngoài danh sách cho phép.
- Không cho phép tải lên tệp thực thi (VD: `.bat`, `.exe`) hoặc tệp có nội dung nguy hiểm.
- Người dùng chỉ được truy cập tệp đính kèm thuộc Ticket mà họ có quyền truy cập.
- Khi tệp không hợp lệ, hệ thống hiển thị thông báo chặn ngay trên giao diện.

---

### BR-03 – Ma trận thời hạn xử lý (SLA Matrix)

**Mô tả**

Mỗi Ticket được xác định thời hạn xử lý dựa trên mức độ ưu tiên (Priority).

**Ma trận SLA chuẩn**

| Priority | Mức độ | Thời hạn xử lý |
|---|---|---|
| Urgent | Khẩn cấp | 04 giờ làm việc |
| High | Cao | 12 giờ làm việc |
| Medium | Trung bình | 24 giờ làm việc |
| Low | Thấp | 48 giờ làm việc |

**Quy tắc**

- Ticket mới được gán mức ưu tiên mặc định là `Medium`.
- Thời gian SLA được tính theo giờ làm việc hành chính của Aurora University.
- Chỉ Manager hoặc Admin mới có quyền thay đổi mức độ ưu tiên của Ticket.
- Thời gian SLA sẽ **tạm dừng (Pause)** khi Ticket chuyển sang trạng thái `Cần bổ sung` (chờ sinh viên cung cấp thông tin) và tiếp tục đếm khi sinh viên phản hồi.

---

### BR-04 – Cảnh báo thời hạn xử lý (SLA Alerts)

**Mô tả**

Hệ thống nhận diện các Ticket sắp đến hạn hoặc đã quá hạn để hỗ trợ cán bộ và quản lý giám sát tiến độ.

**Quy tắc cảnh báo**

| Trạng thái | Điều kiện |
|---|---|
| Bình thường | Thời gian SLA còn lại trên 25% tổng thời gian SLA áp dụng |
| Cảnh báo vàng | Thời gian SLA còn lại từ 0% đến 25% tổng thời gian SLA áp dụng |
| Cảnh báo đỏ | Ticket đã vượt quá thời hạn xử lý |

**Điều kiện nghiệp vụ**

- Cảnh báo vàng/đỏ được hệ thống tự động gửi qua Email và thông báo In-app cho cán bộ phụ trách và Manager.
- Các cảnh báo áp dụng đối với Ticket chưa hoàn thành.
- Ticket đã hoàn thành không tiếp tục phát sinh cảnh báo quá hạn.

---

### BR-05 – Quy tắc mở lại & Đóng Ticket (Ticket Reopen & Close Window)

**Mô tả**

Sinh viên được phép mở lại Ticket đã hoàn thành trong khoảng thời gian quy định nếu vấn đề chưa được giải quyết thỏa đáng.

**Quy tắc**

- Chỉ Ticket ở trạng thái `Hoàn thành (Resolved)` mới đủ điều kiện mở lại.
- Sinh viên có quyền truy cập Ticket được phép yêu cầu mở lại thông qua nút "Mở lại".
- Thời gian cho phép mở lại là **72 giờ (tính theo thời gian thực liên tục)** kể từ thời điểm Ticket được chuyển sang `Hoàn thành`.
- Sau khi được sinh viên Mở lại, Ticket chuyển về trạng thái `Đang xử lý (In Progress)` và SLA được thiết lập lại từ đầu dựa trên mức độ ưu tiên hiện tại.

**Quy tắc Đóng Ticket (Closed)**
- Sau đúng 72 giờ kể từ thời điểm hoàn thành mà sinh viên không có thao tác mở lại, Ticket tự động chuyển sang trạng thái `Đóng (Closed)`.
- Ticket đã `Đóng` là trạng thái kết thúc vĩnh viễn, không cho phép mở lại hay trao đổi thêm. Sinh viên muốn hỗ trợ tiếp phải tạo Ticket mới.

## 3. Nguyên tắc áp dụng (Rule Enforcement)

- Các Business Rules được áp dụng thống nhất cho những chức năng liên quan.
- Người dùng chỉ được thực hiện các thao tác phù hợp với quyền hạn đã được cấp.
- Các thay đổi quan trọng đối với Ticket phải được ghi nhận trong lịch sử xử lý.
- Các quy tắc cần được xác nhận trước khi trở thành tiêu chí nghiệm thu chính thức.
- Mọi thay đổi sau khi khóa phạm vi phải tuân theo quy trình Change Request nếu ảnh hưởng đến phạm vi, chi phí hoặc tiến độ.

## 4. Quan hệ với tài liệu khác (Related Documents)

- `ticket-lifecycle.md`: Vòng đời và chuyển đổi trạng thái Ticket.
- `ticket-routing.md`: Phân luồng, phân công và chuyển cấp Ticket.
- `sla-management.md`: Quản lý thời hạn xử lý.
- `../01-product/product-scope.md`: Phạm vi sản phẩm.
- `../03-modules/`: Yêu cầu chức năng của từng module.