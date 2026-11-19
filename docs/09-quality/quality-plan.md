# Kế hoạch chất lượng (Quality Plan)

UniSupport phục vụ Aurora University trong tình huống **Mô phỏng**. Kế hoạch này là nguồn tra Definition of Done, thang lỗi và điều kiện bàn giao. Phạm vi lấy từ [Proposal](../08-project/proposal.docx), yêu cầu kiểm từ [PRD M01–M05](../03-modules/README.md) và [NFR](../05-non-functional-requirements/README.md), lịch và effort từ [Master Plan](../08-project/master-plan.xlsx). Các hoạt động triển khai và bằng chứng dưới đây là kế hoạch thực hiện.

## QA (phòng ngừa)

| Hoạt động và thời điểm | Chủ trì và xác nhận | Bằng chứng cần lưu |
| --- | --- | --- |
| Review PRD trước khi chốt FR hoặc giao việc phát triển | PM/BA kiểm phạm vi và nguồn; Tech Lead kiểm khả thi, QA kiểm AC cho luồng chính, quy tắc và lỗi. PM/BA kết luận review kỹ thuật tài liệu sau khi nhận xét được xử lý. Nhóm lấy xác nhận của đại diện trường cho thay đổi nghiệp vụ hoặc tiêu chí cam kết. | Issue/PR gắn phiên bản PRD, FR/AC/NFR, nhận xét, quyết định nghiệp vụ và người xác nhận. |
| Review thiết kế trước khi triển khai UI hoặc tích hợp | UI/UX dẫn walkthrough theo các vai trò; PM/BA đối chiếu luồng, QA kiểm trạng thái, lỗi và thao tác; Tech Lead xác nhận khả thi và tích hợp. PM/BA ghi kết luận sau khi các nhận xét chặn được xử lý. | Link phiên bản Prototype, luồng/AC đã xem, nhận xét, quyết định và việc còn mở. |
| Review thay đổi trước merge | Tác giả chuẩn bị PR và bằng chứng kiểm; reviewer độc lập cho tài liệu, Technical Lead hoặc người thay thế theo Charter cho code. | PR ghi commit, Issue, các AC chịu ảnh hưởng, kiểm tra và phê duyệt phiên bản cuối. |
| Chuẩn bị trước mỗi MS | PM kiểm đầu ra, cửa sổ khách phản hồi và nguồn lực; QA lập danh sách test mới, hồi quy và kiểm lại lỗi; Tech Lead xác nhận bản ứng viên. | Danh sách ca theo RTM, lịch tại sheet Nghiệm thu, giờ theo Resources và các việc bị chặn. |

### Tiêu chuẩn Code Review

Áp dụng nhánh đích, người duyệt và người merge theo [Team Charter, mục 9](../08-project/team-charter.md#9-branch-pr-review-và-merge), gồm feature/bugfix, PR phát hành và hotfix. PR code đi qua review kỹ thuật độc lập trước khi merge. PR tài liệu áp dụng cơ chế reviewer độc lập của Charter. Sau thay đổi ảnh hưởng nội dung đã duyệt, reviewer kiểm lại phần thay đổi và bằng chứng của commit mới. Phân quyền repo và quy ước Charter áp dụng theo quyết định của nhóm.

## QC (kiểm tra)

QA và Dev thực hiện kiểm theo [Kịch bản kiểm thử](../06-acceptance/test-scenarios.md) và [RTM](../06-acceptance/traceability-matrix.md). Mỗi test run ghi mốc, build/commit, môi trường, bộ dữ liệu, mã AC/NFR và TS, kết quả, người kiểm và bằng chứng. Với ca Fail hoặc Blocked, ghi Bug hoặc Issue phụ thuộc. Kiểm ca lỗi và phần ảnh hưởng sau khi sửa, rồi lưu kết quả hồi quy theo phiên bản.

| Tiêu chí | Nguồn và phép kiểm |
| --- | --- |
| Chức năng và độ tin cậy luồng | PRD/RTM. Kiểm đầu vào, xử lý và lưu kết quả qua UI/API; chạy luồng xuyên module từ tạo Ticket đến xử lý và báo cáo. Kiểm tình huống lỗi Email tại TS-040 và lưu bằng chứng thử khôi phục theo WBS 8.4 trước triển khai. |
| Dữ liệu và quyền | NFR-GLOBAL-01, NFR-SEC-01; kiểm bộ dữ liệu giả lập, quyền chức năng, dữ liệu chéo vai trò/phòng ban, phiên và tệp. Dùng các ca liên quan trong RTM, ví dụ TS-009, TS-012 và TS-122. |
| Hiệu năng | NFR-PERF-01 và TS-121. Ghi tải, tập dữ liệu, môi trường, cách đo và ngưỡng đã xác nhận trước khi kết luận. |
| Tương thích | NFR-GLOBAL-03 và TS-106–TS-110, TS-119. Kiểm bố cục, điều hướng và cùng thao tác nghiệp vụ trên Desktop/Mobile theo ma trận thiết bị đã xác nhận. |
| Bản địa hóa | NFR-GLOBAL-02 và TS-102–TS-105, TS-118. Kiểm nhãn, thông báo và dữ liệu khi đổi VI/EN. |
| Khả năng sử dụng | NFR-GLOBAL-04 và TS-111–TS-116, TS-120. Kiểm thuật ngữ, phản hồi sau thao tác, validation, trạng thái và giao diện theo quyền. |

**Môi trường.** Dev chạy unit test và kiểm chức năng đơn lẻ. Trước khi mở test trên Staging, DevOps ghi checklist đối chiếu phiên bản ứng dụng, schema/migration, cấu hình quyền, lưu tệp, Email thử và các thành phần ảnh hưởng phép đo. Tech Lead xác nhận tương đương cho mục đích kiểm, QA ghi sai khác, giới hạn phép đo và các ca phải chờ. Chỉ kết luận NFR trên môi trường phù hợp với phép kiểm đã xác nhận. Dev, Test và Staging, kể cả UAT trên Staging, chỉ dùng dữ liệu giả lập theo NFR-GLOBAL-01. QA và DevOps đối chiếu nguồn bộ dữ liệu trước đợt kiểm và giữ bằng chứng ngưỡng 0 bản ghi thật; dữ liệu chưa xác minh bị loại khỏi đợt kiểm. QA chuẩn bị bốn nhóm vai trò, ít nhất hai phạm vi dữ liệu để kiểm chéo, Ticket có/không có tệp, đủ trạng thái và tình huống SLA theo kịch bản. Quy mô 50 Ticket là đề xuất cho bộ dữ liệu chức năng, quy mô đo tải theo NFR đã xác nhận.

### Cổng chất lượng theo milestone

Trước từng lần trình xác nhận, QA kiểm phạm vi mới, tích hợp liên quan, hồi quy phần đã giao bị ảnh hưởng và xác minh bản sửa. Với MS-01, kiểm lại luồng đăng nhập của bản tích hợp sau mỗi bản sửa và trước khi gửi khách. Áp dụng điều kiện lỗi và hồ sơ tại mục Release Criteria.

| Mốc | Kiểm phạm vi mới | Hồi quy và bằng chứng |
| --- | --- | --- |
| MS-01 | Đăng nhập xuyên suốt UI–API–dữ liệu trên Staging, từ chối thông tin sai, kết thúc phiên (WBS 3.6). | Test run đăng nhập/đăng xuất trên build tích hợp, kết quả kiểm bản sửa, URL và tài khoản thử để khách dùng tại WBS 3.9. |
| MS-02 | Quản trị tài khoản, gán vai trò, đặt lại mật khẩu và quyền chức năng đã có (WBS 3.5/3.7). | Hồi quy đăng nhập và phiên. Lưu kết quả theo bốn vai trò. Quyền Ticket/tệp đi cùng luồng tích hợp MS-03/MS-04. |
| MS-03 | Gửi, tra cứu Ticket, tệp và FAQ; đối chiếu phòng nhận được lưu từ ánh xạ danh mục tại TS-021 và kiểm giới hạn, quyền, truy cập chéo theo PRD (WBS 4.1–4.2). | Hồi quy đăng nhập và quyền MS-01/MS-02. Lưu test run và bằng chứng Ticket/tệp theo quyền. |
| MS-04 | Hàng đợi theo quyền, nhánh dự phòng thiếu quy tắc, phân công, xử lý, trả kết quả, mở lại, cấu hình SLA, quyền và Email/In-App (WBS 4.4/4.6/5.3). | Hồi quy gửi, tra cứu, tệp và quyền qua vòng đời Ticket. Lưu bằng chứng luồng liên vai trò, thông báo và xử lý sai khác. |
| MS-05 | Dashboard, CSV theo quyền, bộ lọc và đối chiếu số liệu; kiểm 19 AC NFR toàn cục (WBS 6.3/6.4). | Hồi quy luồng Ticket và quyền liên quan báo cáo. Lưu file CSV mẫu, bảng đối chiếu và kết quả RTM, gồm TS-095 trước xác nhận mốc. |
| MS-06 | E2E năm module trên một bản Staging, quyền và sáu phép kiểm ngưỡng NFR (WBS 7.2–7.4). | Hồi quy luồng đã giao, gồm CSV và bộ NFR toàn cục theo lịch test. Lưu kết quả E2E, dữ liệu đo và danh sách lỗi đã verify/còn mở. |
| MS-07 | Đại diện trường thực hiện UAT bốn vai trò. Kiểm tài liệu, đào tạo, sao lưu/khôi phục và điều kiện triển khai (WBS 8.3/8.4). | Hồi quy toàn bộ chức năng trên RC Staging và kiểm bản sửa UAT. Lưu hồ sơ RC, test run và biên bản UAT được xác nhận. |
| MS-08 | Kiểm phiên bản trên Production, smoke và bộ ca luồng chính theo lịch test; kiểm hồ sơ chuyển giao (WBS 9.2/9.3). | Lưu kết quả cho đúng phiên bản triển khai, xử lý hoặc khôi phục nếu kiểm thất bại, lưu biên bản bàn giao. Bảo hành bắt đầu từ ngày liền sau ngày ký theo Proposal. |

## Definition of Done (DoD)

**Tài liệu và kế hoạch.** Chủ tài liệu hoàn tất phạm vi Issue, kiểm nguồn và mã, đồng bộ tài liệu chịu ảnh hưởng và ghi các điểm còn mở. Reviewer độc lập xác nhận ở PR hoặc Issue sau khi nhận xét chặn được xử lý.

**Công việc thực thi Mô phỏng.** Hoàn thành AC của task; kiểm linter/CI và unit test phù hợp; có bằng chứng chức năng và hồi quy phần bị ảnh hưởng trên phiên bản kiểm thử; xử lý Critical/High liên quan; đồng bộ tài liệu thay đổi và có phê duyệt PR theo Charter. Developer gắn PR và QA xác nhận bằng chứng test trên Issue. Điều kiện của một bản giao được đánh giá riêng theo Release Criteria.

**Coverage đề xuất tại OQ-06.** Tối thiểu 80% line coverage bằng unit test trên tập file/hàm logic nghiệp vụ lõi của xác thực, phân luồng Ticket và tính SLA. Technical Lead chốt tập mã và cách đo, QA lưu báo cáo theo commit. Nhóm xác nhận phạm vi, cách đo và ngưỡng trước khi dùng làm điều kiện bắt buộc. Các ngưỡng NFR lấy từ PRD/NFR và quyết định được lưu, xem [OQ-06](../08-project/open-questions.md).

## Mức độ lỗi và cách xử lý

Severity phản ánh mức ảnh hưởng. Priority là thứ tự xử lý theo tác động, phụ thuộc và thời điểm bàn giao.

| Mức và nhãn | Cách phân loại | Hạn xử lý đề xuất |
| --- | --- | --- |
| Critical · `critical` | Mất/hỏng dữ liệu, lộ dữ liệu hoặc truy cập trái quyền, hoặc hệ thống/luồng cốt lõi dùng chung ngừng hoạt động trên bản đang kiểm. | Xác minh bản sửa trong 4 giờ làm việc. Báo và cô lập ngay khi phát hiện sự cố nghiêm trọng theo Reporting. |
| High · `high` | Một chức năng chính bị chặn cho vai trò hoặc nhóm nghiệp vụ, thiếu cách thay thế an toàn, tác động tới nghiệm thu; hệ thống còn hoạt động ở phạm vi khác. | Mặc định 12 giờ làm việc. Tech Lead có thể đề xuất tối đa 24 giờ làm việc khi có lý do kỹ thuật. PM xác nhận hạn và ghi tác động tới mốc trên Issue. |
| Medium · `medium` | Lỗi nghiệp vụ cục bộ có cách thao tác tạm an toàn và kiểm được, các điều kiện bắt buộc của bản giao vẫn đáp ứng. | 3 ngày làm việc; PM có thể chốt tối đa 5 ngày theo tác động, hoặc duyệt hoãn theo Release Criteria. |
| Low · `low` | Lỗi trình bày hoặc câu chữ, không thay đổi kết quả nghiệp vụ hay quyền. | PM xác nhận hạn theo backlog và ghi bản dự kiến xử lý. |

Các hạn trên là đề xuất thuộc [OQ-06](../08-project/open-questions.md). Đồng hồ bắt đầu tại thời điểm ghi nhận Issue, cộng theo khung giờ và lịch làm việc đã thống nhất (UTC+7); ngoài khung bắt đầu tính ở phiên làm việc kế tiếp. QA ghi giờ ghi nhận, Tech Lead ghi hạn cụ thể sau triage và giữ mốc bắt đầu khi đổi assignee hoặc severity. Hạn kết thúc tại thời điểm QA xác nhận Verify đạt, gồm cả hồi quy liên quan. Lỗi phải mở lại tiếp tục theo dõi từ mốc ghi nhận ban đầu. Nếu thiếu khả dụng hoặc vượt hạn, PM ghi quyết định điều phối/đổi lịch và bằng chứng trong Issue. Cảnh báo khẩn áp dụng ngay theo [Reporting](../11-governance/reporting.md).

1. **Record:** QA hoặc người phát hiện mở [Bug Issue](../../.github/ISSUE_TEMPLATE/2-bug.md), gắn build, môi trường, MS, FR/AC/TS, tái hiện, mong đợi, thực tế và bằng chứng.
2. **Classify / Assign:** QA đề xuất severity, Tech Lead chốt mức và phân công Developer, PM xác nhận priority và hạn. Mọi đổi severity cần Tech Lead ghi lý do và QA đối chiếu ảnh hưởng. PM tiếp nhận chuyển cấp nếu ảnh hưởng cam kết.
3. **Investigate / Resolve:** Developer ghi nguyên nhân, bản sửa và vùng ảnh hưởng; Tech Lead review PR. QA giữ Issue mở cho đến khi kiểm lại.
4. **Verify / Close:** QA chạy lại ca lỗi và ca hồi quy, lưu kết quả theo build, ghi thời điểm Verify và đóng Issue khi đạt. Nếu lỗi tái diễn, QA mở lại và thông báo Tech Lead. Lỗi được hoãn giữ trạng thái mở, có owner, hạn, cách tạm và bản ghi chấp thuận.

## Điều kiện release (Release Criteria)

| Loại bản giao | Điều kiện | Người xác nhận và bằng chứng |
| --- | --- | --- |
| MS-01–MS-06, bản dùng thử theo mốc | Đầu ra và AC/NFR thuộc phạm vi mốc có bằng chứng đạt. Hồi quy phần chịu ảnh hưởng và verify bản sửa hoàn tất. 0 Critical/High còn mở trong phạm vi bản giao và phần tích hợp phụ thuộc. | QA đề nghị cho trình dựa trên test run, Tech Lead xác nhận build, PM quyết định trình hoặc hoãn. Đại diện trường xác nhận mốc bằng văn bản theo Proposal. |
| MS-07, nghiệm thu UAT và sẵn sàng phát hành | RC đủ phạm vi UAT, hồi quy chức năng đầy đủ trên Staging, 0 Critical/High còn mở thuộc bản RC. Hồ sơ đào tạo, vận hành và khôi phục sẵn sàng. | QA và Tech Lead xác nhận RC và bằng chứng. Đại diện trường ký xác nhận UAT; PM ghi quyết định sẵn sàng triển khai. |
| MS-08, phát hành cuối và bàn giao | Toàn bộ In-Scope M01–M05 đạt các AC/NFR áp dụng và có UAT đã xác nhận. Sau triển khai, Production đạt smoke và bộ hồi quy luồng chính theo [lịch kiểm](../06-acceptance/test-scenarios.md#lịch-kiểm-tra-theo-phiên-bản). 0 Critical/High còn mở thuộc bản phát hành. Đủ mã nguồn, cấu hình, tài liệu và hồ sơ chuyển giao. | QA lưu kết quả theo build triển khai, Tech Lead xác nhận bản và khả năng khôi phục, PM quyết định trình ký. Đại diện trường ký bàn giao. Nếu Production fail, PM giữ bàn giao ở trạng thái chờ; Tech Lead và DevOps điều phối khôi phục hoặc sửa và kiểm lại. |

**Lỗi Medium/Low còn mở.** Chỉ trình ngoại lệ khi lỗi không làm trượt AC/NFR hoặc chặn luồng thuộc bản giao. QA kiểm cách thao tác tạm cho Medium và ghi bằng chứng, Tech Lead xác nhận rủi ro kỹ thuật, PM duyệt đề xuất hoãn và đại diện trường xác nhận bằng văn bản nếu lỗi ảnh hưởng phần khách sử dụng hoặc nghiệm thu. Lưu Bug ID, rủi ro, cách tạm, owner, hạn và xác nhận trong Issue và biên bản mốc. Với bản cuối, giới hạn đề xuất là dưới 5 lỗi Medium còn mở, tức tối đa 4. Nhóm phải chốt ngưỡng tại OQ-06 trước khi dùng. PM tạm hoãn duyệt ngoại lệ nếu chưa có quy tắc được xác nhận hoặc thiếu chấp thuận cần thiết.

Lịch gửi hồ sơ, hạn phản hồi và việc phụ thuộc tra sheet **Nghiệm thu**. PM ghi thời điểm khách nhận đủ hồ sơ, xử lý phản hồi theo mục 8 Proposal và lưu quyết định bằng văn bản. Nếu khách chưa xác nhận, công việc phụ thuộc tiếp tục chờ theo Master Plan. Bảo hành phần mềm 30 ngày lịch từ ngày liền sau ký bàn giao. Hỗ trợ vận hành lâu dài theo thỏa thuận riêng.

## Định mức QA trong kế hoạch

Tra **Resources** trong [Master Plan](../08-project/master-plan.xlsx) để kiểm effort theo từng mốc và vai trò, gồm 97 AC chức năng, 19 AC NFR toàn cục và 6 phép kiểm ngưỡng. Workload mô phỏng 287,75 giờ được so với 320 giờ QA triển khai, QA bảo hành có 24 giờ trong tổng 98 giờ bảo hành. Các giờ test và kiểm lại đã lập lịch nằm trong WBS và [Báo giá](../08-project/quotation.xlsx). Nếu phải thêm vòng kiểm hoặc giảm khả dụng, PM và QA dùng sheet **Kịch bản** để kiểm thiếu hụt trước khi đề xuất điều chuyển hoặc đổi lịch. Phần dự phòng CR theo Master Plan được xét riêng.
