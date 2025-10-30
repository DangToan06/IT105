# Liệt kê , mô tả vai trò

- **Khách hàng**: Action

- **Vai trò**:

    - Đây là người dùng cuối, là một thực thể nằm ngoài hệ thống phần mềm của bạn.

    - Khách hàng là người bắt đầu chuỗi tương tác. Ví dụ: Khách hàng gửi yêu cầu "Xem sản phẩm" hoặc "Thanh toán đơn hàng" đến Website. Trong sơ đồ, Actor thường được đặt ở vị trí ngoài cùng bên trái.

- **Website**: Object

- **Vai trò**:

    - Đây là một thành phần nằm bên trong hệ thống mà Actor tương tác trực tiếp.

    - Website đóng vai trò trung gian, nhận yêu cầu từ Khách hàng, xử lý các logic nghiệp vụ (như quản lý giỏ hàng, hiển thị thông tin) và gọi đến các Object khác khi cần.

- **Hệ thống thanh toáne**: Object

- **Vai trò**:

    - Đây cũng là một thành phần nằm bên trong hệ thống, chuyên thực hiện một nhiệm vụ cụ thể.

    - Hệ thống thanh toán nhận yêu cầu xử lý giao dịch từ Website, thực hiện việc thanh toán (ví dụ: kết nối với ngân hàng), và sau đó trả kết quả (thành công hay thất bại) ngược lại cho Website.