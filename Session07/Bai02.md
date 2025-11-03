## 1. Thiết kế Kiến trúc 3 Tầng

###  Presentation Tier (Tầng Giao diện/Trình bày)

* **Mục đích:** Cung cấp giao diện người dùng (UI) và xử lý tương tác với người dùng. Đây là nơi người dùng cuối trực tiếp tương tác với hệ thống.
* **Công nghệ ví dụ:**
    * **Web:** React.
    * **Mobile:** Native (Swift/Kotlin) .
* **Các thành phần chính:**
    * **User Interface (UI):** Các màn hình/trang để thực hiện các nghiệp vụ:
        * Màn hình Quản lý Sản phẩm (Thêm, Sửa, Xóa).
        * Màn hình Quản lý Nhà cung cấp.
        * Màn hình Nhập kho, Xuất kho.
        * Màn hình Báo cáo Tồn kho.
    * **Input Validation:** Kiểm tra dữ liệu đầu vào cơ bản (ví dụ: không để trống, đúng định dạng) trước khi gửi yêu cầu xuống tầng Business Logic.
    * **Communication:** Gửi yêu cầu (thường là qua **API/HTTP**) đến Business Logic Tier và hiển thị kết quả trả về.

---

### Business Logic Tier (Tầng Logic Nghiệp vụ/Ứng dụng)

* **Mục đích:** Chứa tất cả các quy tắc, quy trình và logic nghiệp vụ cốt lõi của hệ thống. Tầng này nhận yêu cầu từ Presentation Tier, xử lý, và điều phối tương tác với Data Access Tier.
* **Công nghệ ví dụ:** Các ngôn ngữ lập trình Backend Java/Spring Boot, Note.js.
* **Các thành phần chính:**
    * **Business Objects/Services:** Các lớp/module thực hiện logic nghiệp vụ:
        * **ProductService:** Chứa logic để **thêm** sản phẩm (kiểm tra SKU trùng lặp, tạo ID), **sửa** (kiểm tra quyền hạn), **xóa** (kiểm tra sản phẩm có còn trong đơn hàng chưa hoàn thành không).
        * **SupplierService:** Logic quản lý thông tin nhà cung cấp và đơn đặt hàng.
        * **InventoryService:** Logic **tính toán tồn kho** (sau khi nhập, số lượng tăng; sau khi xuất, số lượng giảm), kiểm tra **sản phẩm có đủ để xuất không**.
    * **Transaction Management:** Đảm bảo các thao tác nghiệp vụ (như Nhập/Xuất kho) được thực hiện thành công toàn bộ hoặc không thực hiện gì cả (tính chất **ACID**).
    * **API/Controller:** Điểm cuối (endpoints) nhận yêu cầu từ Presentation Tier và gọi các Service tương ứng.

---

### Data Access Tier (Tầng Truy cập Dữ liệu/Nguồn dữ liệu)

* **Mục đích:** Quản lý việc lưu trữ, truy xuất, cập nhật và xóa dữ liệu (CRUD operations) trong cơ sở dữ liệu. Tầng này cô lập logic nghiệp vụ khỏi chi tiết kỹ thuật của cơ sở dữ liệu.
* **Công nghệ ví dụ:**
    * **Database:** MySQL, SQL Server.
    * **Frameworks/Libraries:** ORM (Hibernate/JPA, Entity Framework, Sequelize), JDBC/ADO.NET.
* **Các thành phần chính:**
    * **Data Access Objects (DAO) / Repositories:** Các lớp chịu trách nhiệm trực tiếp giao tiếp với CSDL:
        * **ProductDAO/Repository:** Chứa các phương thức SQL/ORM để `saveProduct(..), findProductById(..), updateProduct(..), deleteProduct(..),` v.v.
        * **SupplierDAO/Repository.**
        * **InventoryLogDAO/Repository** (Lưu trữ các bản ghi Nhập/Xuất kho).
    * **Data Models (Entities/POJOs):** Đại diện cho cấu trúc dữ liệu trong CSDL (ví dụ: lớp `Product` có các trường `id`, `name`, `sku`, `current_stock`).
    * **Connection Management:** Quản lý các kết nối đến CSDL.

---

## 2. Sơ đồ Package/Lớp (Logic)

| Package (Gói) | Mô tả Chi tiết | Ví dụ Lớp/Thành phần |
| :--- | :--- | :--- |
| **com.inventory.presentation** | Tầng giao diện (Được triển khai độc lập, giao tiếp qua API) | UI/UX Web/Mobile |
| **com.inventory.api** | Controller, điểm nhận API từ Presentation Tier | `ProductController`, `InventoryController` |
| **com.inventory.service** | **Tầng Business Logic:** Chứa logic nghiệp vụ | `ProductService`, `InventoryService`, `SupplierService` |
| **com.inventory.model** | Các đối tượng dữ liệu được sử dụng trong toàn bộ ứng dụng | `Product`, `Supplier`, `InventoryLog` |
| **com.inventory.repository** | **Tầng Data Access:** Giao tiếp với CSDL | `ProductRepository`, `SupplierRepository`, `InventoryLogRepository` |
| **com.inventory.exception** | Các lớp xử lý lỗi nghiệp vụ và hệ thống | `ResourceNotFoundException`, `InsufficientStockException` |