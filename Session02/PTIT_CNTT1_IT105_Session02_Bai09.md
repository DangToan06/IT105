## Đề cương Tài liệu SRS: Hệ thống Đặt món ăn tại quán
### 1. Mở đầu

- 1.1. Mục đích (Purpose): Mô tả mục tiêu của tài liệu này là xác định chi tiết các yêu cầu chức năng và phi chức năng cho "Hệ thống Đặt món ăn tại quán", làm cơ sở cho việc thiết kế, phát triển và kiểm thử.

- 1.2. Phạm vi (Scope): Xác định hệ thống sẽ cho phép khách hàng xem thực đơn, đặt món và thanh toán tại bàn thông qua thiết bị di động. Hệ thống cũng hỗ trợ nhân viên quản lý đơn hàng và báo cáo doanh thu.

- 1.3. Định nghĩa, Từ viết tắt (Definitions & Acronyms): Liệt kê và giải thích các thuật ngữ như "POS" (Point of Sale), "QR Code", "Order", "Bill" để đảm bảo mọi người hiểu thống nhất.

- 1.4. Tài liệu tham khảo (References): Danh sách các tài liệu liên quan như bản khảo sát yêu cầu khách hàng, tài liệu thiết kế giao diện (UI/UX), quy trình vận hành của nhà hàng.

- 1.5. Tổng quan tài liệu (Document Overview): Tóm tắt ngắn gọn cấu trúc của các phần còn lại trong tài liệu SRS này.

### 2. Mô tả tổng quan

- 2.1. Bối cảnh sản phẩm (Product Perspective): Mô tả hệ thống là một giải pháp độc lập, tích hợp với máy in hóa đơn và hệ thống máy POS hiện có của nhà hàng để đồng bộ dữ liệu.

- 2.2. Chức năng chính (Product Functions): Tóm tắt các chức năng cốt lõi: Quét mã QR tại bàn, xem thực đơn điện tử, tạo và gửi đơn hàng, thanh toán trực tuyến, quản lý đơn hàng cho nhân viên.

- 2.3. Đặc điểm người dùng (User Characteristics): Xác định các nhóm người dùng chính: Khách hàng (không cần kỹ năng đặc biệt), Nhân viên Phục vụ (cần được đào tạo cơ bản), Nhân viên Bếp (chỉ xem đơn), và Quản lý (truy cập mọi tính năng).

- 2.4. Các ràng buộc (Constraints): Liệt kê các giới hạn kỹ thuật và nghiệp vụ, ví dụ: hệ thống phải chạy trên nền tảng web (web-app), phải tích hợp với cổng thanh toán VNPay, và phải tuân thủ quy định về xuất hóa đơn điện tử.

- 2.5. Giả định và Phụ thuộc (Assumptions & Dependencies): Nêu các giả định như nhà hàng đã có sẵn mạng Wi-Fi ổn định cho khách và hệ thống phụ thuộc vào dịch vụ của bên thứ ba (cổng thanh toán, dịch vụ SMS).

### 3. Yêu cầu cụ thể

- 3.1. Yêu cầu chức năng (Functional Requirements):

    - FR1: Quản lý Bàn ăn & QR Code

        - Hệ thống cho phép Quản lý tạo, sửa, xóa bàn và gán một mã QR duy nhất cho mỗi bàn.

    - FR2: Quản lý Thực đơn (Menu)

        - Quản lý có thể thêm, sửa, xóa món ăn, cập nhật giá, hình ảnh, mô tả và trạng thái (còn món/hết món).

    - FR3: Quy trình Đặt món của Khách hàng

        - Khách hàng quét mã QR để truy cập thực đơn, chọn món, điều chỉnh số lượng và gửi đơn hàng đến bếp mà không cần đăng nhập.

    - FR4: Quản lý Đơn hàng (Order)

        - Nhân viên Bếp nhận đơn hàng mới trên màn hình hiển thị. Nhân viên Phục vụ có thể xem trạng thái các đơn hàng theo từng bàn.

    - FR5: Thanh toán

        - Hệ thống cho phép khách hàng yêu cầu thanh toán. Nhân viên Phục vụ xác nhận và hệ thống tạo hóa đơn, hỗ trợ thanh toán bằng tiền mặt hoặc qua cổng thanh toán trực tuyến.

    - FR6: Báo cáo

        - Quản lý có thể xem các báo cáo về doanh thu theo ngày/tuần/tháng và thống kê các món ăn bán chạy nhất.

- 3.2. Yêu cầu phi chức năng (Non-functional Requirements):

    - NFR1: Hiệu năng (Performance):

        - Thời gian tải thực đơn không quá 3 giây. Hệ thống phải xử lý được 50 đơn hàng được tạo đồng thời trong giờ cao điểm.

    - NFR2: Bảo mật (Security):

        - Thông tin thanh toán của khách hàng phải được mã hóa. Dữ liệu hệ thống phải được bảo vệ chống truy cập trái phép.

    - NFR3: Tính khả dụng (Availability):

        - Hệ thống phải hoạt động 99.5% thời gian trong giờ mở cửa của nhà hàng.

    - NFR4: Tính dễ sử dụng (Usability):

        - Giao diện cho khách hàng phải cực kỳ đơn giản, trực quan, không yêu cầu hướng dẫn sử dụng.

- 3.3. Yêu cầu về giao diện bên ngoài (External Interface Requirements):

    - 3.3.1. Giao diện người dùng (User Interfaces):

        - Mô tả sơ bộ về giao diện trên thiết bị di động của khách và giao diện quản lý trên máy tính bảng/PC của nhân viên.

    - 3.3.2. Giao diện phần cứng (Hardware Interfaces):

        - Hệ thống phải có khả năng giao tiếp và gửi lệnh in đến máy in hóa đơn qua mạng LAN.

    - 3.3.3. Giao diện phần mềm (Software Interfaces):

        - Mô tả chi tiết cách hệ thống tích hợp với API của cổng thanh toán (ví dụ: VNPay, MoMo) để xử lý giao dịch.