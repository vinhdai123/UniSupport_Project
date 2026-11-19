# Quản lý chất lượng UniSupport

UniSupport là dự án hỗ trợ sinh viên Aurora University trong tình huống **Mô phỏng**. Tài liệu này giải thích cách nhóm phòng ngừa sai lệch, kiểm sản phẩm và quyết định bàn giao. [Quality Plan trong repo](../09-quality/quality-plan.md) là nguồn tra DoD, thang lỗi, thời hạn và điều kiện phát hành.

## 1. Mục tiêu và tiêu chí

Mỗi lần bàn giao được đối chiếu với phạm vi trong [Proposal](../08-project/proposal.docx) và AC của [PRD M01–M05](../03-modules/README.md). QA dùng [RTM](../06-acceptance/traceability-matrix.md) để chọn ca và ghi bằng chứng theo phiên bản. Chất lượng chức năng và tích hợp được kiểm theo AC. Quyền, phiên và bảo vệ dữ liệu theo NFR-SEC-01, NFR-GLOBAL-01 và các ca quyền trong RTM. Hiệu năng theo NFR-PERF-01. VI/EN, Desktop/Mobile và khả năng sử dụng theo NFR-GLOBAL-02, NFR-GLOBAL-03 và NFR-GLOBAL-04. Ngưỡng và điều kiện đo tra tại [NFR](../05-non-functional-requirements/README.md).

## 2. Phòng ngừa sai lệch (QA)

PM/BA tổ chức review yêu cầu trước khi giao việc. Tech Lead kiểm tính khả thi, QA kiểm AC và ca lỗi, đại diện trường xác nhận nội dung nghiệp vụ ảnh hưởng cam kết. UI/UX dẫn walkthrough thiết kế trước khi làm giao diện, sau đó PM/BA ghi kết luận và các việc cần sửa. Người tham gia lưu phiên bản, nhận xét và quyết định vào Issue/PR. Developer mở PR kèm các kiểm tra đã thực hiện. Việc phê duyệt và merge theo [Team Charter](../08-project/team-charter.md), có reviewer độc lập.

## 3. Kiểm sản phẩm (QC)

Dev chạy unit test. Staging phục vụ tích hợp, quyền, đo theo NFR và UAT sau khi DevOps ghi cấu hình, Tech Lead xác nhận điều kiện kiểm và QA xác nhận dữ liệu giả lập đủ ca. Checklist đối chiếu build, schema, quyền, tệp, Email và giới hạn của phép đo. QA lưu mỗi test run với build, môi trường, mã ca, kết quả và Bug Issue liên quan. Mỗi lần gửi bản đều có kiểm phần mới, hồi quy phần đã giao chịu ảnh hưởng và kiểm lại lỗi đã sửa. QA cùng đại diện trường ghi kết quả UAT và phản hồi qua biên bản.

| Mốc trong Master Plan | Phạm vi kiểm và bằng chứng cần chuẩn bị |
| --- | --- |
| MS-01 | Đăng nhập tích hợp trên Staging. Kiểm tài khoản đúng/sai, kết thúc phiên và lưu test run cùng gói dùng thử. |
| MS-02 | Tài khoản, reset mật khẩu, vai trò và quyền chức năng đã có. Hồi quy đăng nhập và phiên. |
| MS-03 | Sinh viên gửi, tra cứu Ticket, dùng FAQ và tệp theo quyền. Hồi quy đăng nhập và kiểm dữ liệu chéo vai trò. |
| MS-04 | Vòng đời xử lý Ticket, phân công, SLA và thông báo. Hồi quy gửi/tra cứu, tệp và phân quyền. |
| MS-05 | Dashboard, CSV và NFR toàn cục. Lưu bằng chứng số liệu/CSV theo bộ lọc và quyền trước xác nhận. |
| MS-06 | E2E năm module, ngưỡng NFR và hồi quy bản tích hợp, gồm CSV. Lưu kết quả và danh sách lỗi. |
| MS-07 | UAT và chuẩn bị release. Hồi quy toàn bộ chức năng trên RC Staging, kiểm bản sửa và lưu biên bản UAT. |
| MS-08 | Smoke và hồi quy ca chính trên Production, lưu kết quả theo build, hồ sơ và biên bản bàn giao. |

Chi tiết từng mốc và bộ ca chính ở [Quality Plan](../09-quality/quality-plan.md#cổng-chất-lượng-theo-milestone) và [Kịch bản kiểm thử](../06-acceptance/test-scenarios.md).

## 4. Điều kiện hoàn thành và xử lý lỗi

Dùng [Definition of Done](../09-quality/quality-plan.md#definition-of-done-dod) để xác định task đã hoàn thành. DoD phân biệt công việc tài liệu và triển khai mô phỏng. Coverage 80% là đề xuất cho line coverage của logic lõi xác thực, phân luồng Ticket và tính SLA. Phạm vi đo, ngưỡng và hạn sửa lỗi chờ xác nhận tại [OQ-06](../08-project/open-questions.md).

QA ghi bug và đề xuất mức Severity theo ảnh hưởng. Tech Lead chốt mức và người sửa, PM chốt Priority và hạn. Developer liên kết bản sửa, QA chạy lại ca lỗi và hồi quy trước khi đóng. Bug chưa qua Verify vẫn mở. [Bảng mức độ và cách tính hạn](../09-quality/quality-plan.md#mức-độ-lỗi-và-cách-xử-lý) là nguồn áp dụng khi ghi hạn hoặc xử lý quá hạn.

## 5. Điều kiện bàn giao và phát hành

Bản giao sớm hoàn thành phạm vi của mốc. Bản cuối hoàn thành In-Scope M01–M05, có UAT xác nhận, kết quả kiểm Production và đủ hồ sơ chuyển giao. [Release Criteria](../09-quality/quality-plan.md#điều-kiện-release-release-criteria) quy định bằng chứng, người quyết định, mức lỗi và cách xét ngoại lệ.

- **MS-03 còn High trong phạm vi mốc:** QA lưu kết quả Fail và Bug, Tech Lead phân công sửa, PM hoãn trình xác nhận. QA xác minh bản sửa và hồi quy trước khi PM trình lại.
- **Production còn Medium có cách tạm:** QA kiểm cách tạm và điều kiện bắt buộc, Tech Lead xác nhận rủi ro, PM duyệt hoãn nếu đáp ứng quy tắc đã được nhóm chốt và có xác nhận của đại diện trường khi ảnh hưởng nghiệm thu. Ghi quyết định và hạn trong Issue, dẫn từ biên bản. Nếu thiếu điều kiện, PM giữ bàn giao ở trạng thái chờ.

PM ghi ngày khách nhận đủ hồ sơ, hạn phản hồi và quyết định bằng văn bản, tra sheet Nghiệm thu của [Master Plan](../08-project/master-plan.xlsx). Bảo hành kéo dài 30 ngày lịch từ ngày liền sau ký bàn giao theo Proposal. Vận hành hoặc hỗ trợ dài hạn theo thỏa thuận riêng.
