# PRD – MODULE B: PHÂN HỆ PHÂN LUỒNG & XỬ LÝ YÊU CẦU (CÁN BỘ)

> **Dự án:** UniSupport – Hệ thống Quản lý Yêu cầu Hỗ trợ Sinh viên  
> **Khách hàng:** Aurora University  
> **Mã phân hệ:** MOD-STAFF (Module B - Staff Service Desk)  
> **Phiên bản:** v1.0 | Ngày cập nhật: 03/10/2026  
> **Tài liệu cha:** [UNISUPPORT_PRD.md](file:///c:/Users/Admin/Documents/New%20Folder/UniSupport_Project/docs/prd/UNISUPPORT_PRD.md)  
> **Giai đoạn triển khai chính:** Phase P4 (Tuần 9–12)

---

## 1. Tổng quan phân hệ

### 1.1. Mục tiêu
Cung cấp không gian làm việc tập trung (Service Desk Workspace) cho cán bộ các phòng ban thuộc Aurora University (*Đào tạo*, *Công tác sinh viên*, *Kế hoạch - Tài chính*, *Khảo thí*), hỗ trợ tiếp nhận, phân loại, gán việc, phối hợp nội bộ, cập nhật tiến độ và gửi phản hồi chính thức cho sinh viên nhằm rút ngắn thời gian giải quyết yêu cầu và kiểm soát hạn xử lý (SLA).

### 1.2. Đối tượng sử dụng chính (Target Actor)
* **Cán bộ xử lý (Staff/Agent):** Nhân viên các phòng ban được giao nhiệm vụ tiếp nhận và giải quyết yêu cầu của sinh viên.
* **Quản lý phòng ban (Manager/Supervisor):** Trưởng/Phó phòng có thẩm quyền giám sát, phân công và xử lý các yêu cầu chuyển cấp.

---

## 2. User Persona & Use Case chính

### 2.1. Persona – Cán bộ xử lý phòng ban
* **Vai trò:** Người tiếp nhận và trực tiếp xử lý Ticket.
* **Mục tiêu:** Quản lý danh sách Ticket được giao, tìm kiếm nhanh thông tin sinh viên, sử dụng mẫu câu trả lời soạn sẵn để phản hồi nhanh chóng, chuyển tiếp yêu cầu khi không đúng thẩm quyền.
* **Khó khăn trước đây:** Yêu cầu đến qua email và điện thoại rời rạc, dễ bỏ sót, khó phối hợp với đồng nghiệp, không có công cụ nhắc hạn xử lý.

### 2.2. Use Case chính: Cán bộ tiếp nhận và xử lý Ticket
1. Cán bộ đăng nhập UniSupport, truy cập vào hàng đợi "Chưa phân công" của phòng ban mình.
2. Cán bộ chọn Ticket và bấm "Nhận xử lý" (Self-assign) $\rightarrow$ Ticket chuyển vào tab "Ticket của tôi".
3. Cán bộ xem thông tin, chứng từ đính kèm và kiểm tra mức độ ưu tiên (Priority).
4. Cán bộ có thể:
   - Thêm "Ghi chú nội bộ" để xin ý kiến đồng nghiệp (ẩn với sinh viên).
   - Yêu cầu sinh viên bổ sung thêm giấy tờ (chuyển sang `Cần bổ sung`).
   - Chuyển tiếp sang phòng ban khác nếu sai chuyên môn.
5. Cán bộ sử dụng Mẫu phản hồi có sẵn (Canned Response), đính kèm file kết quả và gửi phản hồi chính thức.
6. Cán bộ chuyển trạng thái Ticket sang `Hoàn thành`.

---

## 3. Đặc tả chi tiết các yêu cầu chức năng (Functional Specifications)

#### FR-11: Hàng đợi xử lý tập trung (Ticket Queue Management)

* **User Story:** Là một Cán bộ xử lý, tôi muốn có một giao diện hàng đợi tập trung hiển thị danh sách các Ticket cần xử lý để tôi dễ dàng quản lý và không bỏ sót công việc.
* **Đặc tả logic (Specifications):**
  * Danh sách phân chia theo các Tab nghiệp vụ rõ ràng:
    * *Ticket của tôi:* Các yêu cầu đang được phân công trực tiếp cho cá nhân cán bộ.
    * *Chưa phân công (Unassigned):* Các yêu cầu thuộc phòng ban của cán bộ nhưng chưa có người nhận xử lý.
    * *Tất cả Ticket phòng ban:* Toàn bộ yêu cầu thuộc phạm vi phòng ban quản lý.
  * Mỗi dòng hiển thị: Mã Ticket, Tiêu đề, Sinh viên, Trạng thái, Priority, Hạn xử lý (SLA Deadline).
  * Đánh dấu màu nổi bật cho Ticket sắp đến hạn (vàng) hoặc đã quá hạn xử lý (đỏ).
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-11.1 (Phân quyền dữ liệu phòng ban):** Cán bộ thuộc phòng ban nào chỉ nhìn thấy Ticket thuộc phòng ban đó; không nhìn thấy Ticket của phòng ban khác.
  * **AC-11.2 (Cảnh báo hạn xử lý trực quan):** Các Ticket có thời gian SLA còn lại $\le 25\%$ tự động đổi sang badge màu vàng; Ticket quá hạn hiển thị badge màu đỏ kèm số giờ quá hạn.

#### FR-12: Tự động phân luồng theo danh mục/phòng ban (Auto-Routing)

* **User Story:** Là một Cán bộ, tôi muốn hệ thống tự động chuyển Ticket mới về đúng phòng ban theo danh mục sinh viên đã chọn để giảm thiểu thao tác điều phối thủ công.
* **Đặc tả logic (Specifications):**
  * Khi sinh viên nộp Ticket thành công, hệ thống đọc cấu hình Routing Rules đang hoạt động:
    * Nhóm *Đào tạo* $\rightarrow$ Phòng Đào tạo.
    * Nhóm *Công tác sinh viên* $\rightarrow$ Phòng Công tác sinh viên (CTSV).
    * Nhóm *Kế toán/Tài chính* $\rightarrow$ Phòng Kế hoạch - Tài chính.
    * Nhóm *Khảo thí* $\rightarrow$ Phòng Khảo thí & Đảm bảo chất lượng.
  * Ticket tự động được gán vào hàng đợi chung của phòng ban tương ứng.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-12.1 (Phân luồng tức thì):** Ngay sau khi sinh viên tạo Ticket, Ticket xuất hiện ngay trong tab "Chưa phân công" của đúng phòng ban thụ lý.

#### FR-13: Tiếp nhận và phân công Ticket (Ticket Assignment & Self-Assign)

* **User Story:** Là một Cán bộ, tôi muốn chủ động nhận xử lý Ticket hoặc phân công cho đồng nghiệp trong phòng ban để phân định rõ trách nhiệm cá nhân.
* **Đặc tả logic (Specifications):**
  * Nút "Nhận xử lý" (Self-assign) cho phép cán bộ tự gán Ticket cho chính mình với 1 cú click.
  * Dropdown phân công hiển thị danh sách toàn bộ cán bộ trực thuộc cùng phòng ban.
  * Khi Ticket được gán người phụ trách, trạng thái Ticket tự động chuyển từ `Mới tạo` sang `Đang xử lý` (nếu đang ở trạng thái mới tạo).
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-13.1 (Tự nhận xử lý):** Cán bộ bấm "Nhận xử lý", trường Người phụ trách (Assignee) lập tức cập nhật tên cán bộ đó và ghi vết vào lịch sử Ticket.
  * **AC-13.2 (Phân công đồng nghiệp):** Cán bộ chọn tên đồng nghiệp trong dropdown và bấm lưu $\rightarrow$ hệ thống chuyển Ticket sang "Ticket của tôi" của cán bộ được gán và gửi thông báo In-app/Email cho người đó.

#### FR-14: Chuyển tiếp phòng ban & Chuyển cấp xử lý (Forward & Escalate)

* **User Story:** Là một Cán bộ, tôi muốn chuyển tiếp Ticket sang phòng ban khác hoặc chuyển cấp lên Quản lý khi nội dung yêu cầu thuộc thẩm quyền đơn vị khác hoặc vượt quá quyền hạn của tôi.
* **Đặc tả logic (Specifications):**
  * Chuyển tiếp phòng ban (Forward): Chọn phòng ban tiếp nhận mới từ danh sách, reset người phụ trách về Unassigned của phòng ban mới. Bắt buộc nhập lý do chuyển tiếp.
  * Chuyển cấp (Escalate): Gán trực tiếp Ticket lên tài khoản Quản lý (Trưởng phòng) của phòng ban để xin ý kiến chỉ đạo. Bắt buộc nhập lý do chuyển cấp.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-14.1 (Chuyển phòng ban hợp lệ):** Cán bộ chọn phòng ban mới, nhập lý do và bấm xác nhận $\rightarrow$ Ticket rời khỏi hàng đợi của phòng ban cũ và chuyển sang hàng đợi của phòng ban mới kèm log chuyển tiếp.
  * **AC-14.2 (Bắt buộc nhập lý do):** Nếu bỏ trống ô lý do chuyển tiếp/chuyển cấp, hệ thống chặn gửi và cảnh báo: "Vui lòng nhập lý do điều chuyển".

#### FR-15: Tìm kiếm, lọc và sắp xếp Ticket nâng cao (Search & Advanced Filter)

* **User Story:** Là một Cán bộ, tôi muốn lọc và sắp xếp danh sách Ticket theo nhiều tiêu chí nghiệp vụ để nhanh chóng tìm thấy các yêu cầu cần xử lý gấp.
* **Đặc tả logic (Specifications):**
  * Các tiêu chí lọc hỗ trợ: Trạng thái (Mới tạo, Đang xử lý, Cần bổ sung, Hoàn thành), Danh mục, Mức độ ưu tiên (Thấp, Trung bình, Cao, Khẩn cấp), Cán bộ phụ trách, Khoảng ngày tiếp nhận.
  * Sắp xếp theo: Hạn xử lý SLA (Gần nhất/Xa nhất), Ngày tạo (Mới nhất/Cũ nhất), Mức độ ưu tiên (Cao $\rightarrow$ Thấp).
  * Tìm kiếm tức thì theo mã định danh `AU-2026-XXXX`, tên sinh viên, mã số sinh viên (MSSV) hoặc từ khóa tiêu đề.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-15.1 (Tốc độ phản hồi tìm kiếm):** Kết quả tìm kiếm và áp dụng bộ lọc hiển thị chính xác trong thời gian $\le 1.0$ giây.
  * **AC-15.2 (Lưu trạng thái bộ lọc):** Khi cán bộ bấm vào xem chi tiết một Ticket và nhấn nút Quay lại, hệ thống giữ nguyên các điều kiện lọc và trang đang xem trước đó.

#### FR-16: Cập nhật trạng thái xử lý Ticket (Status Update)

* **User Story:** Là một Cán bộ, tôi muốn cập nhật trạng thái xử lý Ticket theo tiến độ thực tế để sinh viên và ban quản lý nắm bắt tình hình giải quyết.
* **Đặc tả logic (Specifications):**
  * Cán bộ có thể cập nhật trạng thái thông qua dropdown trên trang chi tiết Ticket.
  * Quy tắc chuyển đổi trạng thái (State Machine):
    * `Mới tạo` $\rightarrow$ `Đang xử lý`.
    * `Đang xử lý` $\rightarrow$ `Cần bổ sung` (khi cần sinh viên cung cấp thêm thông tin).
    * `Đang xử lý` $\rightarrow$ `Hoàn thành` (khi đã giải quyết xong).
  * Khi chuyển trạng thái sang `Hoàn thành`, hệ thống bắt buộc cán bộ phải gửi kèm nội dung giải quyết chính thức.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-16.1 (Chuyển trạng thái thành công):** Chọn trạng thái mới và bấm lưu $\rightarrow$ trạng thái cập nhật ngay lập tức, kích hoạt gửi email thông báo tương ứng cho sinh viên.
  * **AC-16.2 (Ràng buộc khi hoàn thành):** Nếu cán bộ chọn `Hoàn thành` nhưng chưa nhập nội dung phản hồi kết quả, hệ thống hiển thị thông báo lỗi yêu cầu nhập nội dung giải quyết trước khi đóng Ticket.

#### FR-17: Thiết lập và điều chỉnh mức độ ưu tiên (Priority Management)

* **User Story:** Là một Cán bộ, tôi muốn điều chỉnh mức độ ưu tiên của Ticket khi phát hiện vấn đề có tính cấp bách để điều chỉnh thời hạn giải quyết phù hợp.
* **Đặc tả logic (Specifications):**
  * 04 mức ưu tiên: `Thấp` (Low), `Trung bình` (Medium - Mặc định), `Cao` (High), `Khẩn cấp` (Urgent).
  * Khi thay đổi mức độ ưu tiên, hệ thống **tự động tính toán lại thời hạn xử lý (SLA Deadline)** của Ticket theo cấu hình tương ứng với mức ưu tiên mới.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-17.1 (Điều chỉnh Priority và cập nhật SLA):** Khi chuyển mức ưu tiên từ `Trung bình` sang `Khẩn cấp`, hệ thống rút ngắn hạn xử lý theo đúng cấu hình và hiển thị hạn chót mới ngay trên giao diện.

#### FR-18: Yêu cầu sinh viên bổ sung thông tin (Request Additional Information)

* **User Story:** Là một Cán bộ, tôi muốn gửi yêu cầu cho sinh viên bổ sung thông tin hoặc tài liệu còn thiếu để có đủ căn cứ giải quyết vấn đề.
* **Đặc tả logic (Specifications):**
  * Cán bộ nhập nội dung chi tiết cần bổ sung vào form "Yêu cầu bổ sung thông tin".
  * Khi nhấn gửi: Trạng thái Ticket tự động đổi sang `Cần bổ sung`.
  * Hệ thống tự động gửi email và thông báo In-app cho sinh viên kèm theo hướng dẫn của cán bộ.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-18.1 (Gửi yêu cầu bổ sung):** Ticket chuyển trạng thái sang `Cần bổ sung`, luồng tin nhắn hiển thị ghi chú yêu cầu bổ sung nổi bật và gửi email thông báo cho sinh viên trong vòng $\le 60$ giây.

#### FR-19: Thêm ghi chú nội bộ bảo mật (Internal Notes)

* **User Story:** Là một Cán bộ, tôi muốn ghi lại các trao đổi kỹ thuật hoặc ý kiến tham vấn với đồng nghiệp ngay trên Ticket mà không để sinh viên nhìn thấy.
* **Đặc tả logic (Specifications):**
  * Cung cấp Tab riêng biệt mang tên "Ghi chú nội bộ" trong khung trao đổi của Ticket.
  * Giao diện ghi chú có viền và màu nền phân biệt rõ (nền vàng nhạt) kèm nhãn "Chỉ nội bộ - Ẩn với sinh viên".
  * **Cơ chế bảo mật tuyệt đối:** Dữ liệu ghi chú nội bộ chỉ được gửi về Client khi người dùng đăng nhập có vai trò là *Cán bộ*, *Quản lý* hoặc *Quản trị viên*. Chặn hoàn toàn trường dữ liệu này ở API trả về cho vai trò *Sinh viên*.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-19.1 (Ghi chú nội bộ hiển thị với cán bộ):** Cán bộ nhập ghi chú và bấm lưu $\rightarrow$ ghi chú xuất hiện trên tab nội bộ với tên người ghi và thời gian.
  * **AC-19.2 (Ẩn hoàn toàn với sinh viên):** Khi đăng nhập tài khoản Sinh viên và mở cùng Ticket đó, sinh viên hoàn toàn không thấy tab hoặc bất kỳ nội dung nào của ghi chú nội bộ.

#### FR-20: Phản hồi chính thức cho sinh viên (Official Public Response)

* **User Story:** Là một Cán bộ, tôi muốn gửi câu trả lời chính thức kèm tài liệu đính kèm cho sinh viên để giải quyết dứt điểm yêu cầu hỗ trợ.
* **Đặc tả logic (Specifications):**
  * Cán bộ soạn nội dung phản hồi trong khung "Phản hồi chính thức".
  * Hỗ trợ đính kèm tối đa 03 tệp kết quả xử lý (ví dụ: file PDF giấy xác nhận, thông báo...).
  * Tin nhắn phản hồi được gửi vào luồng trao đổi công khai và kích hoạt thông báo qua email cho sinh viên.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-20.1 (Phản hồi thành công):** Nội dung phản hồi hiển thị trên trang của sinh viên, sinh viên có thể xem và tải các tệp đính kèm do cán bộ gửi về.

#### FR-21: Sử dụng mẫu phản hồi soạn sẵn (Canned Response Templates)

* **User Story:** Là một Cán bộ, tôi muốn chọn nhanh các câu trả lời mẫu cho các câu hỏi phổ biến để tiết kiệm thời gian soạn thảo và chuẩn hóa câu từ.
* **Đặc tả logic (Specifications):**
  * Nút "Chọn mẫu phản hồi" hiển thị ngay trong thanh công cụ của khung soạn thảo tin nhắn.
  * Cho phép tìm kiếm mẫu câu trả lời theo tên mẫu hoặc danh mục nghiệp vụ.
  * Tự động thay thế các biến thông tin (Placeholder) trong mẫu: `{ten_sinh_vien}` $\rightarrow$ Tên thật của SV, `{ma_ticket}` $\rightarrow$ Mã `AU-2026-XXXX`.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-21.1 (Điền nội dung mẫu tự động):** Khi cán bộ chọn một mẫu phản hồi, toàn bộ văn bản mẫu tự động điền vào khung soạn thảo kèm theo thông tin sinh viên đã được thay thế chính xác.

#### FR-22: Lưu nhật ký và lịch sử thao tác (Ticket Activity Log)

* **User Story:** Là một Cán bộ hoặc Quản lý, tôi muốn xem toàn bộ nhật ký thao tác trên Ticket để phục vụ kiểm soát chất lượng dịch vụ và truy vết khi có tranh chấp.
* **Đặc tả logic (Specifications):**
  * Hệ thống tự động ghi nhận không thể can thiệp (Immutable log) mọi thao tác: Tạo Ticket, Gán cán bộ, Đổi mức ưu tiên, Đổi trạng thái, Thêm ghi chú nội bộ, Gửi phản hồi, Điều chuyển phòng ban.
  * Cấu trúc mỗi bản ghi log: Thời gian (Timestamp chuẩn), Người thực hiện (Tên, Mã cán bộ), Hành động, Giá trị trước thay đổi $\rightarrow$ Giá trị sau thay đổi.
* **Tiêu chí chấp nhận (Acceptance Criteria):**
  * **AC-22.1 (Ghi log đầy đủ):** Tab "Nhật ký hoạt động" hiển thị toàn bộ chuỗi sự kiện theo thứ tự thời gian giảm dần, không có tùy chọn sửa hoặc xóa log đối với bất kỳ người dùng nào.

---

## 4. Yêu cầu phi chức năng phân hệ (Module NFR)
* **Bảo mật truy cập phòng ban:** Cán bộ chỉ có quyền truy xuất dữ liệu thuộc phạm vi phòng ban mình được phân bổ.
* **Hiệu năng hàng đợi:** Tải danh sách hàng đợi (Queue) gồm 100 Ticket $\le 1.0$ giây.
* **Tính toàn vẹn dữ liệu:** Toàn bộ lịch sử can thiệp Ticket (Activity Log) không thể bị chỉnh sửa hoặc xóa bởi bất kỳ người dùng nào.
