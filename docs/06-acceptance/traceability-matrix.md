# Ma trận truy vết UniSupport

Bảng tổng hợp theo từng AC từ PRD, test, task GitHub và kế hoạch, theo Master Plan baseline 3.2. Cột Báo giá lấy từ cột Module và FR của sheet Báo giá trong [quotation.xlsx](../08-project/quotation.xlsx); nhiều AC dùng chung một hạng mục. Một chức năng có thể được triển khai qua nhiều gói công việc, như phần Sinh viên ở Q-04 và luồng xử lý/kết quả tại Q-05. Quản trị tài khoản theo WBS 3.7 thuộc Q-06, thông báo WBS 4.6 thuộc Q-05, SLA WBS 5.3 thuộc Q-06.

Các AC có nhiều điều kiện được kiểm theo từng ca con trong cùng mã TS. Khi chạy TS-020, TS-022, TS-023, TS-027, TS-039, TS-051, TS-052, TS-065, TS-082 hoặc TS-100, lưu kết quả từng ca con trước khi đánh dấu AC đạt. Đối chiếu quyền chuyển phòng với OQ-05 và kiểm dữ liệu giả lập trên từng môi trường theo NFR-GLOBAL-01. Tham số tệp tham chiếu BR-02 và OQ-04.

| AC hoặc NFR | Test | Parent task | Milestone | Báo giá |
| --- | --- | --- | --- | --- |
| [FR-AUTH-01/AC-01](../03-modules/M01-auth-rbac/prd.md) | TS-001 | [#101](https://github.com/vinhdai123/UniSupport_Project/issues/101) | MS-01 | Q-03 |
| [FR-AUTH-01/AC-02](../03-modules/M01-auth-rbac/prd.md) | TS-002 | [#101](https://github.com/vinhdai123/UniSupport_Project/issues/101) | MS-01 | Q-03 |
| [FR-AUTH-01/AC-03](../03-modules/M01-auth-rbac/prd.md) | TS-003 | [#101](https://github.com/vinhdai123/UniSupport_Project/issues/101) | MS-01 | Q-03 |
| [FR-AUTH-02/AC-01](../03-modules/M01-auth-rbac/prd.md) | TS-004 | [#56](https://github.com/vinhdai123/UniSupport_Project/issues/56) | MS-02 | Q-03 |
| [FR-AUTH-02/AC-02](../03-modules/M01-auth-rbac/prd.md) | TS-005 | [#56](https://github.com/vinhdai123/UniSupport_Project/issues/56) | MS-02 | Q-03 |
| [FR-AUTH-02/AC-03](../03-modules/M01-auth-rbac/prd.md) | TS-006 | [#56](https://github.com/vinhdai123/UniSupport_Project/issues/56) | MS-02 | Q-03 |
| [FR-AUTH-02/AC-04](../03-modules/M01-auth-rbac/prd.md) | TS-007 | [#56](https://github.com/vinhdai123/UniSupport_Project/issues/56) | MS-02 | Q-03 |
| [FR-AUTH-03/AC-01](../03-modules/M01-auth-rbac/prd.md) | TS-008 | [#93](https://github.com/vinhdai123/UniSupport_Project/issues/93) | MS-03 | Q-03 |
| [FR-AUTH-03/AC-02](../03-modules/M01-auth-rbac/prd.md) | TS-009 | [#55](https://github.com/vinhdai123/UniSupport_Project/issues/55) | MS-02 | Q-03 |
| [FR-AUTH-03/AC-03](../03-modules/M01-auth-rbac/prd.md) | TS-010 | [#55](https://github.com/vinhdai123/UniSupport_Project/issues/55) | MS-02 | Q-03 |
| [FR-AUTH-04/AC-01](../03-modules/M01-auth-rbac/prd.md) | TS-011 | [#59](https://github.com/vinhdai123/UniSupport_Project/issues/59) | MS-04 | Q-03 |
| [FR-AUTH-04/AC-02](../03-modules/M01-auth-rbac/prd.md) | TS-012 | [#59](https://github.com/vinhdai123/UniSupport_Project/issues/59) | MS-04 | Q-03 |
| [FR-AUTH-05/AC-01](../03-modules/M01-auth-rbac/prd.md) | TS-013 | [#77](https://github.com/vinhdai123/UniSupport_Project/issues/77) | MS-04 | Q-03 |
| [FR-AUTH-05/AC-02](../03-modules/M01-auth-rbac/prd.md) | TS-014 | [#77](https://github.com/vinhdai123/UniSupport_Project/issues/77) | MS-04 | Q-03 |
| [FR-AUTH-06/AC-01](../03-modules/M01-auth-rbac/prd.md) | TS-015 | [#101](https://github.com/vinhdai123/UniSupport_Project/issues/101) | MS-01 | Q-03 |
| [FR-AUTH-06/AC-02](../03-modules/M01-auth-rbac/prd.md) | TS-016 | [#101](https://github.com/vinhdai123/UniSupport_Project/issues/101) | MS-01 | Q-03 |
| [FR-AUTH-06/AC-03](../03-modules/M01-auth-rbac/prd.md) | TS-017 | [#101](https://github.com/vinhdai123/UniSupport_Project/issues/101) | MS-01 | Q-03 |
| [FR-AUTH-07/AC-01](../03-modules/M01-auth-rbac/prd.md) | TS-018 | [#80](https://github.com/vinhdai123/UniSupport_Project/issues/80) | MS-02 | Q-06 |
| [FR-AUTH-07/AC-02](../03-modules/M01-auth-rbac/prd.md) | TS-019 | [#80](https://github.com/vinhdai123/UniSupport_Project/issues/80) | MS-02 | Q-06 |
| [FR-AUTH-07/AC-03](../03-modules/M01-auth-rbac/prd.md) | TS-020 | [#80](https://github.com/vinhdai123/UniSupport_Project/issues/80) | MS-02 | Q-06 |
| [FR-STU-01/AC-01](../03-modules/M02-student-portal/prd.md) | TS-021 | [#60](https://github.com/vinhdai123/UniSupport_Project/issues/60), [#93](https://github.com/vinhdai123/UniSupport_Project/issues/93) | MS-03 | Q-04 |
| [FR-STU-01/AC-02](../03-modules/M02-student-portal/prd.md) | TS-022 | [#60](https://github.com/vinhdai123/UniSupport_Project/issues/60) | MS-03 | Q-04 |
| [FR-STU-01/AC-03](../03-modules/M02-student-portal/prd.md) | TS-023 | [#60](https://github.com/vinhdai123/UniSupport_Project/issues/60) | MS-03 | Q-04 |
| [FR-STU-01/AC-04](../03-modules/M02-student-portal/prd.md) | TS-123 | [#60](https://github.com/vinhdai123/UniSupport_Project/issues/60) | MS-03 | Q-04 |
| [FR-STU-02/AC-01](../03-modules/M02-student-portal/prd.md) | TS-024 | [#68](https://github.com/vinhdai123/UniSupport_Project/issues/68) | MS-03 | Q-04 |
| [FR-STU-02/AC-02](../03-modules/M02-student-portal/prd.md) | TS-025 | [#68](https://github.com/vinhdai123/UniSupport_Project/issues/68) | MS-03 | Q-04 |
| [FR-STU-02/AC-03](../03-modules/M02-student-portal/prd.md) | TS-124 | [#68](https://github.com/vinhdai123/UniSupport_Project/issues/68) | MS-03 | Q-04 |
| [FR-STU-03/AC-01](../03-modules/M02-student-portal/prd.md) | TS-026 | [#79](https://github.com/vinhdai123/UniSupport_Project/issues/79) | MS-04 | Q-04 |
| [FR-STU-03/AC-02](../03-modules/M02-student-portal/prd.md) | TS-027 | [#79](https://github.com/vinhdai123/UniSupport_Project/issues/79) | MS-04 | Q-04 |
| [FR-STU-03/AC-03](../03-modules/M02-student-portal/prd.md) | TS-028 | [#79](https://github.com/vinhdai123/UniSupport_Project/issues/79) | MS-04 | Q-04 |
| [FR-STU-03/AC-04](../03-modules/M02-student-portal/prd.md) | TS-029 | [#79](https://github.com/vinhdai123/UniSupport_Project/issues/79) | MS-04 | Q-04 |
| [FR-STU-04/AC-01](../03-modules/M02-student-portal/prd.md) | TS-030 | [#74](https://github.com/vinhdai123/UniSupport_Project/issues/74) | MS-04 | Q-04, Q-05 |
| [FR-STU-04/AC-02](../03-modules/M02-student-portal/prd.md) | TS-031 | [#74](https://github.com/vinhdai123/UniSupport_Project/issues/74) | MS-04 | Q-04, Q-05 |
| [FR-STU-04/AC-03](../03-modules/M02-student-portal/prd.md) | TS-125 | [#74](https://github.com/vinhdai123/UniSupport_Project/issues/74) | MS-04 | Q-04, Q-05 |
| [FR-STU-05/AC-01](../03-modules/M02-student-portal/prd.md) | TS-032 | [#75](https://github.com/vinhdai123/UniSupport_Project/issues/75) | MS-04 | Q-04, Q-05 |
| [FR-STU-05/AC-02](../03-modules/M02-student-portal/prd.md) | TS-033 | [#75](https://github.com/vinhdai123/UniSupport_Project/issues/75) | MS-04 | Q-04, Q-05 |
| [FR-STU-05/AC-03](../03-modules/M02-student-portal/prd.md) | TS-034 | [#75](https://github.com/vinhdai123/UniSupport_Project/issues/75) | MS-04 | Q-04, Q-05 |
| [FR-STU-06/AC-01](../03-modules/M02-student-portal/prd.md) | TS-035 | [#14](https://github.com/vinhdai123/UniSupport_Project/issues/14) | MS-03 | Q-04 |
| [FR-STU-06/AC-02](../03-modules/M02-student-portal/prd.md) | TS-036 | [#14](https://github.com/vinhdai123/UniSupport_Project/issues/14) | MS-03 | Q-04 |
| [FR-STU-06/AC-03](../03-modules/M02-student-portal/prd.md) | TS-037 | [#14](https://github.com/vinhdai123/UniSupport_Project/issues/14) | MS-03 | Q-04 |
| [FR-STU-07/AC-01](../03-modules/M02-student-portal/prd.md) | TS-038 | [#70](https://github.com/vinhdai123/UniSupport_Project/issues/70) | MS-04 | Q-05 |
| [FR-STU-07/AC-02](../03-modules/M02-student-portal/prd.md) | TS-039 | [#70](https://github.com/vinhdai123/UniSupport_Project/issues/70) | MS-04 | Q-05 |
| [FR-STU-07/AC-03](../03-modules/M02-student-portal/prd.md) | TS-040 | [#70](https://github.com/vinhdai123/UniSupport_Project/issues/70) | MS-04 | Q-05 |
| [FR-STF-01/AC-01](../03-modules/M03-staff-desk/prd.md) | TS-041 | [#67](https://github.com/vinhdai123/UniSupport_Project/issues/67) | MS-04 | Q-05 |
| [FR-STF-01/AC-02](../03-modules/M03-staff-desk/prd.md) | TS-042 | [#67](https://github.com/vinhdai123/UniSupport_Project/issues/67) | MS-04 | Q-05 |
| [FR-STF-01/AC-03](../03-modules/M03-staff-desk/prd.md) | TS-043 | [#67](https://github.com/vinhdai123/UniSupport_Project/issues/67) | MS-04 | Q-05 |
| [FR-STF-02/AC-01](../03-modules/M03-staff-desk/prd.md) | TS-044 | [#63](https://github.com/vinhdai123/UniSupport_Project/issues/63), [#67](https://github.com/vinhdai123/UniSupport_Project/issues/67) | MS-04 | Q-05 |
| [FR-STF-02/AC-02](../03-modules/M03-staff-desk/prd.md) | TS-045 | [#63](https://github.com/vinhdai123/UniSupport_Project/issues/63) | MS-04 | Q-05 |
| [FR-STF-02/AC-03](../03-modules/M03-staff-desk/prd.md) | TS-046 | [#63](https://github.com/vinhdai123/UniSupport_Project/issues/63) | MS-04 | Q-05 |
| [FR-STF-02/AC-04](../03-modules/M03-staff-desk/prd.md) | TS-047 | [#63](https://github.com/vinhdai123/UniSupport_Project/issues/63) | MS-04 | Q-05 |
| [FR-STF-03/AC-01](../03-modules/M03-staff-desk/prd.md) | TS-048 | [#64](https://github.com/vinhdai123/UniSupport_Project/issues/64) | MS-04 | Q-05 |
| [FR-STF-03/AC-02](../03-modules/M03-staff-desk/prd.md) | TS-049 | [#64](https://github.com/vinhdai123/UniSupport_Project/issues/64) | MS-04 | Q-05 |
| [FR-STF-03/AC-03](../03-modules/M03-staff-desk/prd.md) | TS-050 | [#64](https://github.com/vinhdai123/UniSupport_Project/issues/64) | MS-04 | Q-05 |
| [FR-STF-03/AC-04](../03-modules/M03-staff-desk/prd.md) | TS-126 | [#64](https://github.com/vinhdai123/UniSupport_Project/issues/64) | MS-04 | Q-05 |
| [FR-STF-04/AC-01](../03-modules/M03-staff-desk/prd.md) | TS-051 | [#13](https://github.com/vinhdai123/UniSupport_Project/issues/13) | MS-04 | Q-05 |
| [FR-STF-04/AC-02](../03-modules/M03-staff-desk/prd.md) | TS-052 | [#13](https://github.com/vinhdai123/UniSupport_Project/issues/13) | MS-04 | Q-05 |
| [FR-STF-05/AC-01](../03-modules/M03-staff-desk/prd.md) | TS-053 | [#69](https://github.com/vinhdai123/UniSupport_Project/issues/69) | MS-04 | Q-05 |
| [FR-STF-05/AC-02](../03-modules/M03-staff-desk/prd.md) | TS-054 | [#69](https://github.com/vinhdai123/UniSupport_Project/issues/69) | MS-04 | Q-05 |
| [FR-STF-05/AC-03](../03-modules/M03-staff-desk/prd.md) | TS-055 | [#69](https://github.com/vinhdai123/UniSupport_Project/issues/69) | MS-04 | Q-05 |
| [FR-STF-05/AC-04](../03-modules/M03-staff-desk/prd.md) | TS-056 | [#69](https://github.com/vinhdai123/UniSupport_Project/issues/69) | MS-04 | Q-05 |
| [FR-STF-05/AC-05](../03-modules/M03-staff-desk/prd.md) | TS-127 | [#69](https://github.com/vinhdai123/UniSupport_Project/issues/69) | MS-04 | Q-05 |
| [FR-STF-06/AC-01](../03-modules/M03-staff-desk/prd.md) | TS-057 | [#15](https://github.com/vinhdai123/UniSupport_Project/issues/15) | MS-04 | Q-05 |
| [FR-STF-06/AC-02](../03-modules/M03-staff-desk/prd.md) | TS-058 | [#15](https://github.com/vinhdai123/UniSupport_Project/issues/15) | MS-04 | Q-05 |
| [FR-STF-06/AC-03](../03-modules/M03-staff-desk/prd.md) | TS-059 | [#15](https://github.com/vinhdai123/UniSupport_Project/issues/15) | MS-04 | Q-05 |
| [FR-STF-07/AC-01](../03-modules/M03-staff-desk/prd.md) | TS-060 | [#71](https://github.com/vinhdai123/UniSupport_Project/issues/71) | MS-04 | Q-06 |
| [FR-STF-07/AC-02](../03-modules/M03-staff-desk/prd.md) | TS-061 | [#71](https://github.com/vinhdai123/UniSupport_Project/issues/71) | MS-04 | Q-06 |
| [FR-STF-07/AC-03](../03-modules/M03-staff-desk/prd.md) | TS-062 | [#71](https://github.com/vinhdai123/UniSupport_Project/issues/71) | MS-04 | Q-06 |
| [FR-ADM-01/AC-01](../03-modules/M04-management-admin/prd.md) | TS-063 | [#17](https://github.com/vinhdai123/UniSupport_Project/issues/17) | MS-04 | Q-06 |
| [FR-ADM-01/AC-02](../03-modules/M04-management-admin/prd.md) | TS-064 | [#17](https://github.com/vinhdai123/UniSupport_Project/issues/17) | MS-04 | Q-06 |
| [FR-ADM-01/AC-03](../03-modules/M04-management-admin/prd.md) | TS-065 | [#17](https://github.com/vinhdai123/UniSupport_Project/issues/17) | MS-04 | Q-06 |
| [FR-ADM-01/AC-04](../03-modules/M04-management-admin/prd.md) | TS-066 | [#17](https://github.com/vinhdai123/UniSupport_Project/issues/17) | MS-04 | Q-06 |
| [FR-ADM-02/AC-01](../03-modules/M04-management-admin/prd.md) | TS-067 | [#17](https://github.com/vinhdai123/UniSupport_Project/issues/17) | MS-04 | Q-06 |
| [FR-ADM-02/AC-02](../03-modules/M04-management-admin/prd.md) | TS-068 | [#17](https://github.com/vinhdai123/UniSupport_Project/issues/17) | MS-04 | Q-06 |
| [FR-ADM-02/AC-03](../03-modules/M04-management-admin/prd.md) | TS-069 | [#17](https://github.com/vinhdai123/UniSupport_Project/issues/17) | MS-04 | Q-06 |
| [FR-ADM-02/AC-04](../03-modules/M04-management-admin/prd.md) | TS-070 | [#17](https://github.com/vinhdai123/UniSupport_Project/issues/17) | MS-04 | Q-06 |
| [FR-ADM-03/AC-01](../03-modules/M04-management-admin/prd.md) | TS-071 | [#17](https://github.com/vinhdai123/UniSupport_Project/issues/17) | MS-04 | Q-06 |
| [FR-ADM-03/AC-02](../03-modules/M04-management-admin/prd.md) | TS-072 | [#17](https://github.com/vinhdai123/UniSupport_Project/issues/17) | MS-04 | Q-06 |
| [FR-ADM-03/AC-03](../03-modules/M04-management-admin/prd.md) | TS-073 | [#17](https://github.com/vinhdai123/UniSupport_Project/issues/17) | MS-04 | Q-06 |
| [FR-ADM-04/AC-01](../03-modules/M04-management-admin/prd.md) | TS-074 | [#73](https://github.com/vinhdai123/UniSupport_Project/issues/73) | MS-04 | Q-06 |
| [FR-ADM-04/AC-02](../03-modules/M04-management-admin/prd.md) | TS-075 | [#73](https://github.com/vinhdai123/UniSupport_Project/issues/73) | MS-04 | Q-06 |
| [FR-ADM-04/AC-03](../03-modules/M04-management-admin/prd.md) | TS-076 | [#73](https://github.com/vinhdai123/UniSupport_Project/issues/73) | MS-04 | Q-06 |
| [FR-ADM-05/AC-01](../03-modules/M04-management-admin/prd.md) | TS-077 | [#72](https://github.com/vinhdai123/UniSupport_Project/issues/72) | MS-04 | Q-06 |
| [FR-ADM-05/AC-02](../03-modules/M04-management-admin/prd.md) | TS-078 | [#72](https://github.com/vinhdai123/UniSupport_Project/issues/72) | MS-04 | Q-06 |
| [FR-ADM-06/AC-01](../03-modules/M04-management-admin/prd.md) | TS-079 | [#71](https://github.com/vinhdai123/UniSupport_Project/issues/71) | MS-04 | Q-06 |
| [FR-ADM-06/AC-02](../03-modules/M04-management-admin/prd.md) | TS-080 | [#71](https://github.com/vinhdai123/UniSupport_Project/issues/71) | MS-04 | Q-06 |
| [FR-ADM-07/AC-01](../03-modules/M04-management-admin/prd.md) | TS-081 | [#81](https://github.com/vinhdai123/UniSupport_Project/issues/81) | MS-04 | Q-06 |
| [FR-ADM-07/AC-02](../03-modules/M04-management-admin/prd.md) | TS-082 | [#81](https://github.com/vinhdai123/UniSupport_Project/issues/81) | MS-04 | Q-06 |
| [FR-RPT-01/AC-01](../03-modules/M05-dashboard-report/prd.md) | TS-083 | [#20](https://github.com/vinhdai123/UniSupport_Project/issues/20) | MS-05 | Q-07 |
| [FR-RPT-01/AC-02](../03-modules/M05-dashboard-report/prd.md) | TS-084 | [#20](https://github.com/vinhdai123/UniSupport_Project/issues/20) | MS-05 | Q-07 |
| [FR-RPT-01/AC-03](../03-modules/M05-dashboard-report/prd.md) | TS-085 | [#20](https://github.com/vinhdai123/UniSupport_Project/issues/20) | MS-05 | Q-07 |
| [FR-RPT-01/AC-04](../03-modules/M05-dashboard-report/prd.md) | TS-086 | [#20](https://github.com/vinhdai123/UniSupport_Project/issues/20) | MS-05 | Q-07 |
| [FR-RPT-01/AC-05](../03-modules/M05-dashboard-report/prd.md) | TS-087 | [#20](https://github.com/vinhdai123/UniSupport_Project/issues/20) | MS-05 | Q-07 |
| [FR-RPT-02/AC-01](../03-modules/M05-dashboard-report/prd.md) | TS-088 | [#20](https://github.com/vinhdai123/UniSupport_Project/issues/20) | MS-05 | Q-07 |
| [FR-RPT-02/AC-02](../03-modules/M05-dashboard-report/prd.md) | TS-089 | [#20](https://github.com/vinhdai123/UniSupport_Project/issues/20) | MS-05 | Q-07 |
| [FR-RPT-02/AC-03](../03-modules/M05-dashboard-report/prd.md) | TS-090 | [#20](https://github.com/vinhdai123/UniSupport_Project/issues/20) | MS-05 | Q-07 |
| [FR-RPT-03/AC-01](../03-modules/M05-dashboard-report/prd.md) | TS-091 | [#20](https://github.com/vinhdai123/UniSupport_Project/issues/20) | MS-05 | Q-07 |
| [FR-RPT-03/AC-02](../03-modules/M05-dashboard-report/prd.md) | TS-092 | [#20](https://github.com/vinhdai123/UniSupport_Project/issues/20) | MS-05 | Q-07 |
| [FR-RPT-04/AC-01](../03-modules/M05-dashboard-report/prd.md) | TS-093 | [#20](https://github.com/vinhdai123/UniSupport_Project/issues/20) | MS-05 | Q-07 |
| [FR-RPT-04/AC-02](../03-modules/M05-dashboard-report/prd.md) | TS-094 | [#20](https://github.com/vinhdai123/UniSupport_Project/issues/20) | MS-05 | Q-07 |
| [FR-RPT-05/AC-01](../03-modules/M05-dashboard-report/prd.md) | TS-095 | [#76](https://github.com/vinhdai123/UniSupport_Project/issues/76) | MS-05 | Q-07 |
| [FR-RPT-05/AC-02](../03-modules/M05-dashboard-report/prd.md) | TS-096 | [#76](https://github.com/vinhdai123/UniSupport_Project/issues/76) | MS-05 | Q-07 |
| [FR-RPT-05/AC-03](../03-modules/M05-dashboard-report/prd.md) | TS-097 | [#76](https://github.com/vinhdai123/UniSupport_Project/issues/76) | MS-05 | Q-07 |
| [NFR-GLOBAL-01/AC-01](../05-non-functional-requirements/README.md) | TS-098 | [#22](https://github.com/vinhdai123/UniSupport_Project/issues/22) | MS-05 | Q-08 |
| [NFR-GLOBAL-01/AC-02](../05-non-functional-requirements/README.md) | TS-099 | [#22](https://github.com/vinhdai123/UniSupport_Project/issues/22) | MS-05 | Q-08 |
| [NFR-GLOBAL-01/AC-03](../05-non-functional-requirements/README.md) | TS-100 | [#22](https://github.com/vinhdai123/UniSupport_Project/issues/22) | MS-05 | Q-08 |
| [NFR-GLOBAL-01/AC-04](../05-non-functional-requirements/README.md) | TS-101 | [#22](https://github.com/vinhdai123/UniSupport_Project/issues/22) | MS-05 | Q-08 |
| [NFR-GLOBAL-02/AC-01](../05-non-functional-requirements/README.md) | TS-102 | [#22](https://github.com/vinhdai123/UniSupport_Project/issues/22) | MS-05 | Q-03–Q-07 (làm theo module), Q-08 (kiểm đủ 5 module) |
| [NFR-GLOBAL-02/AC-02](../05-non-functional-requirements/README.md) | TS-103 | [#22](https://github.com/vinhdai123/UniSupport_Project/issues/22) | MS-05 | Q-03–Q-07 (làm theo module), Q-08 (kiểm đủ 5 module) |
| [NFR-GLOBAL-02/AC-03](../05-non-functional-requirements/README.md) | TS-104 | [#22](https://github.com/vinhdai123/UniSupport_Project/issues/22) | MS-05 | Q-03–Q-07 (làm theo module), Q-08 (kiểm đủ 5 module) |
| [NFR-GLOBAL-02/AC-04](../05-non-functional-requirements/README.md) | TS-105 | [#22](https://github.com/vinhdai123/UniSupport_Project/issues/22) | MS-05 | Q-03–Q-07 (làm theo module), Q-08 (kiểm đủ 5 module) |
| [NFR-GLOBAL-03/AC-01](../05-non-functional-requirements/README.md) | TS-106 | [#22](https://github.com/vinhdai123/UniSupport_Project/issues/22) | MS-05 | Q-03–Q-07 (làm theo module), Q-08 (kiểm đủ 5 module) |
| [NFR-GLOBAL-03/AC-02](../05-non-functional-requirements/README.md) | TS-107 | [#22](https://github.com/vinhdai123/UniSupport_Project/issues/22) | MS-05 | Q-03–Q-07 (làm theo module), Q-08 (kiểm đủ 5 module) |
| [NFR-GLOBAL-03/AC-03](../05-non-functional-requirements/README.md) | TS-108 | [#22](https://github.com/vinhdai123/UniSupport_Project/issues/22) | MS-05 | Q-03–Q-07 (làm theo module), Q-08 (kiểm đủ 5 module) |
| [NFR-GLOBAL-03/AC-04](../05-non-functional-requirements/README.md) | TS-109 | [#22](https://github.com/vinhdai123/UniSupport_Project/issues/22) | MS-05 | Q-03–Q-07 (làm theo module), Q-08 (kiểm đủ 5 module) |
| [NFR-GLOBAL-03/AC-05](../05-non-functional-requirements/README.md) | TS-110 | [#22](https://github.com/vinhdai123/UniSupport_Project/issues/22) | MS-05 | Q-03–Q-07 (làm theo module), Q-08 (kiểm đủ 5 module) |
| [NFR-GLOBAL-04/AC-01](../05-non-functional-requirements/README.md) | TS-111 | [#22](https://github.com/vinhdai123/UniSupport_Project/issues/22) | MS-05 | Q-03–Q-07 (làm theo module), Q-08 (kiểm đủ 5 module) |
| [NFR-GLOBAL-04/AC-02](../05-non-functional-requirements/README.md) | TS-112 | [#22](https://github.com/vinhdai123/UniSupport_Project/issues/22) | MS-05 | Q-03–Q-07 (làm theo module), Q-08 (kiểm đủ 5 module) |
| [NFR-GLOBAL-04/AC-03](../05-non-functional-requirements/README.md) | TS-113 | [#22](https://github.com/vinhdai123/UniSupport_Project/issues/22) | MS-05 | Q-03–Q-07 (làm theo module), Q-08 (kiểm đủ 5 module) |
| [NFR-GLOBAL-04/AC-04](../05-non-functional-requirements/README.md) | TS-114 | [#22](https://github.com/vinhdai123/UniSupport_Project/issues/22) | MS-05 | Q-03–Q-07 (làm theo module), Q-08 (kiểm đủ 5 module) |
| [NFR-GLOBAL-04/AC-05](../05-non-functional-requirements/README.md) | TS-115 | [#22](https://github.com/vinhdai123/UniSupport_Project/issues/22) | MS-05 | Q-03–Q-07 (làm theo module), Q-08 (kiểm đủ 5 module) |
| [NFR-GLOBAL-04/AC-06](../05-non-functional-requirements/README.md) | TS-116 | [#22](https://github.com/vinhdai123/UniSupport_Project/issues/22) | MS-05 | Q-03–Q-07 (làm theo module), Q-08 (kiểm đủ 5 module) |
| [NFR-GLOBAL-01](../05-non-functional-requirements/README.md) | TS-117 | [#23](https://github.com/vinhdai123/UniSupport_Project/issues/23) | MS-06 | Q-08 |
| [NFR-GLOBAL-02](../05-non-functional-requirements/README.md) | TS-118 | [#23](https://github.com/vinhdai123/UniSupport_Project/issues/23) | MS-06 | Q-08 |
| [NFR-GLOBAL-03](../05-non-functional-requirements/README.md) | TS-119 | [#23](https://github.com/vinhdai123/UniSupport_Project/issues/23) | MS-06 | Q-08 |
| [NFR-GLOBAL-04](../05-non-functional-requirements/README.md) | TS-120 | [#23](https://github.com/vinhdai123/UniSupport_Project/issues/23) | MS-06 | Q-08 |
| [NFR-PERF-01](../05-non-functional-requirements/README.md) | TS-121 | [#23](https://github.com/vinhdai123/UniSupport_Project/issues/23) | MS-06 | Q-08 |
| [NFR-SEC-01](../05-non-functional-requirements/README.md) | TS-122 | [#26](https://github.com/vinhdai123/UniSupport_Project/issues/26) | MS-06 | Q-08 |
