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

- Các loại phần mềm: Hệ điều hành tại các máy trạm (thường là Windows), hệ quản trị cơ sở dữ liệu (ví dụ: SQL Server, Oracle), trình duyệt web.

Tác động đến yêu cầu:

Tương thích nền tảng: Ứng dụng phải hoạt động ổn định trên hệ điều hành và trình duyệt tiêu chuẩn của bệnh viện.

Yêu cầu về cơ sở dữ liệu: CSDL phải có khả năng mở rộng (scalability) để xử lý lượng dữ liệu bệnh nhân tăng lên theo thời gian và phải có cơ chế sao lưu, phục hồi (backup & recovery) tin cậy để tránh mất mát dữ liệu y tế quan trọng.