# MODULE M05: DASHBOARD & REPORT (BÁO CÁO THỐNG KÊ)

Bản đặc tả phục vụ kế hoạch Mô phỏng. Tham số mật khẩu, thời hạn, tệp, số dòng và chính sách quyền theo Business Rules/NFR là đề xuất cần PM/BA xác nhận trước baseline nghiệm thu.


# 1. Đặc tả yêu cầu chức năng

## FR-RPT-01 – Bảng điều khiển Tổng quan (Overview Metrics)

### Mô tả
Cung cấp cho Quản lý (Manager/Admin) cái nhìn toàn cảnh về tình hình xử lý Ticket thông qua các chỉ số cốt lõi (KPIs): Số lượng Ticket theo trạng thái, Tỷ lệ hoàn thành, Ticket tồn đọng (Backlog) và Thời gian xử lý trung bình (SLA).

### Actor
Quản lý (Manager), Quản trị viên (Admin).

### Mức độ ưu tiên
Cao.

### Điều kiện tiên quyết
Tài khoản có quyền xem báo cáo và hệ thống có dữ liệu Ticket.

### Luồng chính
1. Người dùng truy cập menu Bảng điều khiển.
2. Hệ thống xác định quyền hạn (Data Scope) của người dùng để quyết định phạm vi dữ liệu được phép tải.
3. Người dùng chọn khoảng thời gian cần xem.
4. Hệ thống tính toán và hiển thị 4 nhóm chỉ số chính:
   - Tổng số Ticket theo trạng thái (Mới tạo, Đang xử lý, Cần bổ sung, Hoàn thành).
   - Tỷ lệ hoàn thành (Số Ticket hoàn thành / Tổng số Ticket x 100%).
   - Số lượng tồn đọng (Backlog).
   - Thời gian xử lý trung bình.

### Quy tắc nghiệp vụ
- BR-RPT-01: Quản trị viên xem được dữ liệu toàn hệ thống. Quản lý chỉ xem được dữ liệu thuộc Phòng ban mình phụ trách.
- BR-RPT-02: Ticket được tính là "Tồn đọng" nếu trạng thái không phải là "Hoàn thành" VÀ đã vượt quá thời hạn xử lý quy định nhưng chưa được giải quyết dứt điểm.
- BR-RPT-03: Thời gian xử lý trung bình chỉ tính trên các Ticket đã "Hoàn thành", đồng thời phải trừ đi khoảng thời gian Ticket nằm ở trạng thái "Cần bổ sung" (chờ sinh viên phản hồi).

### Luồng rẽ nhánh và lỗi
- E-RPT-01: Nếu người dùng chọn mốc thời gian không hợp lệ (ví dụ: ngày bắt đầu lớn hơn ngày kết thúc), hệ thống chặn lại và báo "Khoảng thời gian không hợp lệ".
- E-RPT-02: Nếu trong khoảng thời gian được chọn không có bất kỳ Ticket nào, các biểu đồ và chỉ số sẽ hiển thị số "0" hoặc trạng thái "Chưa có dữ liệu", hệ thống không được báo lỗi.

### Tiêu chí nghiệm thu
- **FR-RPT-01/AC-01:** Hiển thị đúng dữ liệu theo phân quyền (Kiểm tra BR-RPT-01)
  - Given: Quản lý phòng Đào tạo đăng nhập.
  - When: Truy cập Bảng điều khiển Tổng quan.
  - Then: Các con số chỉ thống kê dựa trên các Ticket thuộc danh mục của phòng Đào tạo.
- **FR-RPT-01/AC-02:** Xử lý điều kiện thời gian sai (Kiểm tra E-RPT-01)
  - Given: Người dùng đang ở màn hình Bảng điều khiển.
  - When: Chọn ngày bắt đầu là 20/10/2026 và ngày kết thúc là 15/10/2026.
  - Then: Hệ thống báo lỗi "Khoảng thời gian không hợp lệ" và giữ nguyên dữ liệu của bộ lọc trước đó.
- **FR-RPT-01/AC-03:** Loại trừ thời gian chờ sinh viên (Kiểm tra BR-RPT-03)
  - Given: Một yêu cầu mất tổng cộng 5 ngày để đóng, trong đó có 3 ngày nằm ở trạng thái chờ sinh viên bổ sung giấy tờ.
  - When: Hệ thống tính toán thời gian xử lý trung bình.
  - Then: Yêu cầu này chỉ được ghi nhận có thời gian xử lý thực tế là 2 ngày.

- **FR-RPT-01/AC-04:** Phân biệt tồn đọng và chưa quá hạn (BR-RPT-02)
  - Given: Có một Ticket chưa hoàn thành đã quá hạn, một chưa hoàn thành còn hạn và một hoàn thành.
  - When: Mở thống kê Tồn đọng.
  - Then: Chỉ Ticket chưa hoàn thành đã quá hạn được tính theo định nghĩa BR-RPT-02.
- **FR-RPT-01/AC-05:** Khoảng thời gian không có Ticket (E-RPT-02)
  - Given: Khoảng thời gian hợp lệ không có Ticket thuộc quyền xem.
  - When: Áp dụng bộ lọc và tải báo cáo.
  - Then: Chỉ số hiển thị 0 hoặc Chưa có dữ liệu, không chia cho 0 hoặc báo lỗi.

### Tình huống ngoại lệ
- Bộ lọc hợp lệ không có Ticket, kiểm không chia cho 0 và không giữ số liệu của bộ lọc cũ.

---

## FR-RPT-02 – Báo cáo Hiệu suất Nhân sự (Performance Report)

### Mô tả
Hỗ trợ đo lường và theo dõi khối lượng công việc, tốc độ xử lý của từng Phòng ban và từng Cán bộ cụ thể nhằm đánh giá hiệu suất nhân sự.

### Actor
Quản lý, Quản trị viên.

### Mức độ ưu tiên
Cao.

### Điều kiện tiên quyết
Tài khoản có quyền xem báo cáo cấp phòng ban.

### Luồng chính
1. Người dùng chuyển sang tab Báo cáo Hiệu suất.
2. Hệ thống hiển thị bảng xếp hạng theo Phòng ban (dành cho Admin) hoặc theo Cán bộ (dành cho Manager của một phòng).
3. Người dùng chọn một Cán bộ cụ thể để xem chi tiết.
4. Hệ thống hiển thị: Số Ticket cán bộ đang giữ, số Ticket đã hoàn thành trong kỳ, số Ticket quá hạn.

### Quy tắc nghiệp vụ
- BR-RPT-04: Quản lý của phòng ban A tuyệt đối không được phép xem hoặc truy cập vào dữ liệu hiệu suất của nhân sự thuộc phòng ban B.

### Luồng rẽ nhánh và lỗi
- E-RPT-03: Nếu một cán bộ mới được thêm vào hệ thống và chưa từng xử lý yêu cầu nào, hệ thống vẫn hiển thị tên cán bộ trong danh sách nhân sự với các chỉ số hiệu suất bằng 0.

### Tiêu chí nghiệm thu
- **FR-RPT-02/AC-01:** Xem hiệu suất theo cán bộ
  - Given: Quản lý phòng Công nghệ thông tin mở báo cáo hiệu suất.
  - When: Chọn nhân viên "Nguyễn Văn A".
  - Then: Hệ thống hiển thị chi tiết số Ticket nhân viên A đã xử lý và so sánh thời gian trung bình của nhân viên này với toàn phòng.
- **FR-RPT-02/AC-02:** Chặn truy cập chéo phòng ban (Kiểm tra BR-RPT-04)
  - Given: Quản lý phòng Công nghệ thông tin đang dùng hệ thống.
  - When: Thử tìm kiếm hoặc truy cập dữ liệu của phòng Kế toán.
  - Then: Hệ thống không hiển thị bất kỳ thông tin nhân sự nào của phòng Kế toán.

- **FR-RPT-02/AC-03:** Cán bộ chưa xử lý Ticket (E-RPT-03)
  - Given: Phòng có Staff mới chưa xử lý Ticket.
  - When: Manager mở báo cáo hiệu suất phòng.
  - Then: Staff mới vẫn xuất hiện, số lượng xử lý bằng 0, chỉ số thiếu mẫu được trình bày rõ.

### Tình huống ngoại lệ
- Staff mới có 0 Ticket, kiểm vẫn hiển thị cùng phạm vi quyền phòng ban.

---

## FR-RPT-03 – Phân tích Xu hướng & Vấn đề (Trend & Category Analysis)

### Mô tả
Hiển thị biểu đồ biểu diễn xu hướng gửi yêu cầu hỗ trợ theo thời gian và thống kê các nhóm vấn đề phổ biến nhất để nhà trường có kế hoạch phân bổ nguồn lực hợp lý.

### Actor
Quản lý, Quản trị viên.

### Mức độ ưu tiên
Trung bình.

### Điều kiện tiên quyết
Hệ thống có dữ liệu Ticket.

### Luồng chính
1. Người dùng mở tab Phân tích xu hướng.
2. Hệ thống vẽ biểu đồ đường thể hiện số lượng Ticket tạo mới chia theo thời gian dựa trên bộ lọc.
3. Hệ thống vẽ biểu đồ tròn thể hiện top các danh mục có lượng Ticket cao nhất.
4. Người dùng có thể di chuột vào các điểm trên biểu đồ để xem con số chi tiết.

### Quy tắc nghiệp vụ
- BR-RPT-05: Khi người dùng chọn dải thời gian lớn hơn 30 ngày, trục thời gian của biểu đồ xu hướng sẽ tự động nhóm theo Tuần hoặc Tháng để tránh quá tải giao diện hiển thị.

### Luồng rẽ nhánh và lỗi
- E-RPT-04: Để tránh truy vấn dữ liệu quá lớn gây treo hệ thống, nếu bộ lọc thời gian lớn hơn 365 ngày (1 năm), hệ thống chặn truy vấn và yêu cầu thu hẹp phạm vi.

### Tiêu chí nghiệm thu
- **FR-RPT-03/AC-01:** Nhóm biểu đồ tự động (Kiểm tra BR-RPT-05)
  - Given: Có bộ dữ liệu đối chứng cho các khoảng thời gian 30 và 31 ngày.
  - When: Tải biểu đồ với từng khoảng.
  - Then: Khoảng 30 ngày vẫn hiển thị theo ngày. Khoảng 31 ngày tự động nhóm theo tuần hoặc tháng theo cấu hình áp dụng. Tổng số Ticket trong các nhóm khớp dữ liệu lọc.
- **FR-RPT-03/AC-02:** Chặn truy vấn quá giới hạn (Kiểm tra E-RPT-04)
  - Given: Có dữ liệu đối chứng và khoảng thời gian 365 ngày, 366 ngày, gồm trường hợp đi qua ngày 29/02.
  - When: Tải báo cáo lần lượt với từng khoảng.
  - Then: 365 ngày được xử lý và nhóm theo BR-RPT-05. 366 ngày bị từ chối, hiển thị yêu cầu thu hẹp về tối đa 365 ngày và không thay biểu đồ bằng kết quả của truy vấn bị từ chối.


### Tình huống ngoại lệ
- Kiểm dải 30/31 ngày và 365/366 ngày theo giá trị đề xuất đã xác nhận, có cả năm nhuận.

---

## FR-RPT-04 – Báo cáo Đánh giá Hài lòng (CSAT Report)

### Mô tả
Tổng hợp dữ liệu từ các lượt đánh giá bằng sao của sinh viên để đo lường mức độ hài lòng đối với dịch vụ hỗ trợ của nhà trường.

### Actor
Quản lý, Quản trị viên.

### Mức độ ưu tiên
Trung bình.

### Điều kiện tiên quyết
Đã có sinh viên gửi đánh giá cho các yêu cầu đã hoàn thành.

### Luồng chính
1. Người dùng mở báo cáo Đánh giá mức độ hài lòng.
2. Hệ thống tổng hợp Điểm trung bình (ví dụ: 4.5/5 sao).
3. Hệ thống hiển thị biểu đồ phân bổ số lượng đánh giá theo từng mức độ sao.
4. Hệ thống hiển thị danh sách các bình luận, góp ý chi tiết mà sinh viên đã để lại.

### Quy tắc nghiệp vụ
- BR-RPT-06: Chỉ các Ticket đã hoàn thành VÀ sinh viên có tham gia đánh giá mới được đưa vào công thức tính điểm trung bình. Những Ticket hoàn thành nhưng sinh viên bỏ qua đánh giá sẽ không làm giảm điểm tổng của hệ thống.

### Luồng rẽ nhánh và lỗi
- E-RPT-05: Nếu chọn xem đánh giá của một Cán bộ hoặc Danh mục chưa có bất kỳ phản hồi nào, hệ thống hiển thị trạng thái "Chưa có dữ liệu đánh giá".

### Tiêu chí nghiệm thu
- **FR-RPT-04/AC-01:** Tính điểm trung bình chuẩn xác (Kiểm tra BR-RPT-06)
  - Given: Phòng ban có 10 Ticket hoàn thành, nhưng chỉ có 4 sinh viên đánh giá (hai lượt 5 sao, hai lượt 4 sao).
  - When: Hệ thống tính toán điểm mức độ hài lòng.
  - Then: Điểm trung bình hiển thị là 4.5 sao, hoàn toàn không bị kéo tụt bởi 6 Ticket không tham gia đánh giá.

- **FR-RPT-04/AC-02:** Chưa có phản hồi hài lòng (E-RPT-05)
  - Given: Cán bộ hoặc danh mục được lọc chưa có đánh giá.
  - When: Mở báo cáo CSAT.
  - Then: Hiển thị Chưa có dữ liệu đánh giá, số mẫu bằng 0 và không trình bày điểm trung bình giả.

### Tình huống ngoại lệ
- Ticket hoàn thành chưa được đánh giá, kiểm mẫu số chỉ gồm các đánh giá hợp lệ.

---

## FR-RPT-05 – Trích xuất và Tải xuống Báo cáo (Export)

### Mô tả
Cho phép người dùng xuất dữ liệu hiện tại của các báo cáo hoặc danh sách yêu cầu ra định dạng file CSV để phục vụ phân tích ngoại tuyến hoặc lưu trữ.

### Actor
Quản lý, Quản trị viên.

### Mức độ ưu tiên
Trung bình.

### Điều kiện tiên quyết
Bộ lọc báo cáo đã được áp dụng và đang có dữ liệu hiển thị trên màn hình.

### Luồng chính
1. Người dùng bấm nút "Trích xuất CSV" trên giao diện báo cáo.
2. Hệ thống đọc các điều kiện bộ lọc hiện tại (Thời gian, Trạng thái, Danh mục, Quyền dữ liệu).
3. Hệ thống truy xuất dữ liệu dưới dạng bảng.
4. Hệ thống tạo file và tiến hành tải xuống máy tính của người dùng.

### Quy tắc nghiệp vụ
- BR-RPT-07: Dữ liệu bên trong file xuất ra phải tuân thủ nghiêm ngặt quyền truy cập dữ liệu của người dùng. Không được phép xem trên web bị giới hạn nhưng khi tải file lại hiển thị toàn bộ dữ liệu.

### Luồng rẽ nhánh và lỗi
- E-RPT-06: Nếu số lượng bản ghi vượt quá 10.000 dòng, hệ thống hiển thị cảnh báo và chặn tải để bảo vệ hiệu năng máy chủ.

### Tiêu chí nghiệm thu
- **FR-RPT-05/AC-01:** Dữ liệu khớp với phân quyền (Kiểm tra BR-RPT-07)
  - Given: Quản lý phòng Đào tạo đang xem báo cáo tháng 10.
  - When: Thực hiện xuất file CSV.
  - Then: File tải về chỉ chứa dữ liệu Ticket của phòng Đào tạo trong tháng 10, không có dữ liệu phòng khác.
- **FR-RPT-05/AC-02:** Xử lý hiển thị tiếng Việt
  - Given: Người dùng tải file về máy.
  - When: Mở file bằng phần mềm bảng tính (như Excel).
  - Then: Các thông tin văn bản hiển thị chuẩn tiếng Việt có dấu, không bị lỗi phông chữ.
- **FR-RPT-05/AC-03:** Chặn trích xuất dữ liệu khổng lồ (Kiểm tra E-RPT-06)
  - Given: Truy vấn báo cáo hiện tại trả về 15.000 dòng dữ liệu.
  - When: Người dùng bấm Trích xuất.
  - Then: Hệ thống chặn tiến trình và báo "Dữ liệu quá lớn. Vui lòng thu hẹp khoảng thời gian trước khi xuất".


### Tình huống ngoại lệ
- Thử đúng giới hạn số dòng đã xác nhận và vượt một dòng, kèm tiếng Việt và bộ lọc quyền.
