# Bài 3

| Use Case A | Use Case B | Mối quan hệ | Giải thích |
| :--- | :--- | :--- | :--- |
| **Đặt hàng** | **Kiểm tra giỏ hàng** | `<<include>>` | Để có thể **Đặt hàng**, người dùng **bắt buộc** phải thực hiện hành động **Kiểm tra giỏ hàng** trước (để xem lại sản phẩm, số lượng, giá tiền). Hành động kiểm tra là một phần không thể thiếu của quy trình đặt hàng. |
| **Đặt hàng** | **Xem đánh giá** | **Association** (Liên kết) hoặc không có | Việc **Xem đánh giá** thường xảy ra trước khi người dùng quyết định mua và thêm sản phẩm vào giỏ hàng. Nó không phải là một phần bắt buộc (`include`) hay tùy chọn (`extend`) *trong lúc* thực hiện quy trình **Đặt hàng**. Do đó, chúng là hai Use Case độc lập mà Actor (Người mua) có thể thực hiện. |
| **Đặt hàng** | **Đề xuất hoá đơn** | `<<extend>>` | Chức năng **Đề xuất hoá đơn** (ví dụ: xuất hóa đơn đỏ cho công ty) là một hành động **tùy chọn**, không phải lúc nào người dùng cũng cần. Nó chỉ được thực hiện khi người dùng có yêu cầu cụ thể (ví dụ: tick vào ô "Xuất hóa đơn công ty"). Do đó, nó "mở rộng" cho chức năng **Đặt hàng**. |
