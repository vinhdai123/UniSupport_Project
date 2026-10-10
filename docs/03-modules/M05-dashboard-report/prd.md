# MODULE M05: DASHBOARD & REPORT

# 1. Functional Requirements

## FR-RPT-01 – Thống kê Ticket theo trạng thái

### User Story

Là **Quản lý**, tôi muốn xem số lượng Ticket theo từng trạng thái để nắm được tình hình xử lý yêu cầu hiện tại trong phạm vi mình được phép quản lý.

### Input

- Phạm vi dữ liệu người dùng được phép xem.
- Khoảng thời gian báo cáo (nếu áp dụng).
- Trạng thái Ticket.

Các trạng thái trong phạm vi hiện tại:

- `Mới tạo`
- `Đang xử lý`
- `Cần bổ sung`
- `Hoàn thành`

### Processing

1. Manager truy cập Dashboard.
2. Hệ thống xác định người dùng hiện tại.
3. Hệ thống xác định phạm vi dữ liệu Manager được phép truy cập.
4. Hệ thống lấy các Ticket thuộc phạm vi đó.
5. Nếu có Time Filter, hệ thống chỉ lấy Ticket phù hợp với khoảng thời gian đã chọn.
6. Hệ thống nhóm Ticket theo trạng thái.
7. Hệ thống đếm số lượng Ticket trong từng nhóm.
8. Hệ thống hiển thị kết quả trên Dashboard.

### Output

Số lượng Ticket theo từng trạng thái:

- Mới tạo.
- Đang xử lý.
- Cần bổ sung.
- Hoàn thành.

### Acceptance Criteria

**AC1 – Hiển thị Ticket theo trạng thái**

- Given: Manager có quyền truy cập Dashboard.
- When: Manager mở Dashboard.
- Then: Hệ thống hiển thị số lượng Ticket theo từng trạng thái.

**AC2 – Đúng phạm vi dữ liệu**

- Given: Manager chỉ được phép xem một phạm vi dữ liệu nhất định.
- When: Dashboard tải dữ liệu.
- Then: Chỉ các Ticket thuộc phạm vi được cấp quyền mới được thống kê.

**AC3 – Đúng trạng thái**

- Given: Ticket thuộc một trong các trạng thái của hệ thống.
- When: Hệ thống thực hiện thống kê.
- Then: Ticket phải được tính vào đúng nhóm trạng thái tương ứng.

**AC4 – Time Filter**

- Given: Manager chọn một khoảng thời gian.
- When: Bộ lọc được áp dụng.
- Then: Các số liệu trên Dashboard phải được cập nhật theo khoảng thời gian đó.

> Quy tắc Time Filter cụ thể: **TBD – Pending Confirmation**.

---

## FR-RPT-02 – Theo dõi tỷ lệ hoàn thành

### User Story

Là **Quản lý**, tôi muốn theo dõi tỷ lệ Ticket đã hoàn thành để đánh giá mức độ hoàn tất các yêu cầu hỗ trợ trong phạm vi quản lý.

### Input

- Phạm vi dữ liệu báo cáo.
- Khoảng thời gian báo cáo (nếu áp dụng).
- Trạng thái Ticket.

### Processing

1. Hệ thống lấy các Ticket thuộc phạm vi báo cáo.
2. Nếu có Time Filter, hệ thống áp dụng bộ lọc tương ứng.
3. Hệ thống xác định số lượng Ticket có trạng thái `Hoàn thành`.
4. Hệ thống xác định tổng số Ticket thuộc phạm vi tính toán.
5. Hệ thống tính Completion Rate theo công thức đã được phê duyệt.
6. Hệ thống hiển thị số lượng Ticket hoàn thành và tỷ lệ hoàn thành.

### Output

- Số lượng Ticket hoàn thành.
- Tỷ lệ Ticket hoàn thành.

> Công thức Completion Rate chính thức: **TBD – Pending Confirmation**.

### Acceptance Criteria

**AC1 – Hiển thị số Ticket hoàn thành**

- Given: Dashboard có dữ liệu Ticket.
- When: Manager xem Completion Metric.
- Then: Hệ thống hiển thị số lượng Ticket hoàn thành.

**AC2 – Hiển thị Completion Rate**

- Given: Có dữ liệu hợp lệ trong phạm vi báo cáo.
- When: Hệ thống tính Completion Rate.
- Then: Dashboard hiển thị tỷ lệ hoàn thành.

**AC3 – Data Scope**

- Given: Manager có phạm vi dữ liệu được cấp quyền.
- When: Completion Rate được tính.
- Then: Chỉ Ticket thuộc phạm vi đó được sử dụng.

**AC4 – Đồng bộ với Filter**

- Given: Manager thay đổi Time Filter.
- When: Dashboard cập nhật.
- Then: Completion Rate được tính lại theo dữ liệu mới.

---

## FR-RPT-03 – Theo dõi Ticket tồn đọng

### User Story

Là **Quản lý**, tôi muốn biết số lượng Ticket đang tồn đọng để theo dõi khối lượng yêu cầu chưa được hoàn tất và có biện pháp điều phối phù hợp.

### Input

- Phạm vi dữ liệu báo cáo.
- Khoảng thời gian báo cáo (nếu áp dụng).
- Dữ liệu trạng thái Ticket.

### Processing

1. Hệ thống lấy các Ticket thuộc phạm vi Manager được phép xem.
2. Hệ thống áp dụng Time Filter nếu có.
3. Hệ thống xác định Ticket thuộc nhóm Backlog theo quy tắc đã được phê duyệt.
4. Hệ thống tổng hợp số lượng Ticket tồn đọng.
5. Hệ thống hiển thị kết quả trên Dashboard.

### Output

- Số lượng Ticket tồn đọng.
- Dữ liệu Backlog thuộc phạm vi báo cáo.

### Acceptance Criteria

**AC1 – Hiển thị Backlog**

- Given: Có Ticket tồn đọng trong phạm vi quản lý.
- When: Manager mở Dashboard.
- Then: Hệ thống hiển thị số lượng Backlog.

**AC2 – Backlog khác Completed**

- Given: Một Ticket đã được xác định là `Hoàn thành`.
- When: Hệ thống tính Backlog.
- Then: Ticket đó không được tính là Ticket tồn đọng theo định nghĩa được phê duyệt.

**AC3 – Backlog khác Overdue**

- Given: Hệ thống có dữ liệu về Ticket tồn đọng và Ticket quá hạn.
- When: Dashboard hiển thị Backlog.
- Then: Không được mặc định coi mọi Ticket tồn đọng là Ticket quá hạn.

**AC4 – Data Scope**

- Given: Manager có phạm vi dữ liệu giới hạn.
- Then: Backlog chỉ được tính từ Ticket thuộc phạm vi đó.

> Quy tắc chi tiết xác định `Backlog`: **TBD – Pending Confirmation**.

---

## FR-RPT-04 – Theo dõi thời gian xử lý trung bình

### User Story

Là **Quản lý**, tôi muốn xem thời gian xử lý Ticket trung bình để đánh giá tốc độ xử lý các yêu cầu hỗ trợ.

### Input

- Phạm vi dữ liệu báo cáo.
- Khoảng thời gian báo cáo (nếu áp dụng).
- Dữ liệu thời gian xử lý Ticket.

### Processing

1. Hệ thống lấy các Ticket thuộc phạm vi báo cáo.
2. Hệ thống áp dụng Time Filter nếu có.
3. Hệ thống lấy dữ liệu thời gian xử lý của các Ticket đủ điều kiện.
4. Hệ thống tính thời gian xử lý trung bình theo công thức đã được xác nhận.
5. Hệ thống hiển thị kết quả trên Dashboard.

### Output

- Average Processing Time.

### Acceptance Criteria

**AC1 – Hiển thị Average Processing Time**

- Given: Có dữ liệu Ticket hợp lệ.
- When: Dashboard tải metric.
- Then: Hệ thống hiển thị thời gian xử lý trung bình.

**AC2 – Đúng phạm vi dữ liệu**

- Given: Manager có Data Scope cụ thể.
- When: Average Processing Time được tính.
- Then: Chỉ Ticket trong Data Scope được sử dụng.

**AC3 – Time Filter**

- Given: Manager thay đổi khoảng thời gian báo cáo.
- When: Dashboard cập nhật.
- Then: Average Processing Time được tính lại theo dữ liệu phù hợp.

> Công thức tính, thời điểm bắt đầu/kết thúc và quy tắc tạm dừng thời gian xử lý: **TBD – Pending Confirmation**.

---

## FR-RPT-05 – Theo dõi hiệu suất theo phòng ban/cán bộ

### User Story

Là **Quản lý**, tôi muốn xem hiệu suất xử lý theo phòng ban và cán bộ để theo dõi hoạt động hỗ trợ và tình hình xử lý Ticket của từng đơn vị hoặc cá nhân.

### Input

- Department.
- Staff.
- Khoảng thời gian báo cáo (nếu áp dụng).
- Phạm vi dữ liệu Manager được phép xem.

### Processing

1. Manager truy cập chức năng theo dõi Performance.
2. Hệ thống xác định Data Scope của Manager.
3. Manager có thể chọn Department.
4. Manager có thể chọn Staff.
5. Manager có thể chọn khoảng thời gian báo cáo.
6. Hệ thống lấy các Ticket phù hợp.
7. Hệ thống tổng hợp dữ liệu theo Department hoặc Staff.
8. Hệ thống tính các Performance Metric đã được phê duyệt.
9. Hệ thống hiển thị kết quả.

### Output

Thông tin hiệu suất theo:

- Department.
- Staff.

### Acceptance Criteria

**AC1 – Performance theo Department**

- Given: Manager chọn một Department.
- When: Hệ thống tổng hợp dữ liệu.
- Then: Dashboard hiển thị Performance của Department tương ứng.

**AC2 – Performance theo Staff**

- Given: Manager chọn một Staff.
- When: Hệ thống tổng hợp dữ liệu.
- Then: Dashboard hiển thị Performance của Staff tương ứng.

**AC3 – Data Scope**

- Given: Manager không có quyền xem một Department hoặc Staff.
- When: Dashboard tải dữ liệu.
- Then: Dữ liệu ngoài phạm vi không được hiển thị.

**AC4 – Time Filter**

- Given: Manager chọn khoảng thời gian.
- When: Filter được áp dụng.
- Then: Performance được tính dựa trên dữ liệu trong khoảng thời gian đó.

> Các chỉ số cụ thể dùng để đánh giá `Performance`: **TBD – Pending Confirmation**.

---

## FR-RPT-06 – Thống kê nhóm vấn đề phổ biến

### User Story

Là **Quản lý**, tôi muốn xem các nhóm vấn đề phổ biến để xác định những loại yêu cầu hỗ trợ thường xuyên phát sinh từ Sinh viên.

### Input

- Phạm vi dữ liệu báo cáo.
- Khoảng thời gian báo cáo (nếu áp dụng).
- Dữ liệu Category hoặc nhóm vấn đề của Ticket.

### Processing

1. Hệ thống lấy Ticket thuộc phạm vi báo cáo.
2. Hệ thống áp dụng Time Filter nếu có.
3. Hệ thống nhóm Ticket theo tiêu chí phân loại được xác định.
4. Hệ thống tính số lượng Ticket của từng nhóm.
5. Hệ thống sắp xếp hoặc trình bày dữ liệu để Manager nhận biết nhóm phổ biến.
6. Hệ thống hiển thị kết quả.

### Output

- Danh sách nhóm vấn đề phổ biến.
- Số lượng Ticket tương ứng với từng nhóm.

### Acceptance Criteria

**AC1 – Hiển thị nhóm vấn đề**

- Given: Có dữ liệu Ticket trong hệ thống.
- When: Manager mở báo cáo Common Issues.
- Then: Hệ thống hiển thị các nhóm vấn đề được tổng hợp.

**AC2 – Ticket Count**

- Given: Một nhóm vấn đề có nhiều Ticket.
- When: Báo cáo được tạo.
- Then: Hệ thống hiển thị số lượng Ticket tương ứng với nhóm đó.

**AC3 – Data Scope**

- Given: Manager có phạm vi dữ liệu giới hạn.
- Then: Báo cáo chỉ tổng hợp Ticket trong phạm vi đó.

**AC4 – Time Filter**

- Given: Manager chọn khoảng thời gian.
- Then: Báo cáo Common Issues được cập nhật theo khoảng thời gian.

> Tiêu chí xác định "nhóm vấn đề" là Category hay một cơ chế phân nhóm khác: **TBD – Pending Confirmation**.

---

## FR-RPT-07 – Phân tích xu hướng Ticket theo thời gian

### User Story

Là **Quản lý**, tôi muốn theo dõi xu hướng số lượng Ticket theo thời gian để nhận biết sự thay đổi về nhu cầu hỗ trợ của Sinh viên.

### Input

- Khoảng thời gian báo cáo.
- Phạm vi dữ liệu báo cáo.
- Dữ liệu thời điểm tạo Ticket.

### Processing

1. Manager chọn khoảng thời gian cần phân tích.
2. Hệ thống xác định Data Scope.
3. Hệ thống lấy các Ticket phù hợp.
4. Hệ thống nhóm Ticket theo đơn vị thời gian được áp dụng.
5. Hệ thống tính số lượng Ticket tại từng mốc thời gian.
6. Hệ thống hiển thị dữ liệu xu hướng.

### Output

- Dữ liệu xu hướng số lượng Ticket theo thời gian.

### Acceptance Criteria

**AC1 – Hiển thị Trend**

- Given: Có Ticket trong khoảng thời gian báo cáo.
- When: Manager mở Trend Report.
- Then: Hệ thống hiển thị sự thay đổi số lượng Ticket theo thời gian.

**AC2 – Time Range**

- Given: Manager chọn một khoảng thời gian khác.
- When: Filter được áp dụng.
- Then: Trend được cập nhật theo khoảng thời gian mới.

**AC3 – Data Scope**

- Given: Manager có phạm vi dữ liệu được cấp.
- Then: Trend chỉ sử dụng Ticket thuộc phạm vi đó.

> Đơn vị tổng hợp thời gian như ngày/tuần/tháng: **TBD – Pending Confirmation**.

---

## FR-RPT-08 – Báo cáo mức độ hài lòng của Sinh viên

### User Story

Là **Quản lý**, tôi muốn xem kết quả đánh giá mức độ hài lòng của Sinh viên để theo dõi chất lượng hỗ trợ sau khi Ticket được hoàn thành.

### Input

- Satisfaction Rating từ Ticket.
- Phạm vi dữ liệu báo cáo.
- Khoảng thời gian báo cáo (nếu áp dụng).

### Processing

1. Hệ thống lấy các Rating được Sinh viên gửi sau khi Ticket hoàn thành.
2. Hệ thống xác định các Rating thuộc phạm vi báo cáo.
3. Hệ thống áp dụng Time Filter nếu có.
4. Hệ thống tổng hợp dữ liệu đánh giá.
5. Hệ thống tính các chỉ số Satisfaction theo phương pháp đã được phê duyệt.
6. Hệ thống hiển thị kết quả.

### Output

- Thông tin về mức độ hài lòng của Sinh viên.
- Dữ liệu tổng hợp từ các Satisfaction Rating đã ghi nhận.

### Acceptance Criteria

**AC1 – Tổng hợp Satisfaction Data**

- Given: Có Ticket đã nhận Satisfaction Rating.
- When: Manager mở Satisfaction Report.
- Then: Hệ thống tổng hợp các Rating phù hợp.

**AC2 – Hiển thị kết quả**

- Given: Có dữ liệu đánh giá hợp lệ.
- Then: Báo cáo hiển thị thông tin mức độ hài lòng.

**AC3 – Không có Rating**

- Given: Ticket chưa nhận Rating.
- Then: Ticket không được xem là đã có dữ liệu Satisfaction.

**AC4 – Data Scope**

- Given: Manager có Data Scope.
- Then: Chỉ Rating của Ticket thuộc phạm vi đó được sử dụng.

> Rating Scale và công thức tổng hợp Satisfaction: **TBD – Pending Confirmation**.

---

## FR-RPT-09 – Xuất báo cáo CSV

### User Story

Là **Quản lý**, tôi muốn xuất dữ liệu báo cáo dưới định dạng CSV để phục vụ phân tích, lưu trữ hoặc xử lý dữ liệu bên ngoài UniSupport.

### Input

- Loại báo cáo cần xuất.
- Phạm vi dữ liệu được phép truy cập.
- Điều kiện Filter đang được áp dụng.
- Khoảng thời gian báo cáo nếu có.

### Processing

1. Manager mở Dashboard hoặc Report cần xuất.
2. Manager áp dụng các điều kiện Filter nếu cần.
3. Manager chọn chức năng `Export CSV`.
4. Hệ thống xác định loại báo cáo.
5. Hệ thống xác định Data Scope của Manager.
6. Hệ thống lấy dữ liệu tương ứng với Report và Filter.
7. Hệ thống tạo file CSV.
8. File CSV được cung cấp cho Manager.

### Output

- File báo cáo định dạng `.csv`.

### Acceptance Criteria

**AC1 – Export CSV**

- Given: Manager đang xem một Report hỗ trợ Export.
- When: Manager chọn Export CSV.
- Then: Hệ thống tạo file CSV.

**AC2 – Đúng loại báo cáo**

- Given: Manager đang xem một Report cụ thể.
- When: Export được thực hiện.
- Then: CSV phải chứa dữ liệu tương ứng với Report đó.

**AC3 – Đúng Filter**

- Given: Manager đã áp dụng Filter.
- When: Export CSV.
- Then: File CSV phản ánh dữ liệu sau khi Filter được áp dụng.

**AC4 – Data Authorization**

- Given: Manager chỉ được truy cập một phạm vi dữ liệu nhất định.
- When: Export CSV.
- Then: File CSV không được chứa dữ liệu ngoài phạm vi quyền.

**AC5 – File hợp lệ**

- Given: Export hoàn tất thành công.
- Then: Hệ thống cung cấp file có định dạng CSV có thể sử dụng để xử lý dữ liệu bên ngoài.

> Tên file, encoding, danh sách Column và cấu trúc CSV cụ thể: **TBD – Pending Confirmation**.

