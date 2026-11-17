# MODULE M03: STAFF DESK (KHÔNG GIAN CÁN BỘ)

Bản đặc tả phục vụ kế hoạch Mô phỏng. Tham số mật khẩu, thời hạn, tệp, số dòng và chính sách quyền theo Business Rules/NFR là đề xuất cần PM/BA xác nhận trước baseline nghiệm thu.


# 1. Đặc tả yêu cầu chức năng

## FR-STF-01 – Hàng đợi và Quản lý danh sách Ticket (Ticket Queue)

### Mô tả
Cho phép cán bộ xử lý theo dõi tập trung, tìm kiếm, lọc và sắp xếp các Ticket thuộc phạm vi bộ phận của mình nhằm lựa chọn yêu cầu cần ưu tiên giải quyết.

### Actor
Cán bộ xử lý (Staff), Trưởng bộ phận (Manager).

### Mức độ ưu tiên
Cao.

### Điều kiện tiên quyết
Cán bộ đã đăng nhập thành công.

### Luồng chính
1. Cán bộ truy cập khu vực Staff Desk.
2. Hệ thống xác định quyền hạn bộ phận của cán bộ để tải dữ liệu.
3. Hệ thống hiển thị Hàng đợi Ticket (Ticket Queue) dạng danh sách, bao gồm: Mã ID, Tiêu đề, Sinh viên gửi, Trạng thái, Mức độ ưu tiên, Người phụ trách và Ngày tạo.
4. Cán bộ nhập từ khóa vào thanh tìm kiếm hoặc sử dụng các bộ lọc (Trạng thái, Danh mục, Mức độ ưu tiên).
5. Hệ thống tải lại danh sách hiển thị các kết quả khớp với điều kiện lọc/tìm kiếm.
6. Cán bộ có thể bấm vào tiêu đề cột để sắp xếp (VD: sắp xếp theo Ngày tạo gần nhất).
7. Cán bộ chọn một Ticket cụ thể để mở xem chi tiết.

### Quy tắc nghiệp vụ
- BR-STF-01: Dữ liệu (Data Scope) hiển thị trên Hàng đợi bắt buộc phải khớp với quyền truy cập phòng ban của cán bộ đó.
- BR-STF-02: Kết quả tìm kiếm và bộ lọc phải được kết hợp (AND logic) nếu cán bộ sử dụng nhiều điều kiện cùng lúc.

### Luồng rẽ nhánh và lỗi
- E-STF-01: Nếu bộ phận của cán bộ chưa có bất kỳ Ticket nào, hoặc kết quả tìm kiếm/lọc không khớp với dữ liệu, hệ thống hiển thị trạng thái trống kèm thông báo "Không tìm thấy Ticket nào phù hợp".

### Tiêu chí nghiệm thu
- **FR-STF-01/AC-01:** Hiển thị dữ liệu đúng phạm vi phòng ban (Kiểm tra BR-STF-01)
  - Given: Cán bộ thuộc phòng Đào tạo.
  - When: Cán bộ truy cập Staff Desk.
  - Then: Hệ thống chỉ hiển thị danh sách các Ticket thuộc danh mục của phòng Đào tạo.
- **FR-STF-01/AC-02:** Áp dụng bộ lọc đa điều kiện (Kiểm tra BR-STF-02)
  - Given: Cán bộ đang ở Hàng đợi.
  - When: Cán bộ chọn trạng thái "Mới tạo" và mức ưu tiên "Cao".
  - Then: Hệ thống chỉ hiển thị các Ticket thỏa mãn đồng thời cả 2 điều kiện này.
- **FR-STF-01/AC-03:** Hiển thị thông báo khi không có dữ liệu (Kiểm tra E-STF-01)
  - Given: Cán bộ đang tìm kiếm Ticket.
  - When: Cán bộ nhập một Ticket ID không tồn tại.
  - Then: Danh sách trống trơn và hệ thống báo "Không tìm thấy Ticket nào phù hợp".


### Tình huống ngoại lệ
- Kết hợp bộ lọc không có kết quả với dữ liệu ở phòng khác, kiểm trạng thái trống không rò rỉ dữ liệu.

---

## FR-STF-02 – Tự động phân luồng và Gán Ticket (Auto-Routing & Assignment)

### Mô tả
Hệ thống tự động tiếp nhận Ticket từ sinh viên, phân luồng về đúng phòng ban theo danh mục, sau đó hỗ trợ Cán bộ Trưởng phòng gán Ticket cho nhân sự cụ thể.

### Actor
Hệ thống (Phân luồng), Trưởng bộ phận hoặc Cán bộ xử lý (Phân công).

### Mức độ ưu tiên
Cao.

### Điều kiện tiên quyết
Ticket đã được tạo thành công bởi sinh viên ở Module M02.

### Luồng chính
1. Hệ thống tiếp nhận Ticket mới, đọc thông tin Danh mục (Category).
2. Hệ thống tra cứu Quy tắc phân luồng (Routing Rule) và chuyển ẩn Ticket về đúng Phòng ban (Department) chịu trách nhiệm.
3. Trưởng bộ phận (Manager) mở Ticket chưa được phân công.
4. Trưởng bộ phận chọn chức năng "Phân công" (Assign).
5. Hệ thống hiển thị danh sách các cán bộ xử lý (Staff) thuộc phòng ban đó.
6. Trưởng bộ phận chọn một cán bộ.
7. Hệ thống cập nhật người phụ trách, gửi thông báo cho cán bộ được gán và ghi nhận vào lịch sử Ticket.

### Quy tắc nghiệp vụ
- BR-STF-03: Một Ticket tại một thời điểm chỉ có thể được gán cho tối đa 01 Cán bộ phụ trách (Assignee).
- BR-STF-04: Cán bộ xử lý (Staff) có thể tự gán (Assign to me) Ticket cho chính mình nếu Ticket chưa có ai phụ trách.

### Luồng rẽ nhánh và lỗi
- E-STF-02: Nếu hệ thống không tìm thấy Quy tắc phân luồng phù hợp cho Danh mục của Ticket, Ticket sẽ được chuyển vào một hàng đợi dự phòng (Unassigned Queue) để Quản trị viên (Admin) xử lý thủ công.

### Tiêu chí nghiệm thu
- **FR-STF-02/AC-01:** Phân luồng tự động về đúng phòng ban
  - Given: Sinh viên vừa gửi thành công một Ticket với danh mục "Kỹ thuật".
  - When: Hệ thống quét Quy tắc phân luồng.
  - Then: Ticket xuất hiện ngay lập tức trong Hàng đợi của phòng IT, nhân sự phòng khác không nhìn thấy.
- **FR-STF-02/AC-02:** Gán người phụ trách thành công (Kiểm tra BR-STF-03)
  - Given: Trưởng bộ phận đang thao tác trên một Ticket mới.
  - When: Trưởng bộ phận chọn gán cho nhân viên A.
  - Then: Tên nhân viên A xuất hiện ở cột "Người phụ trách", hệ thống thông báo gán thành công.
- **FR-STF-02/AC-03:** Lỗi không có quy tắc phân luồng (Kiểm tra E-STF-02)
  - Given: Một danh mục mới vừa tạo nhưng chưa cài đặt Routing Rule.
  - When: Có Ticket gửi vào danh mục này.
  - Then: Ticket không bị mất mà rơi vào Hàng đợi dự phòng, chờ Admin xử lý.

- **FR-STF-02/AC-04:** Tự nhận và tranh chấp người phụ trách (BR-STF-03, BR-STF-04)
  - Given: Ticket chưa có người phụ trách, hai Staff cùng phòng mở phiên bản hiện tại.
  - When: Hai người đồng thời chọn tự nhận Ticket.
  - Then: Chỉ một người được lưu làm assignee, yêu cầu còn lại được báo dữ liệu đã thay đổi và tải lại, không ghi đè người nhận trước.

### Tình huống ngoại lệ
- Hai Staff cùng tự nhận một Ticket chưa gán, kiểm chỉ một assignee được lưu.

---

## FR-STF-03 – Cập nhật trạng thái và Mức độ ưu tiên

### Mô tả
Cho phép cán bộ xử lý thay đổi trạng thái và mức độ ưu tiên của Ticket để phản ánh chính xác tiến độ giải quyết sự việc.

### Actor
Cán bộ xử lý.

### Mức độ ưu tiên
Cao.

### Điều kiện tiên quyết
Cán bộ có quyền xử lý Ticket đang mở chi tiết Ticket đó.

### Luồng chính
1. Cán bộ mở chi tiết một Ticket.
2. Cán bộ chọn thay đổi Trạng thái (VD: từ "Mới tạo" sang "Đang xử lý") hoặc thay đổi Mức độ ưu tiên (VD: từ "Thấp" lên "Cao").
3. Hệ thống xác thực quyền thao tác.
4. Hệ thống cập nhật thông tin lên cơ sở dữ liệu.
5. Hệ thống ghi chú sự thay đổi này vào Dòng thời gian (Timeline/History) của Ticket.

### Quy tắc nghiệp vụ
- BR-STF-05: Cán bộ không được phép đổi trạng thái về "Mới tạo" nếu Ticket đã được bắt đầu xử lý.
- BR-STF-06: Khi trạng thái được chuyển sang "Hoàn thành", hệ thống sẽ tự động cập nhật thời gian giải quyết thực tế (Resolution Time).

### Luồng rẽ nhánh và lỗi
- E-STF-03: Nếu một cán bộ khác đã thay đổi trạng thái của Ticket này vài giây trước đó, hệ thống sẽ chặn thao tác hiện tại và báo lỗi "Dữ liệu đã cũ, vui lòng tải lại trang".

### Tiêu chí nghiệm thu
- **FR-STF-03/AC-01:** Chuyển trạng thái hợp lệ (Kiểm tra BR-STF-06)
  - Given: Ticket đang ở trạng thái "Đang xử lý".
  - When: Cán bộ chuyển sang trạng thái "Hoàn thành".
  - Then: Hệ thống cập nhật thành công, lưu lại mốc thời gian hoàn thành vào lịch sử.
- **FR-STF-03/AC-02:** Xử lý xung đột dữ liệu (Kiểm tra E-STF-03)
  - Given: Cán bộ A và Trưởng phòng B cùng đang mở chi tiết 1 Ticket. Trưởng phòng B vừa đổi mức ưu tiên thành Cao.
  - When: Cán bộ A bấm chuyển trạng thái thành "Đang xử lý" mà chưa tải lại trang.
  - Then: Hệ thống từ chối cập nhật và báo "Dữ liệu đã có sự thay đổi từ người dùng khác. Vui lòng tải lại".

- **FR-STF-03/AC-03:** Chặn chuyển lùi về Mới tạo (BR-STF-05)
  - Given: Ticket đã bắt đầu xử lý.
  - When: Staff gọi giao diện hoặc API yêu cầu đổi về Mới tạo.
  - Then: Hệ thống từ chối, giữ trạng thái và lịch sử đã có.

### Tình huống ngoại lệ
- Hai cán bộ lưu thay đổi trên cùng phiên bản Ticket, kiểm yêu cầu cũ bị từ chối và lịch sử không bị ghi đè.

---

## FR-STF-04 – Chuyển tiếp và Chuyển cấp (Transfer & Escalation)

### Mô tả
Hỗ trợ cán bộ chuyển tiếp Ticket sang bộ phận khác nếu xử lý nhầm luồng, hoặc chuyển cấp lên cấp quản lý cao hơn nếu tính chất vụ việc vượt quá thẩm quyền.

### Actor
Cán bộ xử lý.

### Mức độ ưu tiên
Trung bình.

### Điều kiện tiên quyết
Ticket đang chưa đóng.

### Luồng chính
1. Cán bộ nhận thấy Ticket không thuộc chuyên môn hoặc quá khó.
2. Cán bộ chọn chức năng Chuyển tiếp (Transfer) hoặc Chuyển cấp (Escalate).
3. Hệ thống hiển thị danh sách phòng ban (nếu chuyển tiếp) hoặc danh sách Quản lý (nếu chuyển cấp).
4. Cán bộ chọn đích đến và BẮT BUỘC nhập lý do chuyển.
5. Hệ thống thu hồi quyền phụ trách của cán bộ hiện tại.
6. Ticket được đẩy sang Hàng đợi của đối tượng mới, ghi chú lý do vào Lịch sử.

### Quy tắc nghiệp vụ
- BR-STF-07: Việc chuyển tiếp/chuyển cấp bắt buộc phải kèm theo lý do giải trình.
- BR-STF-08: Hệ thống không tạo mới Ticket, mã Ticket ID vẫn giữ nguyên để đảm bảo liền mạch lịch sử.

### Luồng rẽ nhánh và lỗi
- E-STF-04: Nếu cán bộ bấm chuyển tiếp mà bỏ trống ô lý do, hệ thống chặn lại và báo lỗi.

### Tiêu chí nghiệm thu
- **FR-STF-04/AC-01:** Chuyển tiếp thành công, giữ nguyên ID (Kiểm tra BR-STF-08)
  - Given: Cán bộ Đào tạo đang giữ Ticket #123.
  - When: Cán bộ nhập lý do "Liên quan đến mạng" và chuyển tiếp cho phòng IT.
  - Then: Ticket #123 biến mất khỏi hàng đợi Đào tạo, xuất hiện ở hàng đợi IT với đầy đủ lịch sử cũ.
- **FR-STF-04/AC-02:** Chặn chuyển khi thiếu lý do (Kiểm tra BR-STF-07, E-STF-04)
  - Given: Cán bộ đang ở form chuyển cấp.
  - When: Cán bộ không nhập chữ nào vào ô lý do và bấm Lưu.
  - Then: Hệ thống không thực hiện việc chuyển và báo "Lý do chuyển là bắt buộc".


### Tình huống ngoại lệ
- Mở Ticket ở phòng cũ sau khi chuyển phòng thành công, kiểm phạm vi dữ liệu mới và giữ nguyên Ticket ID.

---

## FR-STF-05 – Phản hồi sinh viên và Yêu cầu bổ sung

### Mô tả
Cho phép cán bộ trao đổi, gửi văn bản phản hồi chính thức cho sinh viên, hoặc yêu cầu sinh viên cung cấp thêm giấy tờ/thông tin để tiếp tục xử lý.

### Actor
Cán bộ xử lý.

### Mức độ ưu tiên
Cao.

### Điều kiện tiên quyết
Cán bộ đang phụ trách Ticket đó.

### Luồng chính
1. Cán bộ kéo xuống phần Trao đổi trong chi tiết Ticket.
2. Cán bộ soạn thảo nội dung phản hồi, đính kèm tệp nếu có.
3. Cán bộ có quyền chọn sử dụng Mẫu phản hồi (Template) có sẵn để điền nhanh văn bản.
4. Nếu chỉ là trả lời thông thường, cán bộ bấm "Gửi". Hệ thống lưu phản hồi và gửi thông báo cho sinh viên.
5. Nếu yêu cầu sinh viên cung cấp thêm giấy tờ, cán bộ chọn "Gửi và Đổi trạng thái thành Cần bổ sung". 
6. Hệ thống thực hiện 2 thao tác cùng lúc: Gửi phản hồi và tự động đổi trạng thái Ticket sang "Cần bổ sung".

### Quy tắc nghiệp vụ
- BR-STF-09: Cán bộ chỉ có thể dùng chức năng "Yêu cầu bổ sung" khi Ticket đang ở trạng thái "Đang xử lý".
- BR-STF-10: Cán bộ có thể sử dụng các Biến tự động (Placeholder) như {Ten_Sinh_Vien} trong Mẫu phản hồi để hệ thống tự điền.

### Luồng rẽ nhánh và lỗi
- E-STF-05: Nếu cán bộ gửi tệp đính kèm chứa mã độc hoặc vi phạm chính sách bảo mật tệp, hệ thống từ chối việc gửi và cảnh báo.

### Tiêu chí nghiệm thu
- **FR-STF-05/AC-01:** Gửi yêu cầu bổ sung thành công
  - Given: Ticket đang ở trạng thái "Đang xử lý".
  - When: Cán bộ nhập "Vui lòng gửi kèm CCCD" và bấm "Gửi & Đổi trạng thái".
  - Then: Lời nhắn xuất hiện trong luồng chat và trạng thái Ticket đổi thành "Cần bổ sung".
- **FR-STF-05/AC-02:** Sử dụng Template phản hồi (Kiểm tra BR-STF-10)
  - Given: Cán bộ đang soạn thảo phản hồi.
  - When: Cán bộ chọn mẫu "Chào mừng".
  - Then: Nội dung ô văn bản tự động điền "Chào em {Tên}, phòng ban đã nhận được yêu cầu..."

- **FR-STF-05/AC-03:** Chặn yêu cầu bổ sung sai trạng thái (BR-STF-09)
  - Given: Ticket đang ở Mới tạo hoặc Hoàn thành.
  - When: Staff gửi thao tác Yêu cầu bổ sung qua API.
  - Then: Hệ thống từ chối thao tác và giữ nguyên trạng thái.
- **FR-STF-05/AC-04:** Từ chối tệp không an toàn (E-STF-05)
  - Given: QA chuẩn bị tệp kiểm thử an toàn mô phỏng định dạng bị cấm theo BR-02.
  - When: Staff gửi phản hồi kèm tệp đó.
  - Then: Hệ thống từ chối gửi, nêu lỗi tệp, không phát hành phản hồi hoặc chuyển trạng thái một phần.

### Tình huống ngoại lệ
- Gửi tệp vi phạm chính sách hoặc thao tác yêu cầu bổ sung từ màn hình đã cũ, kiểm không lưu một phần.

---

## FR-STF-06 – Ghi chú nội bộ (Internal Note)

### Mô tả
Cán bộ xử lý có thể viết các trao đổi, nhắc nhở hoặc tóm tắt sự việc lưu trữ ngay trong Ticket. Các ghi chú này hoàn toàn "tàng hình" đối với sinh viên.

### Actor
Cán bộ xử lý, Trưởng bộ phận, Quản trị viên.

### Mức độ ưu tiên
Trung bình.

### Điều kiện tiên quyết
Cán bộ có quyền truy cập vào Ticket.

### Luồng chính
1. Cán bộ mở phần Trao đổi của Ticket.
2. Cán bộ chuyển tab từ "Phản hồi công khai" sang tab "Ghi chú nội bộ".
3. Cán bộ nhập văn bản (thường có giao diện đổi màu, VD: nền vàng) và đính kèm tài liệu nội bộ nếu cần.
4. Cán bộ bấm Lưu.
5. Hệ thống lưu ghi chú, hiển thị vào Timeline của Ticket dưới dạng Nhãn nội bộ.

### Quy tắc nghiệp vụ
- BR-STF-11: Ghi chú nội bộ tuyệt đối không được kích hoạt thông báo (notification) hay hiển thị dưới bất kỳ hình thức nào trên Student Portal.
- BR-STF-12: Ghi chú nội bộ của bộ phận nào thì chỉ cán bộ thuộc bộ phận đó (và Admin/Manager) mới xem được.

### Luồng rẽ nhánh và lỗi
- E-STF-06: Nếu cán bộ nhập văn bản quá giới hạn ký tự cho phép, hệ thống chặn việc lưu và báo lỗi.

### Tiêu chí nghiệm thu
- **FR-STF-06/AC-01:** Sinh viên không nhìn thấy ghi chú nội bộ (Kiểm tra BR-STF-11)
  - Given: Cán bộ đã lưu thành công một Ghi chú nội bộ trên Ticket #123.
  - When: Sinh viên sở hữu Ticket #123 đăng nhập và xem chi tiết yêu cầu.
  - Then: Dòng thời gian của sinh viên không hề có đoạn ghi chú đó, cũng không nhận được email thông báo nào.

- **FR-STF-06/AC-02:** Giới hạn quyền ghi chú (BR-STF-12)
  - Given: Có ghi chú thuộc phòng A và một Staff chỉ thuộc phòng B.
  - When: Staff B mở Ticket hoặc gọi API đọc ghi chú của phòng A.
  - Then: Nội dung ghi chú bị chặn. Manager trong phạm vi quản lý và Admin được kiểm theo ma trận quyền đã xác nhận.
- **FR-STF-06/AC-03:** Vượt giới hạn ký tự (E-STF-06)
  - Given: Baseline đã xác nhận giới hạn L ký tự cho ghi chú.
  - When: Nhập L ký tự rồi thử L+1 ký tự.
  - Then: L ký tự được lưu nếu hợp lệ. L+1 bị từ chối với thông báo, không cắt mất nội dung hoặc tạo bản ghi dở dang.

### Tình huống ngoại lệ
- Thử ghi chú tại L và L+1 ký tự theo giới hạn đã xác nhận, kiểm không lộ nội dung qua API hoặc thông báo sinh viên.

---

## FR-STF-07 – Theo dõi hạn và cảnh báo SLA

### Mô tả
Cán bộ và quản lý xem hạn xử lý, mức cảnh báo Ticket thuộc phạm vi theo SLA và lịch làm việc đã cấu hình.

### Actor
Staff, Manager.

### Mức độ ưu tiên
Cao.

### Điều kiện tiên quyết
Ticket có priority và cấu hình SLA hợp lệ theo BR-03, BR-04.

### Luồng chính
1. Hệ thống tính hạn theo priority, lịch làm việc và chính sách chờ bổ sung đã xác nhận.
2. Hàng đợi hiển thị hạn và cảnh báo hiện tại.
3. Người dùng lọc Ticket sắp hạn hoặc quá hạn trong phạm vi quyền.
4. Khi hoàn thành, hệ thống giữ dữ liệu đo và ngừng tạo cảnh báo mới cho lần xử lý đã kết thúc.

### Quy tắc nghiệp vụ
- BR-STF-13: Công thức thời hạn và ngưỡng cảnh báo dùng BR-03, BR-04 gốc.
- BR-STF-14: Cảnh báo chỉ hiển thị trong phạm vi quyền dữ liệu và áp dụng với Ticket chưa hoàn thành.

### Luồng rẽ nhánh và lỗi
- E-STF-07: Thiếu cấu hình SLA hoặc lịch làm việc thì báo cấu hình chưa hoàn tất, chuyển PM/BA và Admin xử lý, tránh hiển thị một hạn giả.

### Tiêu chí nghiệm thu
- **FR-STF-07/AC-01:** Cảnh báo đúng biên thời gian (BR-STF-13)
  - Given: Bộ dữ liệu có Ticket tại trên, đúng và dưới ngưỡng vàng, đúng hạn và quá hạn theo BR-04 đã xác nhận.
  - When: Mở hàng đợi bằng thời gian kiểm thử cố định.
  - Then: Mỗi Ticket có hạn và màu đúng công thức được xác nhận, điểm đúng hạn được kiểm riêng.
- **FR-STF-07/AC-02:** Phạm vi và Ticket hoàn thành (BR-STF-14)
  - Given: Có Ticket phòng khác và một Ticket đã hoàn thành.
  - When: Staff mở bộ lọc cảnh báo.
  - Then: Ticket ngoài quyền bị ẩn, Ticket đã hoàn thành không phát sinh cảnh báo quá hạn mới cho lần xử lý đã xong.
- **FR-STF-07/AC-03:** Thiếu cấu hình (E-STF-07)
  - Given: Môi trường thử thiếu SLA cho một priority.
  - When: Tạo hoặc hiển thị Ticket liên quan.
  - Then: Hiển thị tình trạng thiếu cấu hình, ghi vấn đề cho người phụ trách và không tạo hạn giả.

### Tình huống ngoại lệ
- Ticket tạo ngoài giờ, gặp ngày nghỉ hoặc đổi priority khi đang Pending, kiểm theo quyết định SLA đã xác nhận.
