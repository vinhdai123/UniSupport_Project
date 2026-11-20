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
  - Given: Staff Đào tạo và Staff IT có phạm vi của từng phòng. Bộ dữ liệu TS-041 có Ticket được chuyển từ Đào tạo sang IT và giữ danh mục Đào tạo.
  - When: Hai Staff mở hàng đợi, sau đó lọc danh mục Đào tạo.
  - Then: Hàng đợi khớp tập Ticket được phép xem theo OQ-05. Khi lọc, kết quả là giao của tập đã được cấp quyền và danh mục được chọn. Ghi riêng tập trước và sau khi lọc cho từng tài khoản.
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
1. Staff Desk nhận Ticket mới cùng kết quả phòng tiếp nhận mà luồng tạo Ticket đã lưu theo FR-STU-01 tại MS-03.
2. Tại MS-04, hệ thống áp dụng quy tắc danh mục–phòng đích cho luồng tích hợp và đưa Ticket vào hàng đợi đúng quyền. Nếu không có quy tắc hợp lệ, áp dụng E-STF-02. WBS 4.4 và #63 hoàn thiện phần này trên đầu ra #60.
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
Cán bộ và quản lý xử lý Ticket sai tuyến bằng chuyển phòng hoặc chuyển cấp. Cơ chế xác nhận trực tiếp và phạm vi dữ liệu sau chuyển dưới đây là **đề xuất chờ xác nhận tại [OQ-05](../../08-project/open-questions.md)**.

### Actor
Staff hoặc Manager có quyền chuyển Ticket hiện tại theo ma trận quyền. Staff thiếu quyền báo Manager qua kênh phối hợp hiện hành để người có quyền thực hiện.

### Mức độ ưu tiên
Trung bình.

### Điều kiện tiên quyết
Ticket chưa Hoàn thành. Người thực hiện có quyền chuyển trên Ticket và đích hợp lệ theo ma trận quyền.

### Luồng chính
1. Người có quyền mở Chuyển tiếp hoặc Chuyển cấp. Hệ thống liệt kê phòng ban hoặc Manager được phép nhận.
2. Người thực hiện chọn đích, nhập lý do và xác nhận. Xác nhận của người có quyền là quyết định chuyển trực tiếp, không tạo trạng thái chờ duyệt.
3. API kiểm quyền hiện tại, lý do, đích và phiên bản Ticket tại thời điểm xác nhận. Nếu hợp lệ, cập nhật đích và quyền phụ trách, giữ Ticket ID.
4. Hệ thống lưu sự kiện bàn giao vào lịch sử gồm nguồn, đích, người thực hiện, thời điểm và lý do. Áp dụng chính sách SLA đã xác nhận tại BR-03.

### Quy tắc nghiệp vụ
- BR-STF-07: Chuyển tiếp/chuyển cấp cần quyền trên Ticket và đích, kèm lý do giải trình. Lý do là dữ liệu của sự kiện bàn giao, chỉ xem được bởi người được phép xem sự kiện, tách khỏi ghi chú nội bộ của phòng.
- BR-STF-08: Giữ Ticket ID và lịch sử. Với chuyển phòng, phòng đích được xem lịch sử nghiệp vụ thuộc quyền hiện hành như trao đổi công khai, mốc trạng thái và sự kiện bàn giao. Ghi chú và tệp nội bộ vẫn theo phòng tạo và ma trận quyền BR-STF-12. Phòng cũ mất quyền phát sinh từ việc phụ trách trước đó. Quyền độc lập khác tiếp tục theo ma trận quyền, được kiểm lại khi đọc Ticket, ghi chú và tệp.

### Luồng rẽ nhánh và lỗi
- E-STF-04: Nếu thiếu lý do, thiếu quyền, đích không hợp lệ hoặc phiên bản Ticket đã cũ, API từ chối, nêu lý do phù hợp và giữ nguyên Ticket. Với phiên bản cũ, yêu cầu tải lại.

### Tiêu chí nghiệm thu
- **FR-STF-04/AC-01:** Chuyển phòng, giữ ID và áp quyền mới (BR-STF-07, BR-STF-08)
  - Given: Staff Đào tạo có quyền chuyển Ticket #123 cùng danh mục Đào tạo sang IT. Ticket có trao đổi công khai, lịch sử trạng thái, ghi chú và tệp nội bộ của Đào tạo. Hai tài khoản thử chỉ thuộc một phòng và không có quyền độc lập khác.
  - When: Staff nhập lý do và xác nhận chuyển sang IT trong ca chỉ đổi phòng phụ trách. Mở Ticket, liên kết cũ và tệp nội bộ bằng các tài khoản thử của hai phòng.
  - Then: Ticket giữ ID, danh mục gốc và lịch sử. Ticket xuất hiện ở hàng đợi IT và rời hàng đợi Đào tạo. Staff IT thấy trao đổi công khai, lịch sử trạng thái và sự kiện bàn giao có lý do. Staff IT không xem/tải được ghi chú và tệp nội bộ Đào tạo. Tài khoản chỉ có quyền theo phân công cũ bị chặn khi mở lại Ticket.
- **FR-STF-04/AC-02:** Từ chối yêu cầu chuyển không hợp lệ (BR-STF-07, E-STF-04)
  - Given: Có Ticket hợp lệ, tài khoản có quyền và tài khoản thiếu quyền với Ticket.
  - When: Thử độc lập chuyển thiếu lý do, chuyển khi thiếu quyền, chọn đích ngoài phạm vi và xác nhận từ phiên bản Ticket cũ.
  - Then: Mỗi yêu cầu bị từ chối với lý do phù hợp. Dữ liệu cũ yêu cầu tải lại. Không đổi hàng đợi, assignee, Ticket ID hoặc tạo sự kiện chuyển thành công.


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
- **FR-STF-05/AC-02:** Thay biến trong mẫu phản hồi (BR-STF-10)
  - Given: Ticket T-MOCK-021 của sinh viên giả lập Nguyễn Minh An. Mẫu đã lưu là "Chào em {Ten_Sinh_Vien}, phòng ban đã nhận được yêu cầu {Ma_Ticket}."
  - When: Staff chọn mẫu khi soạn phản hồi cho Ticket.
  - Then: Bản nháp hiện "Chào em Nguyễn Minh An, phòng ban đã nhận được yêu cầu T-MOCK-021." Hai biến đã được thay bằng dữ liệu của Ticket hiện tại, mẫu gốc giữ nguyên và phản hồi chờ Staff gửi.

- **FR-STF-05/AC-03:** Chặn yêu cầu bổ sung sai trạng thái (BR-STF-09)
  - Given: Ticket đang ở Mới tạo hoặc Hoàn thành.
  - When: Staff gửi thao tác Yêu cầu bổ sung qua API.
  - Then: Hệ thống từ chối thao tác và giữ nguyên trạng thái.
- **FR-STF-05/AC-04:** Từ chối tệp không an toàn (E-STF-05)
  - Given: Ticket Đang xử lý. QA có bộ dữ liệu vô hại mô phỏng định dạng bị cấm theo BR-02 và một tệp giả lập đúng định dạng, dung lượng. Trong ca thứ hai, bộ kiểm tra nội dung mô phỏng trả kết quả Không an toàn.
  - When: Thử độc lập gửi phản hồi với đầu vào sai định dạng, rồi gửi và yêu cầu bổ sung với tệp đúng định dạng nhưng bị đánh dấu Không an toàn.
  - Then: Cả hai lần bị từ chối với lý do tương ứng. Không phát hành phản hồi, không gắn tệp vào Ticket, không gửi thông báo và không đổi trạng thái sang Cần bổ sung.

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
- BR-STF-12: Đọc ghi chú và tệp nội bộ cần đồng thời có quyền trên Ticket và quyền với phòng tạo ghi chú. Staff cần thuộc phòng tạo. Manager/Admin chỉ xem trong phạm vi ma trận quyền cho phép. Chuyển phòng theo FR-STF-04 giữ nguyên phòng tạo và phạm vi của ghi chú.

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
