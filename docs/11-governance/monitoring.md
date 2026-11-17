# Giám sát dự án (Project Monitoring)

Tài liệu này quy định các chỉ số đo lường, cách thức trích xuất dữ liệu, cơ chế cảnh báo sớm (Đỏ/Vàng/Xanh) và quy trình leo thang (escalation) của dự án **UniSupport**.

---

## Chỉ số theo dõi (Monitoring Metrics)

Các chỉ số được theo dõi trực tiếp từ GitHub Project, Issue Tracker và kế hoạch WBS:

| Chỉ số | Lấy từ đâu (Bộ lọc / Nguồn) | Ngưỡng bình thường (Xanh) | Ngưỡng escalate (Vàng / Đỏ) | Escalate tới ai |
| --- | --- | --- | --- | --- |
| **Tiến độ task theo Milestone** | GitHub Issues:<br>`is:issue label:task milestone:"MS-xx | Tên mốc" is:open` | Tỷ lệ hoàn thành được đối chiếu phần phải xong tại ngày báo cáo theo WBS | **Vàng:** Effort đã xác nhận hoàn thành thấp hơn baseline tại ngày báo cáo.<br>**Đỏ:** Có nguy cơ trễ Milestone đã cam kết. | **Vàng:** PM điều phối nội bộ.<br>**Đỏ:** Báo cáo khẩn cấp Aurora University. |
| **Lỗi nghiêm trọng (Critical/High Bugs)** | GitHub Issues:<br>`is:issue label:bug label:critical is:open`<br>`is:issue label:bug label:high is:open` | 0 lỗi Critical/High mở tại thời điểm kiểm tra mốc | **Vàng:** Có 1–2 lỗi đang điều tra/sửa.<br>**Đỏ:** Còn lỗi Critical/High mở sát ngày kiểm tra mốc. | Technical Lead & QA Lead; chuyển cấp PM xử lý ưu tiên. |
| **Task bị chặn (Blockers)** | GitHub Issues:<br>`is:issue label:blocked is:open` | 0 task bị chặn trên đường găng (Critical Path) | **Vàng:** Bị chặn $< 24$h.<br>**Đỏ:** Bị chặn $> 24$h làm gián đoạn thành viên khác. | Technical Lead xử lý kỹ thuật; PM gỡ vướng mắc nghiệp vụ. |
| **Giờ công thực tế (Actual Hours)** | Comment ghi giờ công trên từng Issue so với WBS [master-plan.xlsx](../08-project/master-plan.xlsx) | Giờ thực tế nằm trong $\pm 10\%$ so với kế hoạch | **Vàng:** Vượt $10\%–20\%$ nhưng còn trong giờ dự phòng.<br>**Đỏ:** Vượt tổng hạn mức dự phòng. | Project Manager đánh giá và cân đối lại nguồn lực. |
| **Chỉ số EVM (SPI & CPI)** | Tính toán lũy kế cuối mỗi Milestone theo công thức EVM | $SPI \ge 1.0$, $CPI \ge 1.0$ | **Vàng:** $0.9 \le SPI, CPI < 1.0$.<br>**Đỏ:** $SPI < 0.9$ hoặc $CPI < 0.9$. | Project Manager lập phương án chấn chỉnh tiến độ/chi phí. |

---

## Chỉ số Giá trị Đạt được (EVM - Earned Value Management)

Cuối mỗi Milestone (MS-01 đến MS-08), PM tổng hợp 3 giá trị cơ sở (VNĐ):
- **PV (Planned Value):** Giá trị công việc dự kiến hoàn thành theo kế hoạch.
- **EV (Earned Value):** Giá trị công việc thực tế đã hoàn thành và nghiệm thu.
- **AC (Actual Cost):** Chi phí thực tế đã sử dụng.

| Chỉ số | Công thức | Ý nghĩa | Hành động khi $< 1$ |
| --- | --- | --- | --- |
| **SPI (Schedule Performance Index)** | $SPI = \frac{EV}{PV}$ | - $SPI > 1$: Nhanh hơn tiến độ<br>- $SPI = 1$: Đúng tiến độ<br>- $SPI < 1$: Chậm tiến độ | Rà soát các task bị chậm trên đường găng, tăng cường hỗ trợ hoặc điều chỉnh phân công. |
| **CPI (Cost Performance Index)** | $CPI = \frac{EV}{AC}$ | - $CPI > 1$: Tiết kiệm ngân sách<br>- $CPI = 1$: Đúng ngân sách<br>- $CPI < 1$: Vượt ngân sách | Phân tích nguyên nhân tiêu tốn giờ công, kiểm soát chặt chẽ các công việc còn lại. |

---

## Nhật ký quản trị (Governance Logs)

Project Manager duy trì 6 nhật ký quản trị trong suốt vòng đời 23 tuần:

1. **Decision Log:** Ghi nhận các quyết định quan trọng về kiến trúc, phạm vi, ngân sách và nhân sự (kèm người quyết định và ngày hiệu lực).
2. **Issue Log:** Ghi nhận các vấn đề, vướng mắc thực tế phát sinh cần xử lý (liên kết với GitHub Issues).
3. **Change Log:** Lưu quyết định từng CR trong Issue gốc và ghi thay đổi baseline đã duyệt tại sheet `Change Log` trong `master-plan.xlsx`.
4. **Risk Register:** Theo dõi 13 rủi ro chính và cập nhật định kỳ hằng tuần tại [08-project/risk-register.md](../08-project/risk-register.md).
5. **Assumption Log:** Ghi nhận và kiểm chứng các giả định dự án tại [08-project/assumptions.md](../08-project/assumptions.md).
6. **Lessons Learned Register:** Ghi nhận các bài học kinh nghiệm sau mỗi Milestone để tối ưu hóa quy trình làm việc.

Các ngưỡng là đề xuất quản trị Mô phỏng. Parent task lập kế hoạch giữ trạng thái open. Khi chưa có dữ liệu thực thi, báo cáo ghi Chưa đo và dùng ngày dự báo của công việc để đánh giá nguy cơ trễ mốc. EV chỉ ghi cho đầu ra được xác nhận theo tiêu chí, tránh đếm đồng thời parent và các việc con. PV/EV dùng cùng cơ sở ngân sách, AC lấy từ hồ sơ chi phí do người phụ trách quản lý. Khi PV hoặc AC bằng 0 hay chưa có dữ liệu, SPI/CPI ghi N/A kèm lý do.
