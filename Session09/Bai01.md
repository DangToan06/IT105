### Phân tích vai trò các thực thể

| Tên thực thể | Miêu tả vai trò |
| :--- | :--- |
| **Sách** | Là đối tượng chứa thông tin chi tiết về mỗi cuốn sách như tên sách, giá, mô tả, thể loại, năm xuất bản. Đây là sản phẩm chính mà hệ thống quản lý. |
| **Tác giả** | Lưu trữ thông tin về người viết sách (tên, tiểu sử, v.v.). Thực thể này liên kết với **Sách** để biết sách nào do ai viết. |
| **Khách hàng** | Lưu trữ thông tin cá nhân của người mua sách (tên, địa chỉ, email, điện thoại). Thực thể này dùng để quản lý giao dịch và lịch sử mua hàng. |
| **Đơn hàng** | Đại diện cho một giao dịch mua hàng của **Khách hàng**. Nó chứa thông tin chung như ngày đặt, tổng tiền, trạng thái đơn hàng và liên kết với khách hàng đã đặt. |
| **Chi tiết đơn hàng** | Là thực thể trung gian, kết nối **Đơn hàng** và **Sách**. Nó ghi rõ một đơn hàng cụ thể bao gồm những sách nào, số lượng bao nhiêu, và đơn giá tại thời điểm mua. |



---
