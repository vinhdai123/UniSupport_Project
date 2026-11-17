# Quy trình luồng công việc (Workflows)

<!-- Hướng dẫn: phần này dùng làm bằng chứng cho PRD, effort và rủi ro. Giúp làm rõ cách các tác nhân phối hợp xuyên suốt các chức năng của UniSupport. -->

Hệ thống **UniSupport** bao gồm 4 luồng quy trình chính:

---

## 1. Luồng Tiếp nhận và Xử lý Ticket (Ticket Handling Workflow)

```mermaid
sequenceDiagram
    autonumber
    actor SV as Sinh viên
    participant Sys as Hệ thống UniSupport
    actor CB as Cán bộ xử lý (Staff)
    actor TP as Trưởng phòng (Manager)

    SV->>Sys: Gửi yêu cầu hỗ trợ (Submit Ticket)
    Sys->>Sys: Tự động phân loại theo Category & tính SLA deadline
    Sys-->>CB: Gán vào hàng đợi (Queue) phòng ban
    CB->>Sys: Tiếp nhận (In Progress) & Gửi phản hồi
    alt Cần sinh viên bổ sung thông tin
        CB->>Sys: Chuyển trạng thái "Pending Info"
        Sys-->>SV: Thông báo cần bổ sung thông tin
        SV->>Sys: Cung cấp thông tin bổ sung
        Sys-->>CB: Tự động chuyển lại "In Progress"
    end
    CB->>Sys: Giải quyết Ticket & Ghi nhận kết quả (Resolved)
    Sys-->>SV: Thông báo kết quả xử lý
    SV->>Sys: Đánh giá độ hài lòng (CSAT) hoặc yêu cầu mở lại
    Sys->>Sys: Tự động đóng Ticket sau 48h (Closed)
```

---

## 2. Luồng Chuyển tiếp Phòng ban (Ticket Escalation & Re-route Workflow)

1. **Nhận diện sai tuyến:** Cán bộ phát hiện Ticket không thuộc phạm vi xử lý của phòng ban mình.
2. **Yêu cầu chuyển tiếp:** Cán bộ chọn phòng ban đích và nhập lý do chuyển giao (Ghi chú nội bộ - Internal Note).
3. **Phê duyệt chuyển phòng:** Trưởng phòng hoặc Cán bộ có thẩm quyền xác nhận chuyển giao.
4. **Cập nhật SLA:** Hệ thống tính toán lại SLA theo chính sách của phòng ban tiếp nhận mới.

---

## 3. Luồng Thu thập Phản hồi và Đánh giá (CSAT Workflow)

1. Khi Ticket chuyển sang trạng thái `Resolved`, sinh viên nhận thông báo kèm khảo sát CSAT (1-5 sao + bình luận).
2. Nếu sinh viên đánh giá $\le 2$ sao (bất mãn), hệ thống tự động gắn cờ cảnh báo gửi tới Trưởng phòng ban để rà soát chất lượng dịch vụ.
3. Số liệu CSAT được tổng hợp trực tiếp vào [M05 - Dashboard & Report](../03-modules/M05-dashboard-report/prd.md).

---

## 4. Liên kết nghiệp vụ

- Ma trận chuyển trạng thái chi tiết: [02-domain/state-transition.md](../02-domain/state-transition.md)
- Đặc tả chức năng cán bộ: [03-modules/M03-staff-desk/prd.md](../03-modules/M03-staff-desk/prd.md)
- Đặc tả cổng sinh viên: [03-modules/M02-student-portal/prd.md](../03-modules/M02-student-portal/prd.md)
