# Hệ thống Quản lý Bệnh viện

## 1. Người dùng (Users)

- **Các nhóm người dùng**: Bác sĩ, y tá, dược sĩ, nhân viên lễ tân, kỹ thuật viên xét nghiệm, quản lý bệnh viện, và cả bệnh nhân (qua cổng thông tin).

- **Tác động đến yêu cầu**:

    - **Phân quyền truy cập**: Hệ thống phải có cơ chế phân quyền chi tiết. Ví dụ, bác sĩ có thể xem bệnh án và ra y lệnh, nhưng không thể xem báo cáo tài chính; lễ tân chỉ có thể tạo lịch hẹn và quản lý thông tin hành chính của bệnh nhân.

    - **Tính dễ sử dụng**: Giao diện phải được thiết kế riêng cho từng vai trò. Giao diện cho y tá và bác sĩ cần tối ưu hóa cho việc nhập liệu nhanh trên máy tính bảng hoặc thiết bị di động trong lúc đi thăm khám, trong khi giao diện cho quản lý cần tập trung vào các biểu đồ và báo cáo.

    - **Yêu cầu chức năng đa dạng**: Mỗi nhóm người dùng sẽ định hình các module chức năng khác nhau: module khám bệnh cho bác sĩ, module quản lý thuốc cho dược sĩ, module thanh toán viện phí cho lễ tân.

## 2. Phần cứng

- **Các loại phần cứng**: Máy tính tại quầy, máy tính bảng cho bác sĩ, máy in (hóa đơn, đơn thuốc, kết quả xét nghiệm), máy quét mã vạch (quản lý thuốc, định danh bệnh nhân), và quan trọng nhất là các thiết bị y tế chuyên dụng (máy X-quang, máy siêu âm, máy xét nghiệm máu) có khả năng xuất dữ liệu số.

- **Tác động đến yêu cầu**:

    - **Tích hợp thiết bị**: Hệ thống phải có khả năng nhận và lưu trữ dữ liệu từ các thiết bị y tế. Điều này đòi hỏi yêu cầu về việc hỗ trợ các chuẩn giao tiếp y tế phổ biến như HL7 hoặc DICOM (cho hình ảnh y khoa).

    - **Tính tương thích**: Giao diện người dùng phải hiển thị tốt trên nhiều kích thước màn hình khác nhau (responsive design), từ máy tính lớn đến máy tính bảng nhỏ.

    - **Yêu cầu hiệu năng**: Hệ thống máy chủ phải đủ mạnh để lưu trữ và xử lý một lượng lớn dữ liệu, đặc biệt là các tệp hình ảnh y khoa có dung lượng cao (như ảnh CT scan, MRI).

## 3. Phần mềm

- **Các loại phần mềm**: Hệ điều hành tại các máy trạm (thường là Windows), hệ quản trị cơ sở dữ liệu (ví dụ: SQL Server, Oracle), trình duyệt web.

- **Tác động đến yêu cầu**:

    - **Tương thích nền tảng**: Ứng dụng phải hoạt động ổn định trên hệ điều hành và trình duyệt tiêu chuẩn của bệnh viện.

    - **Yêu cầu về cơ sở dữ liệu**: CSDL phải có khả năng mở rộng (scalability) để xử lý lượng dữ liệu bệnh nhân tăng lên theo thời gian và phải có cơ chế sao lưu, phục hồi (backup & recovery) tin cậy để tránh mất mát dữ liệu y tế quan trọng.

## 4. Hệ thống bên ngoài

- **Các hệ thống cần kết nối**: Hệ thống của Bảo hiểm Y tế Quốc gia, Cổng dữ liệu của Bộ Y tế, các phòng khám hoặc bệnh viện khác (để chuyển tuyến), hệ thống của các phòng xét nghiệm bên ngoài, các cổng thanh toán không dùng tiền mặt.

- **Tác động đến yêu cầu**:

    - **Giao diện lập trình ứng dụng (API)**: Hệ thống bắt buộc phải có các API an toàn để trao đổi dữ liệu với các bên thứ ba. Ví dụ, API để gửi yêu cầu thanh toán và nhận kết quả từ cơ quan Bảo hiểm Y tế, hoặc API để gửi báo cáo định kỳ cho Bộ Y tế.

    - **Tiêu chuẩn dữ liệu**: Dữ liệu trao đổi phải tuân theo các định dạng và tiêu chuẩn do cơ quan quản lý nhà nước hoặc đối tác quy định để đảm bảo tính liên thông.

## 5. Quy trình nghiệp vụ

- **Các quy trình chính**: Quy trình đăng ký khám bệnh, quy trình khám và chẩn đoán, quy trình cấp phát thuốc, quy trình thanh toán và xuất viện, quy trình yêu cầu và trả kết quả xét nghiệm.

- **Tác động đến yêu cầu**:

    - **Luồng công việc**: Các yêu cầu chức năng của hệ thống phải được thiết kế để mô phỏng và tự động hóa các quy trình này. Ví dụ, khi bác sĩ tạo một y lệnh xét nghiệm trên hệ thống, yêu cầu này phải tự động được chuyển đến module của phòng xét nghiệm.

    - **Tích hợp module**: Các module chức năng không thể hoạt động riêng lẻ mà phải liên kết chặt chẽ với nhau để tạo thành một chu trình khép kín, từ lúc bệnh nhân vào viện đến lúc ra viện.

## 6. Luật lệ

- **Các quy định pháp lý**: Luật Khám bệnh, chữa bệnh; quy định của Bộ Y tế về việc triển khai bệnh án điện tử; Luật An ninh mạng; và đặc biệt là các quy định về bảo mật thông tin và quyền riêng tư của bệnh nhân.

- **Tác động đến yêu cầu**:

    - **Bảo mật**: Đây là yêu cầu phi chức năng quan trọng nhất. Hệ thống phải mã hóa dữ liệu nhạy cảm của bệnh nhân (cả khi lưu trữ và khi truyền đi).

    - **Nhật ký truy cập**: Hệ thống phải ghi lại mọi hành động truy cập, xem, sửa, xóa dữ liệu bệnh án, bao gồm thông tin về ai, lúc nào, và đã làm gì. Đây là yêu cầu bắt buộc để tuân thủ pháp luật và truy vết khi có sự cố.

    - **Lưu trữ dữ liệu**: Hệ thống phải tuân thủ các quy định về thời gian lưu trữ hồ sơ bệnh án theo yêu cầu của pháp luật.