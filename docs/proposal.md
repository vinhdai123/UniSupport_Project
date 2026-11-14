**Đề xuất triển khai UniSupport**

*Hệ thống quản lý yêu cầu hỗ trợ sinh viên*

| Thông tin | Nội dung |
| :---: | ----- |
| Khách hàng | Aurora University  |
| Bên đề xuất | Project Team UniSupport |
| Ngày đề xuất | 14/11/2026 |
| Mục đích | Trao đổi và đàm phán phương án triển khai |

Project Team đề xuất triển khai UniSupport cho Aurora University với giá đề xuất **700.000.000 VNĐ** và thời gian thực hiện **23 tuần**. Nhà trường nhận được một cổng hỗ trợ tập trung, từ tiếp nhận yêu cầu đến phân công, trao đổi, trả kết quả và theo dõi hiệu suất. Giải pháp phục vụ khoảng 3.000 sinh viên cùng các cán bộ, quản lý và quản trị viên của nhà trường.

Khoản đầu tư bao gồm phân tích, thiết kế, phát triển, tích hợp, kiểm thử, triển khai, hướng dẫn, bàn giao mã nguồn và bảo hành phần mềm 30 ngày. Project Team chịu trách nhiệm điều phối xuyên suốt để nhà trường có một đầu mối làm việc về phạm vi, tiến độ và kết quả bàn giao.

# **1 Bài toán và mục tiêu**

## **Bối cảnh nghiệp vụ**

Aurora University cần một cách thống nhất để sinh viên gửi và theo dõi yêu cầu, cán bộ phối hợp xử lý và quản lý nhìn thấy tình trạng công việc theo phòng ban. UniSupport đáp ứng nhu cầu này bằng mã Ticket, lịch sử trao đổi, người phụ trách và trạng thái xử lý trên cùng một hệ thống. Trong giai đoạn khảo sát, PM/BA cùng đại diện nhà trường xác nhận hiện trạng, danh mục yêu cầu và các luồng phối hợp để hoàn thiện thiết kế.

Khi yêu cầu chuyển giữa các phòng ban, các bên tiếp tục theo dõi cùng một Ticket và lịch sử xử lý. Dữ liệu được tổng hợp để nhà trường xem khối lượng công việc, yêu cầu tồn đọng và các nhóm vấn đề cần cải thiện. Sinh viên có thể tự tra cứu tiến độ, còn cán bộ tập trung vào xử lý và trả kết quả.

## **Giá trị mang lại cho nhà trường**

* Sinh viên gửi yêu cầu tại một cổng, nhận mã Ticket và theo dõi trạng thái, trao đổi, kết quả của chính mình.  
* Cán bộ có danh sách xử lý tập trung, biết Ticket được giao, thông tin cần bổ sung và lịch sử xử lý.  
* Quản lý theo dõi khối lượng công việc, Ticket tồn đọng, sắp đến hạn và quá hạn theo phạm vi quyền.  
* Nhà trường có Dashboard, báo cáo và dữ liệu xuất CSV để theo dõi hoạt động hỗ trợ.

Quy mô phục vụ dự kiến là khoảng 3.000 sinh viên. Hai bên xác nhận số người truy cập đồng thời, tải dữ liệu và các chỉ tiêu hiệu năng trong giai đoạn phân tích yêu cầu. Chỉ tiêu nghiệm thu được ghi trong đặc tả yêu cầu sản phẩm, gọi tắt là PRD.

# **2 Giải pháp và phạm vi thực hiện**

UniSupport là ứng dụng web dành cho bốn vai trò gồm Sinh viên, Cán bộ xử lý, Quản lý và Quản trị viên. Một Ticket được theo dõi từ lúc tạo, phân luồng, phân công, xử lý và yêu cầu bổ sung đến khi trả kết quả, đánh giá hoặc mở lại theo quy tắc đã xác nhận. Mã Ticket và lịch sử chung giúp các bên phối hợp trên cùng một yêu cầu.

## **In Scope**

Phạm vi thực hiện gồm các nhóm chức năng sau.

### **Module Sinh viên**

* Gửi yêu cầu theo danh mục, đính kèm tài liệu hoặc hình ảnh và nhận mã Ticket do hệ thống tạo.  
* Theo dõi các trạng thái Mới tạo, Đang xử lý, Cần bổ sung và Hoàn thành. Xem lịch sử xử lý của Ticket.  
* Trao đổi với cán bộ, bổ sung thông tin hoặc tài liệu khi được yêu cầu và nhận thông báo trong hệ thống, qua Email khi có cập nhật quan trọng.  
* Mở lại Ticket trong khoảng thời gian được xác nhận trong PRD.  
* Tra cứu FAQ theo chủ đề, tìm hướng dẫn trước khi tạo yêu cầu và đánh giá mức độ hài lòng sau khi Ticket hoàn thành.

### **Module Cán bộ xử lý**

* Xem danh sách Ticket trong phạm vi được phép. Tìm kiếm, lọc và sắp xếp theo trạng thái, danh mục, mức ưu tiên và thời gian.  
* Tự động phân luồng theo danh mục hoặc phòng ban. Phân công, chuyển tiếp hoặc chuyển cấp Ticket.  
* Cập nhật trạng thái và mức ưu tiên. Yêu cầu sinh viên bổ sung thông tin. Thêm ghi chú nội bộ.  
* Gửi phản hồi chính thức, sử dụng mẫu phản hồi và lưu lịch sử thao tác, thay đổi trạng thái.

### **Module Quản lý và Quản trị**

* Theo dõi số lượng Ticket, Ticket tồn đọng, sắp quá hạn và khối lượng công việc theo phòng ban hoặc cán bộ. Điều chuyển hoặc phân công lại khi cần.  
* Thiết lập thời hạn theo loại Ticket hoặc mức ưu tiên, theo dõi thời gian xử lý và cảnh báo sắp đến hạn hoặc quá hạn.  
* Quản lý danh mục yêu cầu, phòng ban, mức ưu tiên và quy tắc phân luồng.  
* Quản lý tài khoản, vai trò, nội dung FAQ hoặc Knowledge Base và mẫu phản hồi.

Đại diện nghiệp vụ của nhà trường xác nhận danh mục yêu cầu, tuyến phân công, thời hạn xử lý và quyền thao tác. Đội dự án cấu hình và kiểm tra hệ thống theo các quyết định đã thống nhất.

### **Dashboard và Báo cáo**

* Thống kê Ticket theo trạng thái, tỷ lệ hoàn thành, tồn đọng và thời gian xử lý trung bình.  
* Theo dõi hiệu suất theo phòng ban hoặc cán bộ, các nhóm vấn đề phổ biến và xu hướng Ticket theo thời gian.  
* Báo cáo mức độ hài lòng của sinh viên và xuất báo cáo CSV theo bộ lọc, phạm vi dữ liệu được phép.

### **Bảo mật và giao diện dùng chung**

* Đăng nhập bằng tài khoản UniSupport, hỗ trợ đặt lại mật khẩu và phân quyền chức năng, dữ liệu cho bốn vai trò.  
* Kiểm soát quyền truy cập Ticket và tệp đính kèm. Ghi nhận các thao tác quan trọng.  
* Dùng dữ liệu giả lập trong phát triển và kiểm thử.  
* Hỗ trợ Tiếng Việt và Tiếng Anh. Giao diện web tương thích Desktop và Mobile, nhất quán giữa các module.

Hai bên thống nhất quy tắc phân quyền, loại và dung lượng tệp, thời gian mở lại Ticket, nội dung thông báo và các chỉ tiêu phi chức năng trong PRD. Các quy tắc này được dùng để thiết kế và kiểm tra kết quả bàn giao.

## **Out of Scope**

* Thay đổi hoặc xây dựng lại quy trình nghiệp vụ hiện tại của Aurora University. Giải quyết các nghiệp vụ phát sinh thuộc thẩm quyền riêng của từng phòng ban hoặc trực tiếp xử lý nghiệp vụ thay nhà trường.  
* Cung cấp hoặc nâng cấp phần cứng, máy chủ vật lý và hạ tầng mạng của nhà trường.  
* Tích hợp SSO, hệ thống xác thực bên ngoài hoặc hệ thống bên thứ ba chưa được liệt kê trong phạm vi. Email phục vụ thông báo Ticket thuộc phạm vi đã nêu, với cấu hình dịch vụ được hai bên xác nhận.  
* Thu thập, làm sạch, chuẩn hóa hoặc chuyển đổi dữ liệu lịch sử thay cho Aurora University.  
* Phát triển ứng dụng Mobile riêng cho iOS hoặc Android. Phát triển AI, ML, Chatbot hoặc chức năng nâng cao ngoài phạm vi.  
* Cung cấp SMS hoặc push notification thay cho hai kênh thông báo đã nêu là trong hệ thống và Email.  
* Vận hành, bảo trì và hỗ trợ dài hạn sau bàn giao, ngoài thời gian bảo hành 30 ngày.

Yêu cầu ngoài phạm vi được tiếp nhận để đánh giá riêng. Đội dự án chỉ thực hiện sau khi hai bên thống nhất phạm vi bổ sung, giá và lịch thông qua yêu cầu thay đổi.

## **Quản lý yêu cầu chi tiết**

PM/BA cùng nhà trường làm rõ hành vi và tiêu chí nghiệm thu cho các chức năng tại mục 2, sau đó trình xác nhận PRD tại M1. PRD cụ thể hóa phạm vi trong đề xuất để đội dự án triển khai và nhà trường kiểm tra kết quả. Yêu cầu bổ sung chức năng hoặc mở rộng phạm vi đã xác nhận được đánh giá theo quy trình thay đổi tại mục 9\.

# **3 Assumptions**

Các giả định dưới đây được sử dụng để lập kế hoạch trước khi hoàn tất khảo sát chi tiết. Project Team cùng Aurora University rà soát và xác minh các giả định trong quá trình thống nhất phương án triển khai.

| Mã | Giả định lập kế hoạch |
| :---: | ----- |
| A-01 | Các quy trình hỗ trợ của nhà trường dự kiến có thể vận hành trên vòng đời Ticket tại mục 2\. Khác biệt giữa các phòng ban có thể đáp ứng bằng cấu hình danh mục, quyền, quy tắc phân luồng và thời hạn xử lý. |
| A-02 | Thông tin, quy trình và yêu cầu nghiệp vụ cần thiết dự kiến được Aurora University cung cấp đầy đủ, nhất quán trước các công việc phụ thuộc. Danh mục phòng ban, tài khoản, phân quyền và FAQ ban đầu dự kiến có sẵn dưới dạng bảng hoặc tài liệu điện tử có thể dùng để cấu hình. |
| A-03 | Đầu mối của nhà trường dự kiến có thể tổng hợp ý kiến các phòng ban và phản hồi tài liệu phân tích, thiết kế trong vòng 3 ngày làm việc kể từ khi nhận đủ tài liệu. Thời gian kiểm tra nghiệm thu từng mốc áp dụng theo mục 8\. |
| A-04 | Quy mô sử dụng trong giai đoạn triển khai dự kiến vào khoảng 3.000 sinh viên với bốn nhóm vai trò tại mục 2\. Tải đồng thời, dung lượng dữ liệu và cấu hình phục vụ được xác định trong khảo sát để đưa vào PRD tại M1. |
| A-05 | Dịch vụ Email và môi trường triển khai dự kiến hỗ trợ kết nối theo cấu hình tiêu chuẩn. Quyền truy cập cần thiết có thể được cấp theo lịch tích hợp. Môi trường Production dự kiến sẵn sàng từ đầu tuần 21 để chuẩn bị phát hành. |
| A-06 | Sau M1, quy trình Ticket, ma trận quyền và các quy tắc nghiệp vụ đã xác nhận dự kiến ổn định trong giai đoạn phát triển. Các đợt kiểm tra sau đó tập trung đối chiếu kết quả với phạm vi và tiêu chí đã thống nhất. |
| A-07 | Đại diện nghiệp vụ và vận hành của nhà trường dự kiến có thể tham gia kiểm tra chấp nhận, xác nhận kết quả và đào tạo theo lịch tuần 21–22, phục vụ quyết định sẵn sàng Go-live tại M3. |

# **4 Sản phẩm bàn giao**

| Giai đoạn | Đầu ra dự kiến và cách nhận diện |
| ----- | ----- |
| Phân tích và thiết kế | Phạm vi, PRD có phiên bản, Prototype, kiến trúc và thiết kế dữ liệu. Ghi nhận ý kiến và quyết định xác nhận tại M1. |
| Phát triển và kiểm thử | Phiên bản tích hợp các nhóm chức năng ở mục 2\. Kịch bản kiểm thử, hồ sơ kiểm tra và danh sách lỗi của phiên bản được trình nghiệm thu. |
| Sẵn sàng phát hành | Bản phát hành được nhận diện, hồ sơ kiểm thử chấp nhận của đại diện trường, tài liệu sử dụng và vận hành, kế hoạch triển khai và khôi phục. |
| Go-live và bàn giao | Hệ thống chính thức, mã nguồn, tài liệu kỹ thuật, HDSD và biên bản bàn giao. Hướng dẫn sử dụng cho đại diện Aurora University. |

Mỗi đầu ra được quản lý theo phiên bản, gắn với tiêu chí kiểm tra và xác nhận của đại diện có thẩm quyền. Tài liệu, mã nguồn và hướng dẫn vận hành đi cùng hệ thống để hỗ trợ nhà trường tiếp nhận và tổ chức sử dụng sau bàn giao.

# **5 Kế hoạch tổng thể**

## **Tiến độ 23 tuần**

Thời gian thực hiện dự kiến là 23 tuần, tính từ ngày khởi động do hai bên xác nhận sau khi hoàn tất thủ tục ký kết, tạm ứng và các đầu vào khởi động cần thiết. Lịch chi tiết thể hiện ngày làm việc, ngày nghỉ, thời điểm cung cấp thông tin và các đợt kiểm tra của nhà trường. Các giai đoạn triển khai dự kiến như sau.

| Giai đoạn | Tuần | Công việc chính |
| ----- | :---: | ----- |
| P1 Khởi động và yêu cầu | 1–2 | Thu thập, xác nhận yêu cầu, phạm vi sơ bộ và quy trình Ticket. |
| P2 Phân tích và thiết kế | 3–5 | Kiến trúc, dữ liệu, Prototype. Làm rõ PRD và khóa phạm vi. |
| P3 Nền tảng và xác thực | 6–8 | Giao diện dùng chung, đăng nhập, đặt lại mật khẩu, phân quyền bốn vai trò và kiểm thử. |
| P4 Ticket cốt lõi | 9–12 | Tạo, theo dõi, trao đổi, routing, assignment, priority, Email, ghi chú và lịch sử. |
| P5 Quản lý và quản trị | 13–15 | Workload, thời hạn, danh mục, phòng ban, tài khoản, routing, FAQ và mẫu phản hồi. |
| P6 Dashboard và báo cáo | 16–18 | Hiệu suất, xu hướng, hài lòng, CSV, responsive và đa ngôn ngữ. |
| P7 Tích hợp và bảo mật | 19–20 | Tổng hợp kiểm thử hệ thống, hồi quy, RBAC, quyền dữ liệu và tệp. Xử lý lỗi. |
| P8 Phát hành và nghiệm thu | 21–22 | Đóng băng mã nguồn, chuẩn bị Production, tài liệu, đào tạo và xác nhận sẵn sàng Go-live. |
| P9 Go-live và bàn giao | 23 | Triển khai, kiểm tra sau triển khai, hướng dẫn và bàn giao. |

Kiểm thử tích hợp và bảo mật được lên kế hoạch từ thiết kế, tiếp tục trong từng giai đoạn phát triển. P7 là đợt tổng hợp cuối kỳ. Kế hoạch chất lượng phải quy định kiểm thử hồi quy trước mỗi lần bàn giao và sau sửa lỗi.

## **Các mốc xác nhận và thanh toán**

| Mốc | Thời điểm dự kiến | Nội dung để hai bên xem xét |
| :---: | ----- | ----- |
| M1 | Tuần 5 | Prototype, PRD và phạm vi được xác nhận. Các thông số ảnh hưởng thiết kế, giá và nghiệm thu được xử lý. |
| M2 | Cuối tuần 20 | Hoàn tất tích hợp và kiểm thử hệ thống. Trình hồ sơ kiểm tra và lỗi còn tồn. |
| M3 | Cuối tuần 22 | Đại diện trường kiểm tra chấp nhận. Xác nhận sẵn sàng Go-live, tài liệu và điều kiện triển khai. |
| M4 | Tuần 23 | Go-live, kiểm tra sau triển khai, bàn giao hệ thống, mã nguồn và tài liệu. |

Các đợt thanh toán gắn với kết quả xác nhận M1–M4 tại mục 7\. Đại diện nhà trường tham gia các đợt dùng thử theo kế hoạch để kiểm tra luồng nghiệp vụ và phản hồi trong quá trình phát triển. Phản hồi được tổng hợp qua đầu mối của mỗi bên để thống nhất nội dung xử lý.

# **6 Cơ sở giá và tiến độ**

Giá đề xuất áp dụng cho phần In Scope trong mục 2, sản phẩm bàn giao tại mục 4 và các giả định tại mục 3\. Báo giá chi tiết đi kèm thỏa thuận triển khai sẽ thể hiện hạng mục, khối lượng, effort và đơn giá bán để hai bên đối chiếu với các đầu ra tương ứng.

Lịch 23 tuần được xây dựng theo các giai đoạn và mốc M1–M4 tại mục 5\. Đầu vào nghiệp vụ, nhịp phản hồi, môi trường triển khai và thời gian tham gia nghiệm thu được lập kế hoạch theo A-02, A-03, A-05 và A-07.

Nếu dữ kiện thực tế khác một giả định và làm tăng khối lượng hoặc thay đổi công việc phụ thuộc, PM xác định phần bị ảnh hưởng, tác động tới giá và lịch, rồi trình phương án để hai bên xác nhận trước khi thực hiện phần phát sinh. Các công việc đáp ứng đủ điều kiện đầu vào tiếp tục theo kế hoạch đã thống nhất.

# **7 Giá đề xuất và thanh toán**

## **Giá trị đầu tư**

**Giá đề xuất triển khai UniSupport là 700.000.000 VNĐ**, áp dụng cho phần In Scope trong mục 2, các assumptions tại mục 3 và sản phẩm bàn giao tại mục 4\.

Khoản đầu tư bao gồm toàn bộ chu kỳ phân tích, thiết kế, phát triển, tích hợp, kiểm thử, sửa lỗi thuộc phạm vi, chuẩn bị triển khai, tài liệu, hướng dẫn sử dụng, bàn giao và bảo hành phần mềm 30 ngày. Nhà trường nhận hệ thống cùng mã nguồn và tài liệu để tiếp nhận sản phẩm, với một đầu mối phụ trách xuyên suốt quá trình triển khai.

## **Điều kiện áp dụng giá**

Các điều kiện áp dụng tại mục 6 là căn cứ đối chiếu phương án thương mại. Khi nhà trường đề nghị điều chỉnh ngân sách, hai bên xem xét phạm vi, đầu ra hoặc lộ trình tương ứng và xác nhận phương án cập nhật cùng báo giá. Các yêu cầu bổ sung sau khi xác nhận phạm vi được xử lý theo mục 9\.

Hạng mục, khối lượng và giá được thể hiện trong báo giá chi tiết đi kèm thỏa thuận triển khai. Hạ tầng, giấy phép và dịch vụ được ghi theo môi trường, thời hạn sử dụng và bên cung cấp để hai bên xác nhận chi phí áp dụng. Điều kiện thuế, hiệu lực báo giá, hồ sơ và hạn thanh toán từng đợt được thống nhất khi chốt báo giá và hợp đồng.

## **Các đợt thanh toán dự kiến**

| Đợt | Căn cứ thanh toán | Tỷ lệ | Giá trị VNĐ |
| :---: | ----- | :---: | ----- |
| Khởi động | Khi hai bên xác nhận thỏa thuận khởi động | 30% | 210.000.000 |
| M1 | Xác nhận Prototype và khóa phạm vi | 20% | 140.000.000 |
| M2 | Xác nhận tích hợp và kiểm thử hệ thống | 20% | 140.000.000 |
| M3 | Xác nhận sẵn sàng Go-live | 20% | 140.000.000 |
| M4 | Xác nhận Go-live và bàn giao | 10% | 70.000.000 |
| **Tổng** |  | **100%** | **700.000.000** |

Khoản tạm ứng khởi động được dùng để huy động nguồn lực triển khai. Các đợt tiếp theo căn cứ vào hồ sơ xác nhận mốc tương ứng. Hồ sơ và hạn thanh toán cụ thể được ghi trong thỏa thuận của hai bên.

# **8 Nghiệm thu bàn giao và bảo hành**

## **Điều kiện nghiệm thu đề xuất**

Tại mỗi mốc, Project Team gửi hồ sơ để đại diện được Aurora University ủy quyền kiểm tra và xác nhận. PM điều phối việc bàn giao và phản hồi. QA xác nhận kết quả kiểm tra, Tech Lead xác nhận mức sẵn sàng kỹ thuật trước khi trình khách hàng. Hai bên thống nhất áp dụng các điều kiện sau.

1\. PM gửi thông báo sẵn sàng kèm mã phiên bản, phạm vi bàn giao, tiêu chí nghiệm thu áp dụng và tài liệu liên quan. Tại M1 dùng hồ sơ phạm vi và Prototype. Từ M2 dùng thêm hồ sơ kiểm thử và danh sách lỗi của phiên bản tương ứng.

2\. Aurora University kiểm tra theo kịch bản đã thống nhất trên dữ liệu giả lập. Phản hồi nêu yêu cầu hoặc tiêu chí chưa đáp ứng và bằng chứng quan sát. Kết quả được gửi trong 5 ngày làm việc kể từ khi nhận đủ hồ sơ sẵn sàng kiểm tra.

3\. QA và Tech Lead phân tích lỗi thuộc phạm vi. Đội dự án sửa, kiểm tra lại và thực hiện hồi quy các luồng bị ảnh hưởng trước khi gửi lại. PM cùng trường thống nhất lịch kiểm tra lại.

4\. Tại M2 và trước bàn giao cuối, các lỗi làm ngưng hệ thống, gây truy cập trái phép dữ liệu hoặc cản trở luồng nghiệp vụ chính phải được khắc phục và kiểm tra lại. Các lỗi còn lại được hai bên đánh giá theo tiêu chí chấp nhận đã thống nhất. Lỗi nhỏ được ghi vào danh sách theo dõi kèm người xử lý và hạn khắc phục khi hai bên đồng ý.

5\. Khi đáp ứng điều kiện, đại diện trường ký xác nhận mốc hoặc biên bản bàn giao. Phản hồi từ chối cần nêu bằng văn bản yêu cầu hoặc tiêu chí chưa đáp ứng, kết quả quan sát và bằng chứng liên quan. Yêu cầu chức năng mới hoặc thay đổi phạm vi được đánh giá theo mục 9\.

6\. Nếu quá 5 ngày làm việc chưa có phản hồi, PM liên hệ đầu mối nhà trường, ghi nhận tác động tới công việc phụ thuộc và thống nhất lịch kiểm tra tiếp theo. Việc nghiệm thu được xác nhận bằng văn bản của đại diện có thẩm quyền.

Phạm vi kiểm tra và tiêu chí chấp nhận của từng chức năng được hai bên xác nhận trong PRD tại M1. Kết quả nghiệm thu được đối chiếu với các tiêu chí đã thống nhất và bản bàn giao cụ thể.

## **Nội dung bàn giao**

Tại M4, hai bên kiểm tra hệ thống chính thức, mã nguồn, tài liệu kỹ thuật, HDSD, hướng dẫn vận hành và danh mục cấu hình cần chuyển giao. Kết quả triển khai và kiểm tra sau triển khai phải gắn với phiên bản cụ thể. Quyền truy cập và thông tin cấu hình được chuyển qua kênh thống nhất. Không đưa bí mật truy cập vào tài liệu công khai. PM lưu biên bản với đại diện nhận bàn giao của trường.

## **Bảo hành phần mềm**

Thời gian bảo hành là 30 ngày kể từ ngày ký biên bản nghiệm thu và bàn giao. Đội dự án tiếp nhận, phân loại và khắc phục lỗi khiến chức năng đã bàn giao không đáp ứng phạm vi và tiêu chí đã xác nhận. Chức năng mới, thay đổi nghiệp vụ và hoạt động vận hành lâu dài cần thỏa thuận riêng.

Thời hạn xử lý Ticket nghiệp vụ của trường khác với thời gian phản hồi hoặc sửa lỗi phần mềm. Người tiếp nhận, kênh liên hệ, thời gian phản hồi và cách xác định hạn khắc phục được hai bên chốt trong phương án bảo hành trước bàn giao. Sau bảo hành, nhà trường chỉ định bên vận hành theo thỏa thuận riêng.

# **9 Quản lý thay đổi và thống nhất triển khai**

## **Phối hợp xử lý rủi ro**

Hai bên phối hợp nhận diện những yếu tố có thể ảnh hưởng phạm vi, chất lượng và tiến độ, đặc biệt là thay đổi nghiệp vụ, chậm cung cấp thông tin, điều kiện hạ tầng và lịch tham gia nghiệm thu. Khi phát hiện ảnh hưởng, PM trao đổi với đầu mối nhà trường về mức tác động, biện pháp xử lý và thời điểm cần quyết định.

Project Team tổ chức kiểm thử tích hợp, phân quyền và hồi quy trong các giai đoạn phát triển. Trước Go-live, hai bên kiểm tra điều kiện môi trường, lịch người tham gia, hồ sơ bàn giao và phương án khôi phục để thống nhất việc triển khai.

## **Xử lý yêu cầu thay đổi**

Khi một bên đề xuất thay đổi phạm vi, giá hoặc mốc đã xác nhận, PM ghi nhận thành yêu cầu thay đổi có mã theo dõi. Đội dự án đánh giá tác động tới chức năng, khối lượng, chi phí, tiến độ, nguồn lực, rủi ro và kiểm thử, sau đó gửi phương án để Aurora University xem xét.

Đại diện có thẩm quyền của hai bên xác nhận bằng văn bản quyết định chấp thuận, từ chối hoặc hoãn. Với thay đổi được chấp thuận, PM cập nhật phạm vi, báo giá, kế hoạch, tiêu chí nghiệm thu và thông báo lịch thực hiện cho các bên liên quan.

## **Nội dung thống nhất khi chốt triển khai**

* Phạm vi chức năng tại mục 2, assumptions tại mục 3 và sản phẩm bàn giao tại mục 4\.  
* Giá và báo giá chi tiết, điều kiện thuế, hiệu lực báo giá và các đợt thanh toán.  
* Ngày khởi động, lịch triển khai 23 tuần và thời điểm tham gia review, nghiệm thu, đào tạo.  
* Hạ tầng, dịch vụ Email, giấy phép và trách nhiệm cung cấp của mỗi bên.  
* Tiêu chí nghiệm thu, đầu mối xác nhận, nội dung chuyển giao và phương án bảo hành.

## **Đại diện làm việc của hai bên**

| Bên tham gia | Trách nhiệm phối hợp |
| ----- | ----- |
| Project Team UniSupport | Cử PM làm đầu mối, trình phương án triển khai và cung cấp hồ sơ bàn giao để nhà trường xem xét. |
| Aurora University  | Cử đại diện có thẩm quyền thống nhất nghiệp vụ, điều kiện thương mại, lịch phối hợp và kết quả nghiệm thu. |

Sau khi thống nhất các nội dung trên, hai bên xác nhận thỏa thuận triển khai và tổ chức khởi động dự án theo lịch đã chốt.

