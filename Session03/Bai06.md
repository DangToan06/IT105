# Use Case Description: Đặt hàng

**Tên Use Case:** Đặt hàng (Place Order)

**Actor (Các bên tham gia):**
* **Primary Actor:** Khách hàng (Customer)
* **Supporting Actors:** Hệ thống (System), Nhà hàng (Restaurant)

**Mục tiêu (Goal):**
Khách hàng chọn món ăn từ một nhà hàng, cung cấp thông tin giao hàng và hoàn tất quy trình để tạo một đơn hàng thành công trên hệ thống.

---

### Luồng chính (Main Flow / Happy Path)

Đây là kịch bản diễn ra khi mọi thứ đều thành công và không có lỗi nào xảy ra.

1.  Khách hàng chọn một nhà hàng, xem thực đơn và thêm các món ăn mong muốn vào giỏ hàng.
2.  Khách hàng truy cập vào giỏ hàng và chọn "Thanh toán".
3.  Hệ thống hiển thị màn hình xác nhận đơn hàng, bao gồm: danh sách món ăn, tổng số tiền, phí giao hàng, địa chỉ nhận hàng mặc định và các phương thức thanh toán khả dụng.
4.  Khách hàng kiểm tra lại thông tin, xác nhận địa chỉ và chọn một phương thức thanh toán (ví dụ: "Tiền mặt khi nhận hàng").
5.  Khách hàng bấm nút **"Đặt hàng"**.
6.  Hệ thống ghi nhận yêu cầu, tạo một đơn hàng với trạng thái "Chờ xác nhận" và gửi thông tin đơn hàng đến cho Nhà hàng.
7.  Nhà hàng nhận và xác nhận đơn hàng.
8.  Hệ thống cập nhật trạng thái đơn hàng thành "Đang chuẩn bị" và gửi thông báo đặt hàng thành công cho Khách hàng.
9.  Use Case kết thúc thành công.

---

### Luồng lỗi (Error Flows / Alternative Paths)

Đây là các kịch bản xảy ra khi có sự cố hoặc điều kiện ngoại lệ.

**Luồng lỗi A: Món ăn trong giỏ hàng đã hết**

*Xảy ra tại bước 3 của Luồng chính.*

1.  Hệ thống kiểm tra và phát hiện một hoặc nhiều món trong giỏ hàng không còn khả dụng tại nhà hàng.
2.  Hệ thống hiển thị thông báo cho Khách hàng về (các) món ăn đã hết.
3.  Hệ thống yêu cầu Khách hàng xóa món ăn đó khỏi giỏ hàng để có thể tiếp tục.
4.  Khách hàng quay lại màn hình giỏ hàng (Luồng chính, bước 2).

**Luồng lỗi B: Nhà hàng từ chối đơn hàng**

*Xảy ra tại bước 7 của Luồng chính.*

1.  Nhà hàng từ chối đơn hàng (lý do: quá tải, hết nguyên liệu, sắp đóng cửa, v.v.).
2.  Hệ thống nhận được thông báo từ chối.
3.  Hệ thống cập nhật trạng thái đơn hàng thành "Đã hủy".
4.  Hệ thống gửi thông báo cho Khách hàng rằng đơn hàng đã bị nhà hàng hủy.
5.  (Nếu đã thanh toán online) Hệ thống tự động bắt đầu quy trình hoàn tiền cho Khách hàng.
6.  Use Case kết thúc thất bại.

**Luồng lỗi C: Thanh toán online thất bại**

*Xảy ra tại bước 5 của Luồng chính nếu khách hàng chọn thanh toán online.*

1.  Hệ thống chuyển hướng người dùng đến cổng thanh toán nhưng giao dịch không thành công (sai thông tin thẻ, không đủ tiền, v.v.).
2.  Hệ thống nhận được phản hồi lỗi từ cổng thanh toán.
3.  Hệ thống hiển thị thông báo "Thanh toán thất bại" cho Khách hàng.
4.  Hệ thống đề nghị Khách hàng thử lại hoặc chọn một phương thức thanh toán khác (quay lại Luồng chính, bước 4).