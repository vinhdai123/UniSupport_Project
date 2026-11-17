# Kế hoạch chất lượng (Quality Plan)

Tài liệu này xác định các tiêu chí, quy trình và hoạt động nhằm đảm bảo hệ thống **UniSupport - Student Support Management System** đáp ứng đúng yêu cầu đã thống nhất, hoạt động ổn định và tin cậy tại Aurora University.

---

## QA (phòng ngừa)

Hoạt động Đảm bảo chất lượng (QA) tập trung vào việc phòng ngừa lỗi và sai lệch ngay từ đầu:

1. **Rà soát yêu cầu (Requirement Review):**
   - Đánh giá tính rõ ràng, khả thi, đầy đủ và nhất quán của PRD trước khi phân công phát triển.
   - Thống nhất các quy tắc nghiệp vụ (Business Rules) và tiêu chí nghiệm thu (Acceptance Criteria) với đại diện Aurora University.
2. **Rà soát thiết kế (Design Review):**
   - Usability Walkthrough trên Figma Prototype nhằm phát hiện sớm các bất cập về trải nghiệm người dùng (UX) trước khi cắt mã giao diện.
3. **Tiêu chuẩn Code Review & Kiểm soát nhánh:**
   - 100% Pull Request từ Developer bắt buộc phải có sự review và phê duyệt của Technical Lead trước khi merge vào nhánh chính.
   - Không commit code trực tiếp vào nhánh chính (`main`/`master`).
4. **Cổng kiểm soát chất lượng theo Milestone (Milestone Quality Gates):**
   - **M1 Gate (Tuần 5):** Khóa PRD, kiến trúc và Prototype. Yêu cầu 0 lỗi Critical/High trong đặc tả.
   - **M2 Gate (Tuần 19-20):** Hoàn thành Integration Test toàn bộ 5 phân hệ M01–M05; Unit Test đạt tối thiểu 80% Code Coverage cho các logic nghiệp vụ cốt lõi (Auth, Ticket Routing, SLA calculation).
   - **M3 Gate (Tuần 21-22):** Nghiệm thu UAT đạt yêu cầu với sự xác nhận của Aurora University; 0 lỗi Critical/High tồn đọng.
   - **M4 Gate (Tuần 23):** Final Smoke Test trên môi trường Production thành công; hoàn tất hồ sơ bàn giao và kích hoạt bảo hành.

---

## QC (kiểm tra)

Hoạt động Kiểm soát chất lượng (QC) tập trung vào việc kiểm thử thực tế sản phẩm để phát hiện và xử lý lỗi:

1. **Các loại kiểm thử:**
   - **Functional Testing:** QA kiểm tra hoạt động từng chức năng theo các kịch bản kiểm thử [06-acceptance/test-scenarios.md](../06-acceptance/test-scenarios.md).
   - **Integration Testing:** Kiểm tra tính liên thông giữa các module (ví dụ: tạo Ticket ở M02 tự động xuất hiện trong Queue của M03).
   - **Security & RBAC Testing:** Kiểm tra phân quyền truy cập, xác thực JWT, ngăn chặn truy cập trái phép hoặc xem chéo dữ liệu phòng ban khác.
   - **Regression Testing:** Chạy lại toàn bộ bộ test kiểm tra hồi quy trước mỗi mốc bàn giao để đảm bảo code mới không làm hỏng tính năng cũ.
   - **User Acceptance Testing (UAT):** Đại diện sinh viên và cán bộ Aurora University trực tiếp thao tác nghiệm thu trên môi trường Staging.
2. **Môi trường và Dữ liệu kiểm thử:**
   - **Dev Environment:** Dùng cho lập trình viên chạy Unit Test.
   - **Staging Environment:** Cấu hình tương đương 99% môi trường Production, dùng cho Integration Test, Security Test và UAT.
   - **Quy định Mock Data:** Tuyệt đối không dùng dữ liệu thật của 3.000 sinh viên. Đội QA khởi tạo bộ Mock Data chuẩn trên Staging gồm 4 nhóm tài khoản mẫu (Student, Staff, Manager, Admin) và 50 Ticket bao phủ đầy đủ các trạng thái, Category và SLA.

---

## Definition of Done (DoD)

Một công việc/tính năng chỉ được xem là hoàn thành (Done) khi đáp ứng toàn bộ các tiêu chí:

- [ ] Mã nguồn được viết theo coding standard và vượt qua kiểm tra tĩnh (linter).
- [ ] 100% tiêu chí nghiệm thu (Acceptance Criteria - AC) trong PRD tương ứng được đáp ứng.
- [ ] Unit Test đạt tối thiểu 80% coverage cho các hàm logic nghiệp vụ.
- [ ] Pull Request được Technical Lead review và phê duyệt.
- [ ] Đã kiểm thử chức năng trên môi trường Staging và đạt kết quả mong đợi.
- [ ] Không có lỗi Critical hoặc High còn mở liên quan đến tính năng đó.
- [ ] Tài liệu kỹ thuật, hướng dẫn hoặc API docs liên quan đã được cập nhật đồng bộ.

---

## Mức độ lỗi và cách xử lý

| Mức độ | Định nghĩa | Thời hạn xử lý | Ai quyết định |
| --- | --- | --- | --- |
| **Critical** | Hệ thống ngừng hoạt động, mất dữ liệu, lỗ hổng bảo mật nghiêm trọng hoặc chặn hoàn toàn luồng chính | Trong vòng 4 giờ | Tech Lead & PM |
| **High** | Chức năng chính bị lỗi, không có phương án thay thế, vi phạm cam kết SLA | Trong vòng 12–24 giờ | Tech Lead |
| **Medium** | Chức năng bị lỗi nhưng vẫn có phương án thao tác thay thế tạm thời | Trong Sprint hiện tại (3–5 ngày) | Developer được gán |
| **Low** | Lỗi hiển thị nhỏ, chính tả giao diện, ít ảnh hưởng trải nghiệm | Xếp vào Backlog đợt sau | Developer được gán |

### Quy trình xử lý lỗi:
`Record (Ghi nhận)` ➔ `Classify (Phân loại)` ➔ `Assign (Phân công)` ➔ `Investigate (Điều tra)` ➔ `Resolve (Khắc phục)` ➔ `Verify (Kiểm tra lại)` ➔ `Close (Đóng lỗi)`

---

## Điều kiện release (Release Criteria)

Hệ thống UniSupport chỉ được phép bàn giao nghiệm thu và đưa vào sử dụng chính thức khi thỏa mãn:

1. 100% các chức năng In-Scope thuộc 5 module M01–M05 đã được triển khai hoàn tất.
2. 100% kịch bản kiểm thử chấp nhận (Acceptance Test Scenarios) và bộ Regression Test đều đạt kết quả PASS.
3. 0 lỗi Critical và 0 lỗi High còn tồn đọng chưa được giải quyết.
4. Tỷ lệ lỗi Medium còn mở dưới 5 lỗi (và các lỗi này phải có phương án khắc phục tạm thời được chấp thuận).
5. Đại diện Aurora University ký biên bản nghiệm thu UAT chính thức.
6. Bộ tài liệu chuyển giao, tài liệu hướng dẫn sử dụng và thông tin quản trị đã bàn giao đầy đủ.

---

## Áp dụng quy trình

- **Công cụ ghi nhận lỗi:** Sử dụng GitHub Issues với mẫu `2-bug.md` có sẵn trong `.github/ISSUE_TEMPLATE/`.
- **Gắn nhãn chuẩn:** Mỗi lỗi phải được gắn nhãn Severity (`critical`, `high`, `medium`, `low`) và gán Milestone (`MS-xx`).
- **Phân công trách nhiệm:** QA tạo bug issue kèm video/ảnh chụp màn hình và các bước tái hiện (reproduce steps); Tech Lead phân công Developer tương ứng; Developer sửa lỗi và tạo PR; QA verify lại trên Staging trước khi đóng Issue.
