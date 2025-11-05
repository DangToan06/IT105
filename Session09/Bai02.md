### Bảng so sánh ERD và Class Diagram

| Tiêu chí | ERD (Entity Relationship Diagram - Sơ đồ quan hệ thực thể) | Class Diagram (Sơ đồ lớp) |
| :--- | :--- | :--- |
| **Mục đích** | Mô hình hóa cấu trúc **dữ liệu** của hệ thống. Dùng để thiết kế cơ sở dữ liệu quan hệ, tập trung vào *cái gì* được lưu trữ. | Mô hình hóa cấu trúc **tĩnh (static)** của một hệ thống hướng đối tượng. Dùng để thiết kế phần mềm, tập trung vào *hành vi* và *cấu trúc* của các đối tượng. |
| **Thành phần chính** | 1. **Thực thể** (Entity): Đối tượng trong thế giới thực (ví dụ: Sách, Khách hàng).<br>2. **Thuộc tính** (Attribute): Đặc điểm của thực thể (ví dụ: Tên sách, Địa chỉ).<br>3. **Mối quan hệ** (Relationship): Sự liên kết giữa các thực thể. | 1. **Lớp** (Class): Khuôn mẫu cho các đối tượng (ví dụ: Class Sach, Class KhachHang).<br>2. **Thuộc tính** (Attribute): Dữ liệu của lớp.<br>3. **Phương thức** (Method/Operation): Hành vi hoặc chức năng của lớp (ví dụ: `tinhTongTien()`, `themSach()`). |
| **Cách biểu diễn mối quan hệ** | Sử dụng **Bản số** (Cardinality) để chỉ số lượng. <br> * Ký hiệu: Một-Một (1:1), Một-Nhiều (1:N), Nhiều-Nhiều (M:N).<br> * Ký hiệu phổ biến: Chân quạ (Crow's Foot). | Sử dụng **Bội số** (Multiplicity) để chỉ số lượng (ví dụ: 1, 0..1, 1..*, \*).<br> * Bao gồm nhiều loại quan hệ hơn:<br> * **Association** (Liên kết)<br> * **Aggregation** (Tập hợp - "có một")<br> * **Composition** (Thành phần - "sở hữu")<br> * **Inheritance/Generalization** (Thừa kế - "là một") |
| **Sử dụng trong giai đoạn nào của dự án** | Chủ yếu trong giai đoạn **Phân tích yêu cầu (dữ liệu)** và **Thiết kế cơ sở dữ liệu** (Database Design). | Chủ yếu trong giai đoạn **Phân tích hướng đối tượng** (OOA) và **Thiết kế hướng đối tượng** (OOD). |
| **Ví dụ** | Trong hệ thống bán sách, thực thể `SACH` và `TACGIA` có quan hệ Nhiều-Nhiều. Điều này dẫn đến việc tạo ra bảng trung gian `SACH_TACGIA` trong CSDL. | Lớp `DonHang` *bao gồm* (Aggregation) một danh sách các đối tượng `ChiTietDonHang`. Lớp `SachGiaoKhoa` và `TieuThuyet` *thừa kế* (Inheritance) từ lớp cha `Sach`. |



---