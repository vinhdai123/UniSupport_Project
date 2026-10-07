# PRD – MODULE A: PHÂN HỆ TIẾP NHẬN & THEO DÕI YÊU CẦU (SINH VIÊN)

> **Dự án:** UniSupport – Hệ thống Quản lý Yêu cầu Hỗ trợ Sinh viên  
> **Khách hàng:** Aurora University  
> **Mã phân hệ:** MOD-STU (Module A - Student Portal)  
> **Phiên bản:** v1.0 | Ngày cập nhật: 03/10/2026  
> **Tài liệu cha:** [UNISUPPORT_PRD.md](file:///c:/Users/Admin/Documents/New%20Folder/UniSupport_Project/docs/prd/UNISUPPORT_PRD.md)  
> **Giai đoạn triển khai chính:** Phase P4 (Tuần 9–12)

---

## 1. Tổng quan phân hệ

### 1.1. Mục tiêu
Xây dựng cổng dịch vụ một cửa trực tuyến dành riêng cho khoảng 3.000 sinh viên Aurora University, giúp sinh viên dễ dàng tạo yêu cầu hỗ trợ theo danh mục, tra cứu bài viết hướng dẫn (FAQ), theo dõi tiến độ xử lý theo thời gian thực và trao đổi trực tiếp với cán bộ xử lý mọi lúc, mọi nơi.

### 1.2. Đối tượng sử dụng chính (Target Actor)
* **Sinh viên:** Sinh viên đang theo học tại Aurora University có tài khoản định danh hợp lệ trên hệ thống UniSupport.

---

## 2. User Persona & Use Case chính

### 2.1. Persona – Sinh viên Aurora University
* **Vai trò:** Người gửi yêu cầu hỗ trợ.
* **Mục tiêu:** Gửi yêu cầu nhanh chóng, đính kèm chứng từ minh họa, nhận phản hồi rõ ràng và theo dõi được tiến trình xử lý mà không phải trực tiếp đến văn phòng trường.
* **Khó khăn trước đây:** Gửi email hoặc liên hệ điện thoại dễ bị thất lạc, không biết ai đang thụ lý và khi nào có kết quả.
* **Môi trường sử dụng:** Trình duyệt Web trên Laptop/Desktop và Thiết bị di động (Smartphone).

### 2.2. Use Case chính: Sinh viên tạo và nộp Ticket
1. Sinh viên đăng nhập vào hệ thống UniSupport.
2. Sinh viên chọn danh mục dịch vụ phù hợp (*Đào tạo*, *Công tác sinh viên*, *Kế toán/Tài chính*, *Khảo thí*).
3. Hệ thống hiển thị form yêu cầu, tự động gợi ý FAQ liên quan dựa trên tiêu đề sinh viên nhập.
4. Sinh viên nhập tiêu đề, mô tả chi tiết và đính kèm tối đa 03 tệp minh chứng (PDF, JPG, PNG $\le$ 5MB).
5. Sinh viên nhấn "Gửi yêu cầu".
6. Hệ thống cấp phát mã định danh duy nhất `AU-2026-XXXX`, ghi nhận trạng thái `Mới tạo` và gửi email xác nhận.

---

## 3. Đặc tả chi tiết các yêu cầu chức năng (Functional Specifications)

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

## 4. Yêu cầu phi chức năng phân hệ (Module NFR)
* **Giao diện di động:** Tối ưu hóa 100% cho màn hình điện thoại (iOS Safari, Android Chrome), kích thước nút bấm tối thiểu $44 \times 44px$.
* **Bảo mật dữ liệu:** Sinh viên tuyệt đối không thể xem Ticket của sinh viên khác hoặc xem Ghi chú nội bộ của cán bộ.
* **Thời gian phản hồi:** Tải trang chi tiết Ticket $\le 1.5$ giây; tìm kiếm FAQ $\le 0.5$ giây.
