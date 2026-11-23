# Câu hỏi mở

PM theo dõi quyết định và bằng chứng trên Issue. Nếu quyết định làm thay đổi phạm vi, giá hoặc mốc đã cam kết, thực hiện [Change Request](../11-governance/change-control.md).

**Hai mức hạn.** *Hạn chốt* là ngày cam kết theo Proposal (A-06: quy tắc và ma trận quyền ổn định sau MS-01) hoặc theo kế hoạch. *Hạn muộn nhất* là ngày làm việc trước khi task phụ thuộc đầu tiên bắt đầu theo baseline 3.2.

**Escalate.** Quá *hạn chốt*: PM ghi vào mục Rủi ro và quyết định của báo cáo tuần, báo đại diện Aurora University và cập nhật rủi ro R-07. Quá *hạn muộn nhất*: task phụ thuộc gắn nhãn `blocked`, PM báo đại diện trường bằng văn bản trong 1 ngày làm việc và đánh giá đổi lịch theo Change Control. Chỉ số theo dõi tại [Monitoring](../11-governance/monitoring.md).

| Mã | Nội dung | Người chốt | Hạn chốt | Hạn muộn nhất và việc bị chặn | Trạng thái |
| --- | --- | --- | --- | --- | --- |
| `OQ-01` | Tài khoản GitHub nào tương ứng với từng thành viên đã ghi trong README? | Trưởng ban quản lý dự án | 09/10/2026 (WBS 1.1) | — | **Đã chốt** 23/11/2026. Ánh xạ tại bảng thành viên trong [README](../../README.md#thành-viên-nhóm-thực-hiện). |
| `OQ-02` | Ban quản lý chốt những điều khoản nào trong [Team Charter 2.4](team-charter.md#11-xác-nhận-và-duy-trì-charter)? | Ban quản lý dự án, ít nhất 3/4 thành viên | 27/11/2026 | 27/11/2026: quyền merge và reviewer độc lập cho PR từ MS-03 | Mở — chờ biểu quyết |
| `OQ-03` | Cửa sổ mở lại 72 giờ và trạng thái khi mở lại hoặc hết hạn ([BR-05](../02-domain/business-rules.md)). | Đại diện nghiệp vụ Aurora University; PM/BA chuẩn bị | 06/11/2026 (MS-01, A-06) | 25/12/2026: WBS 4.5 mở lại và CSAT (bắt đầu 28/12) | Mở — quá hạn chốt |
| `OQ-04` | Loại, số lượng và dung lượng tệp được phép ([BR-02](../02-domain/business-rules.md)). | Đại diện nghiệp vụ và CNTT Aurora University | 06/11/2026 (MS-01, A-06) | 27/11/2026: WBS 4.1 tạo Ticket kèm tệp (bắt đầu 30/11) | Mở — quá hạn chốt |
| `OQ-05` | SLA, lịch làm việc, tạm dừng khi chờ bổ sung và [phạm vi quyền và báo cáo](#phạm-vi-quyền-và-báo-cáo-oq-05) của bốn vai trò. | Đại diện nghiệp vụ Aurora University; PM/BA chuẩn bị Permission Matrix | 06/11/2026 (MS-01, A-06) | Quyền Ticket/tệp: 27/11/2026 (WBS 4.1). SLA và lịch làm việc: 31/12/2026 (WBS 5.3, bắt đầu 04/01/2027) | Mở — quá hạn chốt |
| `OQ-06` | Ngưỡng NFR, coverage, bộ dữ liệu thử, hạn xử lý lỗi và giới hạn Medium ([các mục cần xác nhận](../09-quality/quality-plan.md#xác-nhận-ngưỡng-chất-lượng-oq-06)). | QA và Tech Lead đề xuất; PM duyệt; đại diện trường xác nhận ngưỡng dùng để nghiệm thu | 06/11/2026 (MS-01, A-06) | Hạn lỗi và coverage: 27/11/2026 (cổng MS-02). Ngưỡng NFR: 15/01/2027 (WBS 6.3, bắt đầu 25/01/2027) | Mở — quá hạn chốt |
| `OQ-07` | Proposal v2.1 đã gửi và được xác nhận chưa? | PM | 28/09/2026 | — | **Đã chốt.** Gửi 14/09/2026, hai bên ký thỏa thuận 28/09/2026. Bằng chứng tại [Bản đã gửi khách](sent/README.md). |
| `OQ-08` | Áp dụng phương án phản hồi 3 ngày P-03 hay giữ baseline ([căn cứ](master-plan.md#xác-nhận-lịch-và-tác-động-thương-mại-oq-08)). | PM và đại diện có thẩm quyền Aurora University | 27/11/2026 (MS-02) | 27/11/2026: cửa sổ phản hồi MS-02 và WBS 4.1 (bắt đầu 30/11). Quá hạn thì giữ baseline 3.2. | Mở — chờ khách |
| `OQ-09` | Tham số BR-06 đến BR-10: chính sách mật khẩu, xác minh đặt lại, danh sách thao tác ghi nhật ký, giới hạn ghi chú nội bộ, chính sách gửi lại Email ([Business Rules](../02-domain/business-rules.md)). | Đại diện CNTT Aurora University; PM/BA chuẩn bị | BR-06, BR-07: 25/11/2026 | BR-06, BR-07: 25/11/2026 (WBS 3.4, cổng MS-02). BR-08 đến BR-10: 11/12/2026 (WBS 4.4–4.6, bắt đầu 14/12) | Mở — giá trị đề xuất đã ghi |

## Phạm vi quyền và báo cáo OQ-05

| Quyết định cần ghi vào Permission Matrix | Nguồn và ca đối chiếu |
| --- | --- |
| Quyền của Student theo chủ sở hữu, Staff/Manager theo phòng và ủy quyền, Administrator theo quyền quản trị và phạm vi dữ liệu được cấp. Ghi riêng quyền danh sách, chi tiết, thao tác, tệp và truy cập lại từ liên kết cũ. | [FR-AUTH-04](../03-modules/M01-auth-rbac/prd.md#fr-auth-04--kiểm-soát-quyền-truy-cập-dữ-liệu-và-tệp-đính-kèm), [M02](../03-modules/M02-student-portal/prd.md), TS-011/012/039/041 |
| Người được chuyển trực tiếp, quyền xem sự kiện/lý do và thời điểm thu hồi quyền phụ trách cũ. Ghi điều kiện giữ quyền độc lập và quyền xem ghi chú/tệp theo phòng tạo. | [FR-STF-04/06](../03-modules/M03-staff-desk/prd.md), [luồng chuyển phòng](../04-workflows/README.md), TS-051/052/057/058 |
| PM/BA chốt quyền tổng hợp toàn trường có mặc định cho mọi Administrator hay phải cấp riêng. Phương án đề xuất là cấp riêng. Ghi quyết định độc lập về quyền xuất CSV chi tiết cho từng vai trò. Ghi riêng quy tắc quy thuộc Ticket đã chuyển, thời điểm chốt số và cách dùng danh mục làm bộ lọc. | [FR-RPT-01/05](../03-modules/M05-dashboard-report/prd.md), TS-083/095, [#20](https://github.com/vinhdai123/UniSupport_Project/issues/20), [#76](https://github.com/vinhdai123/UniSupport_Project/issues/76) |

Dùng [bộ dữ liệu Ticket chuyển phòng](../06-acceptance/test-scenarios.md#dữ-liệu-dùng-chung) để ghi chính xác tập Ticket được xem, số đếm theo phòng và tập mã được xuất. Phương án dùng phòng đang phụ trách cho hàng đợi, Dashboard vận hành và CSV cùng nguồn đang chờ PM/BA xác nhận. Nếu báo cáo lịch sử dùng cách quy thuộc khác, ghi công thức, thời điểm và phạm vi xem/xuất tương ứng trước khi áp dụng.
