# MODULE M02: STUDENT PORTAL (CỔNG HỖ TRỢ SINH VIÊN)

# 1. Đặc tả yêu cầu chức năng

## FR-STU-01 – Tạo yêu cầu hỗ trợ (Submit Ticket)

### Mô tả
Cho phép sinh viên gửi yêu cầu hỗ trợ trực tuyến theo danh mục để hệ thống ghi nhận, tự động cấp mã và chuyển vào quy trình phân luồng xử lý phù hợp.

### Actor
Sinh viên.

### Mức độ ưu tiên
Cao.

### Điều kiện tiên quyết
Sinh viên đã đăng nhập thành công vào Cổng hỗ trợ sinh viên.

### Luồng chính
1. Sinh viên truy cập chức năng tạo yêu cầu hỗ trợ.
2. Hệ thống hiển thị biểu mẫu với các danh mục yêu cầu hiện có.
3. Sinh viên chọn danh mục phù hợp.
4. Sinh viên nhập tiêu đề, nội dung chi tiết và đính kèm tài liệu/hình ảnh nếu cần.
5. Sinh viên chọn gửi yêu cầu.
6. Hệ thống xác thực dữ liệu. Nếu hợp lệ, hệ thống tạo bản ghi mới, liên kết với tài khoản sinh viên.
7. Hệ thống tự động tạo mã Ticket ID và thiết lập trạng thái ban đầu là "Mới tạo".
8. Yêu cầu được tự động chuyển đến phòng ban xử lý dựa trên danh mục.
9. Hệ thống hiển thị thông báo tạo thành công kèm mã Ticket ID.

### Quy tắc nghiệp vụ
- BR-STU-01: Tiêu đề, nội dung và danh mục là các trường thông tin bắt buộc.
- BR-STU-02: Việc xác định phòng ban tiếp nhận do hệ thống tự động phân luồng (Routing Rule) dựa trên danh mục, sinh viên không được phép tự chọn phòng ban.
- BR-STU-03: Mã Ticket ID được sinh tự động theo quy tắc hệ thống, đảm bảo tính duy nhất.

### Luồng rẽ nhánh và lỗi
- E-STU-01: Nếu sinh viên để trống thông tin bắt buộc, hệ thống từ chối tạo và đánh dấu đỏ các trường còn thiếu.
- E-STU-02: Nếu tệp đính kèm vượt quá dung lượng quy định hoặc sai định dạng, hệ thống từ chối tải tệp lên và hiển thị thông báo lỗi.

### Tiêu chí nghiệm thu
- **FR-STU-01/AC-01:** Tạo yêu cầu thành công và phân luồng tự động (Kiểm tra BR-STU-02, BR-STU-03)
  - Given: Sinh viên đã nhập đầy đủ thông tin hợp lệ trên biểu mẫu.
  - When: Sinh viên gửi yêu cầu.
  - Then: Hệ thống thông báo thành công, cấp một mã Ticket ID duy nhất, đặt trạng thái "Mới tạo" và chuyển ẩn đến phòng ban tương ứng.
- **FR-STU-01/AC-02:** Xử lý khi thiếu thông tin bắt buộc (Kiểm tra BR-STU-01, E-STU-01)
  - Given: Sinh viên đang ở biểu mẫu tạo yêu cầu.
  - When: Sinh viên bỏ trống nội dung yêu cầu và chọn gửi.
  - Then: Hệ thống không tạo bản ghi và hiển thị cảnh báo "Vui lòng nhập nội dung yêu cầu".
- **FR-STU-01/AC-03:** Xử lý tệp đính kèm không hợp lệ (Kiểm tra E-STU-02)
  - Given: Sinh viên đang đính kèm tài liệu vào yêu cầu.
  - When: Sinh viên tải lên tệp `.exe` hoặc tệp lớn hơn 5MB.
  - Then: Hệ thống hiển thị thông báo "Định dạng tệp không được hỗ trợ hoặc vượt quá 5MB".

### Tình huống ngoại lệ
- Mất kết nối mạng ngay khi sinh viên vừa bấm nút gửi. Hệ thống trình duyệt sẽ giữ nguyên nội dung sinh viên đã nhập thay vì làm trắng trang, đồng thời hiển thị thông báo lỗi mạng để sinh viên thử lại sau.

---

## FR-STU-02 – Xem trạng thái và lịch sử yêu cầu

### Mô tả
Cho phép sinh viên xem danh sách các yêu cầu mình đã gửi, theo dõi trạng thái hiện tại và lịch sử xử lý của từng yêu cầu.

### Actor
Sinh viên.

### Mức độ ưu tiên
Cao.

### Điều kiện tiên quyết
Sinh viên đã đăng nhập.

### Luồng chính
1. Sinh viên truy cập màn hình Danh sách yêu cầu của tôi.
2. Hệ thống hiển thị danh sách các Ticket kèm mã ID, tiêu đề, ngày tạo và trạng thái.
3. Sinh viên có thể dùng bộ lọc (theo trạng thái) hoặc thanh tìm kiếm để tìm Ticket.
4. Sinh viên chọn một Ticket cụ thể.
5. Hệ thống hiển thị chi tiết nội dung Ticket và dòng thời gian (timeline) lịch sử xử lý của Ticket đó.

### Quy tắc nghiệp vụ
- BR-STU-04: Sinh viên chỉ được phép xem danh sách và chi tiết các Ticket do chính tài khoản của mình tạo.

### Luồng rẽ nhánh và lỗi
- E-STU-03: Nếu sinh viên chưa từng tạo yêu cầu nào, hệ thống hiển thị minh họa trạng thái trống (Empty state) với thông điệp "Bạn chưa có yêu cầu hỗ trợ nào".

### Tiêu chí nghiệm thu
- **FR-STU-02/AC-01:** Hiển thị danh sách yêu cầu đúng quyền hạn (Kiểm tra BR-STU-04)
  - Given: Sinh viên A đã tạo 2 yêu cầu, Sinh viên B đã tạo 1 yêu cầu.
  - When: Sinh viên A truy cập Danh sách yêu cầu.
  - Then: Hệ thống chỉ hiển thị đúng 2 yêu cầu của Sinh viên A.
- **FR-STU-02/AC-02:** Hiển thị trạng thái trống (Kiểm tra E-STU-03)
  - Given: Sinh viên C là người mới, chưa từng tạo yêu cầu.
  - When: Sinh viên C truy cập Danh sách yêu cầu.
  - Then: Hệ thống hiển thị thông báo "Bạn chưa có yêu cầu hỗ trợ nào" kèm nút bấm điều hướng đi tạo yêu cầu mới.

### Tình huống ngoại lệ
- Quản trị viên vừa xóa một Ticket rác trên hệ thống. Sinh viên lưu lại đường dẫn (URL) của Ticket đó và truy cập trực tiếp. Hệ thống phải báo lỗi "Yêu cầu không tồn tại hoặc đã bị xóa".

---

## FR-STU-03 – Trao đổi và bổ sung thông tin

### Mô tả
Cho phép sinh viên tương tác trực tiếp với cán bộ phụ trách (chat/bình luận) ngay trong Ticket và đính kèm thêm tài liệu khi được yêu cầu bổ sung thông tin.

### Actor
Sinh viên.

### Mức độ ưu tiên
Cao.

### Điều kiện tiên quyết
Sinh viên đang xem chi tiết một Ticket thuộc sở hữu của mình.

### Luồng chính
1. Sinh viên kéo xuống khu vực "Trao đổi" trong giao diện chi tiết Ticket.
2. Sinh viên nhập nội dung phản hồi.
3. Sinh viên có thể đính kèm thêm hình ảnh hoặc tài liệu.
4. Sinh viên chọn Gửi.
5. Hệ thống lưu nội dung và hiển thị ngay lập tức lên dòng thời gian của Ticket.
6. Nếu Ticket đang ở trạng thái "Cần bổ sung", hệ thống tự động đổi trạng thái Ticket về "Đang xử lý".

### Quy tắc nghiệp vụ
- BR-STU-05: Chức năng gửi phản hồi chỉ khả dụng khi Ticket ở trạng thái "Mới tạo", "Đang xử lý" hoặc "Cần bổ sung". 
- BR-STU-06: Không cho phép trao đổi thêm nếu Ticket đã chuyển sang trạng thái "Đóng" hoặc "Hoàn thành".

### Luồng rẽ nhánh và lỗi
- E-STU-04: Nếu sinh viên không nhập nội dung mà bấm gửi, hệ thống vô hiệu hóa nút gửi hoặc yêu cầu nhập văn bản.

### Tiêu chí nghiệm thu
- **FR-STU-03/AC-01:** Bổ sung thông tin thành công và tự đổi trạng thái
  - Given: Sinh viên đang mở Ticket có trạng thái "Cần bổ sung".
  - When: Sinh viên nhập phản hồi, đính kèm ảnh và bấm Gửi.
  - Then: Phản hồi xuất hiện trên màn hình, đồng thời trạng thái Ticket tự động chuyển thành "Đang xử lý".
- **FR-STU-03/AC-02:** Chặn phản hồi khi Ticket đã hoàn thành (Kiểm tra BR-STU-06)
  - Given: Sinh viên mở một Ticket có trạng thái "Hoàn thành".
  - When: Sinh viên lướt xuống khu vực trao đổi.
  - Then: Khu vực nhập văn bản bị ẩn hoặc vô hiệu hóa, kèm dòng chữ "Yêu cầu này đã đóng, không thể trao đổi thêm".

### Tình huống ngoại lệ
- Cán bộ vừa bấm đóng Ticket trên hệ thống nội bộ đúng vào giây sinh viên đang gõ chữ phản hồi. Khi sinh viên bấm gửi, hệ thống từ chối và báo "Yêu cầu đã được đóng bởi cán bộ xử lý".

---

## FR-STU-04 – Mở lại yêu cầu (Reopen Ticket)

### Mô tả
Cho phép sinh viên yêu cầu cán bộ xem xét lại một Ticket đã được xử lý nếu sinh viên cảm thấy kết quả giải quyết chưa thỏa đáng.

### Actor
Sinh viên.

### Mức độ ưu tiên
Trung bình.

### Điều kiện tiên quyết
Ticket đang ở trạng thái "Hoàn thành".

### Luồng chính
1. Sinh viên truy cập chi tiết Ticket đã Hoàn thành.
2. Sinh viên chọn chức năng "Mở lại yêu cầu".
3. Hệ thống yêu cầu sinh viên nhập lý do muốn mở lại.
4. Sinh viên nhập lý do và xác nhận.
5. Hệ thống cập nhật trạng thái Ticket thành "Mở lại" (Reopened) và thông báo cho cán bộ phụ trách.

### Quy tắc nghiệp vụ
- BR-STU-07: Sinh viên chỉ được phép Mở lại yêu cầu trong vòng 72 giờ (3 ngày) kể từ thời điểm Ticket được chuyển sang trạng thái "Hoàn thành".

### Luồng rẽ nhánh và lỗi
- E-STU-05: Nếu đã quá 72 giờ, nút "Mở lại yêu cầu" sẽ bị hệ thống ẩn đi vĩnh viễn và Ticket chuyển sang trạng thái "Đóng" (Closed).

### Tiêu chí nghiệm thu
- **FR-STU-04/AC-01:** Mở lại yêu cầu hợp lệ
  - Given: Ticket vừa được chuyển sang "Hoàn thành" cách đây 1 ngày.
  - When: Sinh viên bấm Mở lại, nhập lý do và xác nhận.
  - Then: Ticket chuyển trạng thái thành "Mở lại" và lưu lý do vào dòng thời gian.
- **FR-STU-04/AC-02:** Quá thời hạn mở lại (Kiểm tra BR-STU-07, E-STU-05)
  - Given: Ticket đã ở trạng thái "Hoàn thành" cách đây 4 ngày.
  - When: Sinh viên vào xem chi tiết Ticket.
  - Then: Nút "Mở lại yêu cầu" không còn xuất hiện trên giao diện.

### Tình huống ngoại lệ
- Không có.

---

## FR-STU-05 – Đánh giá mức độ hài lòng (CSAT)

### Mô tả
Cho phép sinh viên đánh giá chất lượng hỗ trợ bằng thang điểm sao và nhận xét sau khi một yêu cầu đã được giải quyết xong.

### Actor
Sinh viên.

### Mức độ ưu tiên
Trung bình.

### Điều kiện tiên quyết
Ticket đang ở trạng thái "Hoàn thành" hoặc "Đóng".

### Luồng chính
1. Sinh viên truy cập chi tiết Ticket.
2. Hệ thống hiển thị bảng đánh giá (VD: từ 1 đến 5 sao).
3. Sinh viên chọn số điểm và có thể để lại lời nhận xét.
4. Sinh viên chọn Gửi đánh giá.
5. Hệ thống ghi nhận kết quả và ẩn bảng đánh giá đi.

### Quy tắc nghiệp vụ
- BR-STU-08: Mỗi Ticket chỉ được đánh giá một lần duy nhất.

### Luồng rẽ nhánh và lỗi
- E-STU-06: Nếu sinh viên chọn số sao thấp (1 hoặc 2 sao), hệ thống bắt buộc sinh viên phải nhập lời nhận xét giải thích lý do trước khi cho phép gửi.

### Tiêu chí nghiệm thu
- **FR-STU-05/AC-01:** Gửi đánh giá thành công (Kiểm tra BR-STU-08)
  - Given: Sinh viên ở bảng đánh giá của một Ticket hoàn thành.
  - When: Sinh viên chọn 5 sao, nhập "Hỗ trợ rất nhanh" và bấm Gửi.
  - Then: Hệ thống lưu kết quả, bảng đánh giá biến mất và hiện lời cảm ơn.
- **FR-STU-05/AC-02:** Bắt buộc nhận xét khi đánh giá thấp (Kiểm tra E-STU-06)
  - Given: Sinh viên ở bảng đánh giá.
  - When: Sinh viên chọn 1 sao, không ghi nhận xét và bấm Gửi.
  - Then: Hệ thống chặn lại và báo "Vui lòng cho biết lý do bạn chưa hài lòng để chúng tôi cải thiện".

### Tình huống ngoại lệ
- Không có.

---

## FR-STU-06 – Tra cứu Câu hỏi thường gặp (FAQ)

### Mô tả
Cho phép sinh viên tự tìm kiếm các hướng dẫn, thủ tục và câu hỏi thường gặp trước khi quyết định tạo một Ticket mới nhằm giảm tải cho bộ phận hỗ trợ.

### Actor
Sinh viên.

### Mức độ ưu tiên
Trung bình.

### Điều kiện tiên quyết
Sinh viên có quyền truy cập chức năng FAQ.

### Luồng chính
1. Sinh viên truy cập trung tâm trợ giúp (FAQ).
2. Hệ thống hiển thị các chủ đề câu hỏi phổ biến.
3. Sinh viên nhập từ khóa vào thanh tìm kiếm.
4. Hệ thống tìm kiếm theo tiêu đề và nội dung bài viết.
5. Hệ thống trả về danh sách các bài viết khớp với từ khóa.
6. Sinh viên chọn một bài viết để đọc nội dung chi tiết.

### Quy tắc nghiệp vụ
- BR-STU-09: Hệ thống chỉ hiển thị các bài viết FAQ đã được đánh dấu là Xuất bản (Published) và thuộc đối tượng xem là Sinh viên.

### Luồng rẽ nhánh và lỗi
- E-STU-07: Nếu từ khóa không khớp với bài viết nào, hệ thống thông báo "Không tìm thấy kết quả" và gợi ý nút Tạo yêu cầu hỗ trợ.

### Tiêu chí nghiệm thu
- **FR-STU-06/AC-01:** Tìm kiếm FAQ thành công
  - Given: Hệ thống có bài viết FAQ chứa từ khóa "bảo lưu".
  - When: Sinh viên nhập "bảo lưu" vào ô tìm kiếm.
  - Then: Hệ thống hiển thị các bài viết liên quan đến thủ tục bảo lưu.
- **FR-STU-06/AC-02:** Tìm kiếm không có kết quả (Kiểm tra E-STU-07)
  - Given: Sinh viên ở màn hình FAQ.
  - When: Sinh viên nhập "tên lửa".
  - Then: Hệ thống báo "Không tìm thấy kết quả" kèm liên kết để Sinh viên gửi Ticket hỏi đáp.

### Tình huống ngoại lệ
- Không có.