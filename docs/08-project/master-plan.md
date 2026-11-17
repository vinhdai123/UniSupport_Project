# Master Plan UniSupport

Kế hoạch Mô phỏng gồm 23 tuần triển khai và 30 ngày bảo hành. Workbook [master-plan.xlsx](master-plan.xlsx) quản lý ngày, effort, capacity và phiên bản. Tám mốc dưới đây dùng cùng mã với Proposal và GitHub.

| Mốc | Tuần | Ngày dự kiến | Phần mềm khách tự dùng thử | Điều kiện kiểm |
| --- | ---: | --- | --- | --- |
| MS-01 | 5 | 06/11/2026 | Client mở URL Staging, dùng tài khoản hợp lệ để đăng nhập, thử thông tin sai và kết thúc phiên. | Màn hình, API và dữ liệu xác thực hoạt động cùng nhau. Tài khoản sai bị từ chối, tài khoản hợp lệ vào đúng trang, phiên kết thúc không còn truy cập được. |
| MS-02 | 8 | 27/11/2026 | Client dùng vai quản trị tạo/cập nhật tài khoản, gán vai trò, đặt lại mật khẩu và thử truy cập được phép/bị chặn. | Tài khoản, vai trò, reset mật khẩu và quyền chức năng đã có hoạt động đúng. Quyền Ticket/tệp kiểm tại MS-03/MS-04. |
| MS-03 | 10 | 11/12/2026 | Client đăng nhập vai sinh viên, gửi Ticket có tệp, nhận mã, mở lại trang tra cứu và xem FAQ. | Ticket và tệp được lưu, được tra cứu theo quyền và quy tắc PRD. Hồi quy đăng nhập và quyền trước bàn giao. |
| MS-04 | 15 | 15/01/2027 | Client dùng vai cán bộ phân công/xử lý, yêu cầu bổ sung, trả kết quả. Vai sinh viên kiểm thông báo và mở lại, vai quản lý kiểm workload/cấu hình. | Vòng đời Ticket, ghi chú nội bộ, Email/In-App và cảnh báo theo quy tắc PRD. Quyền dữ liệu được bảo vệ, hồi quy luồng đã giao. |
| MS-05 | 18 | 05/02/2027 | Client xem/lọc báo cáo, đối chiếu số liệu với bộ dữ liệu giả lập và tải CSV theo quyền. | Số liệu màn hình/CSV khớp dữ liệu chuẩn bị, quyền và bộ lọc. Kiểm VI/EN, responsive và hồi quy Ticket. |
| MS-06 | 20 | 19/02/2027 | Client chạy toàn bộ luồng từ đăng nhập, gửi/xử lý Ticket đến nhận kết quả và xem báo cáo trên cùng bản tích hợp. | Đối chiếu PRD, hồ sơ kiểm thử và lỗi còn tồn. Khắc phục lỗi chặn luồng chính hoặc vi phạm quyền, lỗi khác theo tiêu chí đã thống nhất. |
| MS-07 | 22 | 05/03/2027 | Đại diện trường chạy UAT bằng bốn vai trò, kiểm bản sửa phản hồi và thử hướng dẫn sử dụng trên bản phát hành. | Xác nhận kết quả UAT, hồi quy bản sửa, tài liệu và đào tạo, lịch triển khai, sao lưu/khôi phục và quyền truy cập cần thiết. |
| MS-08 | 23 | 12/03/2027 | Client dùng hệ thống Production, thử luồng chính theo quyền và tiếp nhận mã nguồn, cấu hình, tài liệu vận hành. | Smoke và hồi quy luồng chính Production có hồ sơ theo phiên bản, xác nhận bàn giao và bắt đầu bảo hành 30 ngày. |

## Cơ sở chia mốc

MS-01 có luồng đăng nhập UI–API–DB trên Staging. WBS 3.1–3.3 chuẩn bị môi trường và phát triển trong tuần 3–4, 3.6 tích hợp và hồi quy trước cuối tuần 4, 3.9 dành tuần 5 cho khách dùng thử. PRD, thiết kế và Prototype đi cùng phiên bản đăng nhập.

MS-02 bổ sung tài khoản và quyền. MS-03 giao gửi/tra cứu Ticket và FAQ. MS-04 tích hợp xử lý, bổ sung, trả kết quả và quản trị. MS-05 có Dashboard và CSV. MS-06 kiểm toàn bộ bản tích hợp, MS-07 xác nhận bản sẵn sàng phát hành, MS-08 bàn giao Production.

## Nguồn lực và kiểm soát chất lượng

Resources đối chiếu 3.000 giờ triển khai và 98 giờ bảo hành với báo giá. 152 giờ dự phòng được tách riêng, cần nhóm xác nhận huy động. Chín vai trò là Mô phỏng. Trần 40 giờ/người/tuần và lịch nghỉ được xác nhận trước khi cam kết khả dụng. QA được phân bổ theo bảng tuần và công việc.

WBS 3.6, 3.5, 4.2, 4.6, 6.3–6.4, 7.4, 8.4 và 9.2 dành giờ tích hợp, sửa lỗi hoặc hồi quy trước các mốc tương ứng. Các mốc phụ thuộc đầu vào và bản tích hợp đã nêu trong WBS. PM kiểm việc phụ thuộc và capacity khi thay đổi ngày.

## Feedback và thay đổi

PM gửi phiên bản, kịch bản và quyền dùng thử. Khách phản hồi theo điều kiện nghiệm thu mục 8 Proposal, dự kiến trong 5 ngày làm việc từ khi nhận đủ hồ sơ. Các giá trị là kế hoạch Mô phỏng.

CR được đánh giá và xác nhận theo [quy trình thay đổi](../11-governance/change-control.md). Lưu bản trước, thêm Change Log rồi cập nhật PRD, báo giá, WBS, Resources, test và GitHub. Gantt vẽ từ ngày bằng công thức.

Lịch gốc bắt đầu 05/10/2026. Tại ngày rà soát 17/11/2026, MS-01 đã có ngày baseline trong quá khứ. Đây là kế hoạch Mô phỏng, PM xác nhận tình huống hoặc tái lập lịch có Change Log trước khi sử dụng làm lịch triển khai thực tế.

Parent task [#101](https://github.com/vinhdai123/UniSupport_Project/issues/101) theo dõi bản đăng nhập đầu tiên. MS-02 kiểm quyền tài khoản và chức năng đã hiện diện. Quyền Ticket và tệp được kiểm khi các luồng xuất hiện tại MS-03/MS-04, với đợt hồi quy đầy đủ theo [#59](https://github.com/vinhdai123/UniSupport_Project/issues/59).

## Đồng bộ phiên bản 2.1

Mô hình QA ở Resources từ dòng 704 có định mức soạn ca, thực thi, hồi quy, đo NFR, triage, hỗ trợ UAT và smoke. Nhu cầu Mô phỏng 287,75 giờ được đối chiếu với 320 giờ QA triển khai ở từng mốc. 22 giờ QA được điều chuyển giữa Q-03/Q-04 và Q-09/Q-10. Lịch UAT có 50 giờ QA trong tuần 21–22, Production có 12 giờ QA cho smoke và 12 ca luồng chính. Bảo hành có 24 giờ QA trong tổng dự trù 98 giờ.

Định mức QA là giả định cần nhóm xác nhận khi có số liệu thử. Khoảng giờ QA còn trong ngân sách triển khai được theo dõi riêng với 152 giờ dự phòng CR/rủi ro. Ngày bảo hành trên WBS bắt đầu từ ngày liền sau ký nghiệm thu và bàn giao, thời hạn 30 ngày lịch.
