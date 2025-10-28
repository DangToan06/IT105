# App giao đồ ăn online

| Actor (Người dùng) | Loại Actor | Use Case Phục Vụ (Hành động chính) |
| :--- | :--- | :--- |
| **Khách hàng (Customer)** | **Primary** | - Đăng ký / Đăng nhập tài khoản<br>- Tìm kiếm nhà hàng / món ăn<br>- Đặt món ăn<br>- Thanh toán đơn hàng<br>- Theo dõi tình trạng đơn hàng<br>- Đánh giá nhà hàng / tài xế |
| **Tài xế (Driver)** | **Primary** | - Đăng ký / Đăng nhập tài khoản<br>- Nhận / Từ chối đơn hàng<br>- Xem thông tin đơn hàng (địa chỉ, món ăn)<br>- Cập nhật trạng thái đơn hàng<br>- Xem thu nhập |
| **Nhà hàng (Restaurant)** | **Primary** | - Đăng ký / Đăng nhập tài khoản<br>- Quản lý thực đơn (thêm/sửa/xóa món)<br>- Xác nhận / Từ chối đơn hàng<br>- Cập nhật trạng thái đơn hàng (đang chuẩn bị)<br>- Xem doanh thu |
| **Quản trị viên (Admin)** | **Primary** | - Quản lý người dùng<br>- Xem báo cáo thống kê<br>- Giải quyết khiếu nại |
| **Hệ thống thanh toán (Payment Gateway)** | **Secondary** | - Xử lý giao dịch thanh toán (VD: Momo, ZaloPay, thẻ ngân hàng) |
| **Dịch vụ bản đồ (Map Service)** | **Secondary** | - Cung cấp bản đồ và định vị (VD: Google Maps) |