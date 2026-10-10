# Terminology – UniSupport

## 1. Tổng quan (Overview)

Tài liệu định nghĩa các thuật ngữ nghiệp vụ và khái niệm cốt lõi được sử dụng xuyên suốt hệ thống UniSupport.

Mục tiêu:

- Thống nhất cách sử dụng thuật ngữ giữa các tài liệu.
- Giúp các thành viên dự án hiểu đúng các khái niệm nghiệp vụ.
- Hạn chế sự nhầm lẫn trong quá trình phân tích, thiết kế, phát triển và kiểm thử.

## 2. Thuật ngữ nghiệp vụ (Business Terminology)

| Thuật ngữ | Viết tắt | Định nghĩa |
|---|---|---|
| Ticket | — | Phiếu yêu cầu hỗ trợ do sinh viên tạo trên hệ thống, chứa nội dung cần được phòng ban xử lý. |
| Ticket ID | — | Mã định danh duy nhất được hệ thống tự động cấp khi Ticket được tạo thành công. |
| Ticket Status | — | Trạng thái thể hiện tiến độ xử lý của Ticket. |
| Ticket Priority | Priority | Mức độ ưu tiên của Ticket, được sử dụng để hỗ trợ sắp xếp và quản lý công việc. |
| Routing Rule | — | Quy tắc phân luồng được cấu hình để tự động chuyển Ticket đến phòng ban phù hợp dựa trên danh mục yêu cầu. |
| Assignment | — | Hoạt động phân công Ticket cho cán bộ chịu trách nhiệm xử lý. |
| Transfer | — | Hoạt động chuyển Ticket sang cán bộ hoặc phòng ban khác có thẩm quyền xử lý. |
| Escalation | — | Hoạt động chuyển cấp Ticket đến cấp có thẩm quyền phù hợp khi cần hỗ trợ hoặc giải quyết vấn đề phát sinh. |
| Processing Deadline | — | Thời hạn xử lý được thiết lập cho Ticket dựa trên loại yêu cầu hoặc mức độ ưu tiên. |
| Deadline Alert | — | Cảnh báo được hệ thống đưa ra khi Ticket sắp đến hạn hoặc quá hạn xử lý. |
| Workload | — | Khối lượng công việc của cán bộ hoặc phòng ban, được thể hiện thông qua số lượng Ticket đang phụ trách. |
| Backlog | — | Các Ticket chưa được hoàn thành tại thời điểm thống kê. |
| Internal Note | — | Ghi chú nội bộ trong Ticket phục vụ quá trình xử lý, không hiển thị cho sinh viên. |
| Canned Response | — | Mẫu phản hồi có sẵn giúp cán bộ trả lời các yêu cầu thường gặp một cách nhất quán. |
| Attachment | — | Tài liệu hoặc hình ảnh được đính kèm vào Ticket. |
| Ticket History | — | Lịch sử các thao tác, cập nhật và thay đổi trạng thái trong quá trình xử lý Ticket. |
| Reopen Ticket | — | Hoạt động mở lại Ticket đã hoàn thành trong thời gian cho phép. |
| FAQ | Frequently Asked Questions | Danh sách câu hỏi thường gặp và hướng dẫn hỗ trợ sinh viên. |
| Knowledge Base | KB | Kho thông tin và hướng dẫn hỗ trợ được nhà trường quản lý. |

## 3. Thuật ngữ trạng thái Ticket (Ticket States)

| Trạng thái | Mã | Định nghĩa |
|---|---|---|
| Mới tạo | New | Ticket được tạo thành công và đang chờ tiếp nhận hoặc xử lý. |
| Đang xử lý | In Progress | Ticket đang được cán bộ tiếp nhận và xử lý. |
| Cần bổ sung | Pending | Ticket đang chờ sinh viên cung cấp thêm thông tin hoặc tài liệu. |
| Hoàn thành | Resolved | Ticket đã được xử lý và có kết quả giải quyết. |

Các trạng thái và quy tắc chuyển đổi được mô tả chi tiết trong `state-transition.md`.

## 4. Thuật ngữ báo cáo và thống kê (Reporting Terminology)

| Thuật ngữ | Viết tắt | Định nghĩa |
|---|---|---|
| Dashboard | — | Giao diện tổng hợp các chỉ số và thông tin về hoạt động xử lý Ticket. |
| Ticket Completion Rate | — | Tỷ lệ Ticket đã hoàn thành trong phạm vi thống kê được xác định. |
| Average Resolution Time | — | Thời gian xử lý hoàn thành Ticket trung bình trong phạm vi thống kê. |
| Ticket Backlog | — | Số lượng Ticket chưa hoàn thành tại thời điểm thống kê. |
| Customer Satisfaction | CSAT | Chỉ số phản ánh mức độ hài lòng của sinh viên thông qua đánh giá sau khi Ticket hoàn thành. |
| Ticket Trend | — | Xu hướng thay đổi số lượng Ticket theo thời gian. |
| Staff Performance | — | Thông tin thống kê về hoạt động và kết quả xử lý Ticket của cán bộ. |
| Department Performance | — | Thông tin thống kê về hoạt động và kết quả xử lý Ticket của phòng ban. |
| CSV Export | CSV | Chức năng xuất dữ liệu báo cáo dưới định dạng Comma-Separated Values. |

## 5. Thuật ngữ người dùng và phân quyền (Roles & Access)

| Thuật ngữ | Viết tắt | Định nghĩa |
|---|---|---|
| Student | — | Sinh viên sử dụng hệ thống để gửi và theo dõi yêu cầu hỗ trợ. |
| Staff | — | Cán bộ chịu trách nhiệm tiếp nhận, xử lý và phản hồi Ticket. |
| Manager | — | Người quản lý giám sát công việc và điều phối Ticket trong phạm vi phòng ban. |
| Administrator | Admin | Người quản trị tài khoản, phân quyền và cấu hình hệ thống. |
| Role-Based Access Control | RBAC | Cơ chế kiểm soát quyền truy cập chức năng và dữ liệu dựa trên vai trò người dùng. |
| Authentication | Auth | Quá trình xác thực người dùng khi đăng nhập vào hệ thống. |
| Authorization | — | Quá trình xác định quyền truy cập chức năng hoặc dữ liệu của người dùng. |
| Audit Log | — | Thông tin ghi nhận các thao tác quan trọng trên hệ thống phục vụ theo dõi và kiểm tra. |

## 6. Nguyên tắc sử dụng thuật ngữ

- Sử dụng thống nhất các thuật ngữ được định nghĩa trong tài liệu.
- Giữ nguyên 04 trạng thái Ticket chính theo Proposal.
- Sử dụng thuật ngữ **Processing Deadline – Thời hạn xử lý** khi mô tả thời hạn hoàn thành Ticket.
- Không tự xác định thời gian xử lý cụ thể nếu chưa được thống nhất.
- Các công thức tính chỉ số thống kê được mô tả trong tài liệu yêu cầu của Module Dashboard & Report.
- Khi bổ sung thuật ngữ mới, cần cập nhật tài liệu này để đảm bảo thống nhất giữa các module.

## 7. Tài liệu liên quan

- `../01-product/product-overview.md` – Tổng quan sản phẩm.
- `../01-product/product-scope.md` – Phạm vi sản phẩm.
- `../01-product/actors-and-roles.md` – Vai trò người dùng.
- `business-rules.md` – Quy tắc nghiệp vụ.
- `state-transition.md` – Chuyển đổi trạng thái Ticket.
- `../03-modules/` – Đặc tả yêu cầu chức năng.