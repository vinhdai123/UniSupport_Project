# Sổ rủi ro

Bảng tra theo sheet **Risk Register** trong [Master Plan](master-plan.xlsx). PM và owner rà soát hằng tuần và trước các mốc. Cập nhật điểm, trạng thái và dấu hiệu ở workbook trước khi đồng bộ bảng này. Chủ rủi ro và trạng thái thuộc tình huống **Mô phỏng**.

## Thang đánh giá

| Mức | Khả năng xảy ra trong thời gian dự án | Tác động nếu xảy ra |
| ---: | --- | --- |
| 1 | Hiếm, dưới 10% | Không đáng kể: xử lý trong tuần, không ảnh hưởng mốc hay giá |
| 2 | Thấp, 10–30% | Nhỏ: trễ một task tối đa 3 ngày làm việc, không ảnh hưởng mốc |
| 3 | Trung bình, 30–50% | Trung bình: trễ một mốc tối đa 1 tuần hoặc dùng tới 40 giờ dự phòng |
| 4 | Cao, 50–70% | Lớn: trễ mốc trên 1 tuần, ảnh hưởng đợt thanh toán hoặc dùng trên 40 giờ dự phòng |
| 5 | Rất cao, trên 70% | Nghiêm trọng: lộ hoặc mất dữ liệu, hay không Go-live được tại MS-08 |

**Điểm** = Khả năng × Tác động. **Ưu tiên:** từ 15 là Cao (theo dõi hằng tuần, nêu trong báo cáo tuần, ưu tiên dùng dự phòng CR.01); 8–14 là Trung bình (rà tại họp tuần); dưới 8 là Thấp (rà trước từng mốc).

## Ba rủi ro ưu tiên cao nhất

1. **R-07** (16): thông số nghiệp vụ chưa chốt. OQ-03 đến OQ-06 và OQ-09 vẫn mở sau mốc khóa PRD, nên AC, test và cổng chất lượng có thể chưa có giá trị khi kiểm.
2. **R-10** (16): khách phản hồi chậm hơn giả định. Phương án P-01 cho thấy hạn phản hồi 5 ngày làm WBS 4.1 vướng xác nhận MS-02.
3. **R-02** và **R-08** (15): sai quyền làm lộ dữ liệu; Production chưa sẵn sàng làm trễ Go-live. R-08 là rủi ro trực tiếp nhất với ngày MS-08.

## Sổ rủi ro

| Hạng | Mã | Mô tả | Khả năng | Tác động | Điểm | Ưu tiên | Hậu quả | Owner | Phương án xử lý | Trạng thái | Liên quan |
| ---: | --- | --- | ---: | ---: | ---: | --- | --- | --- | --- | --- | --- |
| 1 | `R-07` | Các thông số 72 giờ mở lại, số tệp hoặc ngưỡng test nguồn chưa được chốt. | 4 | 4 | 16 | Cao | Đội và khách hiểu khác tiêu chí, phát sinh làm lại. | PM / BA | Chốt thông số theo hạn tại câu hỏi mở (OQ-03 đến OQ-06, OQ-09); quá hạn thì escalate theo open-questions.md. Không dùng con số đề xuất làm cam kết khi chưa chốt. Cập nhật WBS, kịch bản và báo giá khi thay đổi phạm vi. | Mở — mô phỏng | 2.1, 4.1, 4.5 |
| 2 | `R-10` | Lịch nghỉ, lịch tham gia của trường hoặc phản hồi chậm hơn giả định. | 4 | 4 | 16 | Cao | Mốc phụ thuộc bị trễ dù tổng giờ nguồn lực vẫn đủ. | PM | Bổ sung lịch nghỉ và lịch đầu mối ngay khi có. Xác nhận đợt dùng thử, UAT, đào tạo; cập nhật ảnh hưởng và lịch sau quyết định được ghi nhận. | Mở — mô phỏng | A-03, A-07 Proposal, MS-01–MS-08 |
| 3 | `R-02` | Quyền truy cập Ticket, ghi chú nội bộ hoặc tệp đính kèm bị cấu hình sai. | 3 | 5 | 15 | Cao | Lộ dữ liệu hoặc chặn luồng sử dụng chính. | Tech Lead | Chốt ma trận quyền. Kiểm thử quyền theo vai trò ở 3.5 và từng module; chặn phát hành khi còn lỗi vi phạm quyền. | Mở — mô phỏng | 3.4, 3.5, 7.3 |
| 4 | `R-08` | Môi trường Production và quyền triển khai chưa sẵn sàng khi chuẩn bị phát hành. | 3 | 5 | 15 | Cao | Chậm UAT, Go-live hoặc bàn giao. | DevOps | Chốt bên cung cấp, cấu hình, chi phí và quyền trước triển khai. Kiểm sẵn sàng từ tuần 21, chuẩn bị runbook và khôi phục; báo PM khi thiếu điều kiện. | Mở — mô phỏng | 8.4, 9.1, MS-07 |
| 5 | `R-01` | Yêu cầu nghiệp vụ và quy tắc Ticket thay đổi sau khi khóa phạm vi. | 3 | 4 | 12 | Trung bình | Tăng effort, sửa thiết kế và trễ mốc. | PM / BA | Làm rõ PRD tại MS-01. Khi phát sinh, phân loại lỗi hoặc CR, tính tác động và chỉ triển khai sau xác nhận. | Mở — mô phỏng | 1.4, 2.1, 2.5, CR.01 |
| 6 | `R-12` | Mất dịch vụ hoặc dữ liệu do lỗi server, cấu hình hay triển khai. | 2 | 5 | 10 | Trung bình | Gián đoạn sử dụng, mất dữ liệu hoặc phải khôi phục phiên bản. | DevOps | Sao lưu, kiểm tra quyền và cấu hình, thử khôi phục trên môi trường mô phỏng trước MS-06/MS-08. Khi sự cố, cô lập lỗi, khôi phục và báo PM. | Mở — mô phỏng | 3.1, 7.3, 8.4, 9.1 |
| 7 | `R-03` | Dịch vụ Email không sẵn sàng hoặc thông báo chậm, trùng hoặc thất bại. | 3 | 3 | 9 | Trung bình | Sinh viên không nhận được cập nhật và phải hỏi lại. | DevOps | Xác nhận cấu hình sớm, kiểm luồng lỗi và ghi nhận gửi. Khi lỗi, xử lý cấu hình và thử lại trên dữ liệu giả lập trước bàn giao. | Mở — mô phỏng | 4.6, MS-04 |
| 8 | `R-05` | Thông tin phòng ban, phân quyền hoặc FAQ ban đầu thiếu và không nhất quán. | 3 | 3 | 9 | Trung bình | Chậm cấu hình, sai routing hoặc mất thời gian nghiệm thu. | PM / BA | Yêu cầu đầu mối xác nhận dữ liệu cấu hình trước công việc phụ thuộc. Dùng dữ liệu giả lập khi thử, theo dõi đầu vào thiếu và tác động lịch. | Mở — mô phỏng | 1.2, 2.1, 5.2 |
| 9 | `R-09` | Kiểm thử hồi quy hoặc sửa lỗi bị lấn bởi công việc phát triển. | 3 | 3 | 9 | Trung bình | Lỗi cũ quay lại và ảnh hưởng các lần bàn giao. | QA Tester | Giữ effort test/fix trong WBS và báo giá. Kiểm phiên bản, lỗi còn tồn và hồi quy trước từng MS; chưa trình bàn giao khi thiếu kiểm tra cần thiết. | Mở — mô phỏng | 3.5, 4.2, 4.6, 6.3, 7.4 |
| 10 | `R-04` | Tải đồng thời và dữ liệu thực tế khác giả định thiết kế. | 2 | 4 | 8 | Trung bình | Tra cứu, báo cáo hoặc thao tác Ticket chậm, ảnh hưởng nghiệm thu. | Tech Lead | Chốt tải và chỉ tiêu trong PRD tại MS-01. Chuẩn bị dữ liệu mô phỏng, kiểm hiệu năng và tối ưu trước MS-06; đánh giá CR nếu quy mô thay đổi. | Mở — mô phỏng | 2.1, 6.1, 7.2 |
| 11 | `R-06` | Nhân sự mô phỏng không huy động đủ hoặc tuần kín tải không còn khoảng trống. | 2 | 4 | 8 | Trung bình | Không giữ được lịch hoặc phải bổ sung kinh phí và nguồn lực. | PM | Kiểm bảng tải tuần, nghỉ phép và việc khác. Ưu tiên đầu ra, chia lại việc trong vai trò hoặc dùng dự phòng được duyệt; đánh giá CR nếu thiếu năng lực. | Mở — mô phỏng | Resources, CR.01 |
| 12 | `R-13` | Luồng đăng nhập, tài khoản thử hoặc Staging chậm sẵn sàng cho MS-01. | 2 | 4 | 8 | Trung bình | Khách thiếu bản dùng thử tuần 5 và phản hồi nghiệp vụ bị chậm. | PM / BA | Xác nhận luồng ưu tiên cuối tuần 2, dựng môi trường tuần 3, kiểm bản tích hợp cuối tuần 4. Theo dõi công việc 3.1–3.6 và điều phối sớm khi lệch lịch. | Mở — mô phỏng | 1.4, 3.1, 3.3, 3.6, MS-01 |
| 13 | `R-11` | 98 giờ dự trù bảo hành không đủ với lỗi phát sinh sau bàn giao. | 2 | 2 | 4 | Thấp | Tốn thêm nguồn lực để thực hiện nghĩa vụ bảo hành. | PM | Theo dõi lỗi và huy động phù hợp trong 30 ngày. Phân biệt lỗi trong phạm vi với chức năng mới; giờ dự trù không giới hạn nghĩa vụ bảo hành. | Mở — mô phỏng | BH.01, Proposal mục 8 |
