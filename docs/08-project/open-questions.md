# Câu hỏi mở

PM theo dõi quyết định và bằng chứng trên Issue. Nếu quyết định làm thay đổi phạm vi, giá hoặc mốc đã cam kết, thực hiện [Change Request](../11-governance/change-control.md).

| # | Nội dung | Ảnh hưởng | Trạng thái |
| --- | --- | --- | --- |
| 1 (`OQ-01`) | Tài khoản GitHub nào tương ứng với từng thành viên đã ghi trong README? | Ảnh hưởng việc gán Issue, review và truy vết trách nhiệm. | Chờ trưởng nhóm tổng hợp xác nhận từ từng thành viên. |
| 2 (`OQ-02`) | Nhóm chốt những điều khoản nào trong [Team Charter 2.4](team-charter.md#11-xác-nhận-và-duy-trì-charter)? | Ảnh hưởng bàn giao, xử lý bất đồng, reviewer độc lập và quyền merge. | Chờ trưởng nhóm ghi kết quả theo từng nhóm điều khoản, người xác nhận, ngày hiệu lực và liên kết biểu quyết. |
| 3 (`OQ-03`) | Chốt trạng thái khi mở lại hoặc đóng Ticket và xác nhận cửa sổ mở lại 72 giờ đang được xem xét thế nào? | Ảnh hưởng vòng đời Ticket, AC và test. | PM/BA chờ đối chiếu quyết định giữa Domain, PRD và AC. |
| 4 (`OQ-04`) | Loại, số lượng và dung lượng tệp nào được cho phép? | Ảnh hưởng lưu trữ, kiểm lỗi và nghiệm thu. | PM/BA chờ xác nhận rule và đối chiếu test. |
| 5 (`OQ-05`) | Chốt SLA, lịch làm việc và cách tạm dừng khi chờ bổ sung. Xác nhận [phạm vi quyền và báo cáo](#phạm-vi-quyền-và-báo-cáo-oq-05), gồm quyền của bốn vai trò, chuyển phòng, ghi chú/tệp, Dashboard và CSV. | Ảnh hưởng xử lý Ticket, báo cáo, nhắc hạn và các ca kiểm quyền. | **Chờ xác nhận.** PM/BA lưu phiên bản Permission Matrix, phạm vi được duyệt hoặc còn mở, người xác nhận, ngày hiệu lực, bằng chứng và kết quả đối chiếu AC/test. |
| 6 (`OQ-06`) | Nhóm xác nhận những ngưỡng NFR, phạm vi coverage, bộ dữ liệu thử, hạn xử lý lỗi và giới hạn Medium nào? Xem [các mục cần xác nhận](../09-quality/quality-plan.md#xác-nhận-ngưỡng-chất-lượng-oq-06). | Ảnh hưởng effort QA, điều kiện release và nghiệm thu. | Chờ QA và Tech Lead đối chiếu cách đo và khả dụng. PM ghi quyết định, người xác nhận và ngày áp dụng theo từng ngưỡng. |
| 7 (`OQ-07`) | Proposal đã duyệt được gửi khi nào và có bằng chứng nào? | Xác định lịch sử gửi và mốc bắt đầu áp dụng quy trình thay đổi sau khi khách nhận Proposal. | PM chờ xác nhận phiên bản, ngày gửi, người nhận và đúng PDF đã gửi tại [Bản đã gửi khách](sent/README.md). |
| 8 (`OQ-08`) | Chốt lịch áp dụng và điều kiện phản hồi với Aurora University. [Lịch ba ngày và bằng chứng cần có](master-plan.md#xác-nhận-lịch-và-tác-động-thương-mại-oq-08). | Baseline MS-08 là 12/03/2027. Phương án thương lượng dự kiến 19/04/2027, phụ thuộc lịch làm việc, khả dụng và chi phí. | Chờ quyết định thương mại nội bộ và xác nhận lịch bằng văn bản của Aurora University. |

## Phạm vi quyền và báo cáo OQ-05

| Quyết định cần ghi vào Permission Matrix | Nguồn và ca đối chiếu |
| --- | --- |
| Quyền của Student theo chủ sở hữu, Staff/Manager theo phòng và ủy quyền, Administrator theo quyền quản trị và phạm vi dữ liệu được cấp. Ghi riêng quyền danh sách, chi tiết, thao tác, tệp và truy cập lại từ liên kết cũ. | [FR-AUTH-04](../03-modules/M01-auth-rbac/prd.md#fr-auth-04--kiểm-soát-quyền-truy-cập-dữ-liệu-và-tệp-đính-kèm), [M02](../03-modules/M02-student-portal/prd.md), TS-011/012/039/041 |
| Người được chuyển trực tiếp, quyền xem sự kiện/lý do và thời điểm thu hồi quyền phụ trách cũ. Ghi điều kiện giữ quyền độc lập và quyền xem ghi chú/tệp theo phòng tạo. | [FR-STF-04/06](../03-modules/M03-staff-desk/prd.md), [luồng chuyển phòng](../04-workflows/README.md), TS-051/052/057/058 |
| PM/BA chốt quyền tổng hợp toàn trường có mặc định cho mọi Administrator hay phải cấp riêng. Phương án đề xuất là cấp riêng. Ghi quyết định độc lập về quyền xuất CSV chi tiết cho từng vai trò. Ghi riêng quy tắc quy thuộc Ticket đã chuyển, thời điểm chốt số và cách dùng danh mục làm bộ lọc. | [FR-RPT-01/05](../03-modules/M05-dashboard-report/prd.md), TS-083/095, [#20](https://github.com/vinhdai123/UniSupport_Project/issues/20), [#76](https://github.com/vinhdai123/UniSupport_Project/issues/76) |

Dùng [bộ dữ liệu Ticket chuyển phòng](../06-acceptance/test-scenarios.md#dữ-liệu-dùng-chung) để ghi chính xác tập Ticket được xem, số đếm theo phòng và tập mã được xuất. Phương án dùng phòng đang phụ trách cho hàng đợi, Dashboard vận hành và CSV cùng nguồn đang chờ PM/BA xác nhận. Nếu báo cáo lịch sử dùng cách quy thuộc khác, ghi công thức, thời điểm và phạm vi xem/xuất tương ứng trước khi áp dụng.
