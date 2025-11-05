### Chuẩn hóa 1NF (First Normal Form)

**Quy tắc:** Loại bỏ các thuộc tính đa trị (repeating groups). Mỗi ô chỉ chứa một giá trị nguyên tử.

"Mở" cột `Danh sách sản phẩm` thành nhiều hàng, mỗi hàng cho một sản phẩm.

**Bảng 1NF:**
| Mã hóa đơn (PK) | Sản phẩm (PK) | Tên khách hàng | Số điện thoại | Tổng tiền |
| :--- | :--- | :--- | :--- | :--- |
| HD001 | Bút bi | An | 0912345678 | 50,000 |
| HD001 | Vở | An | 0912345678 | 50,000 |
| HD001 | Thước | An | 0912345678 | 50,000 |
| HD002 | Sách | Bình | 0987654321 | 80,000 |
| HD002 | Bút chì | Bình | 0987654321 | 80,000 |

* **Khóa chính (PK):** `(Mã hóa đơn, Sản phẩm)` (Vì `Mã hóa đơn` lặp lại).

---

### Chuẩn hóa 2NF (Second Normal Form)

**Quy tắc:** Phải ở 1NF. Loại bỏ các phụ thuộc hàm riêng phần (Partial Functional Dependency). Mọi thuộc tính không phải khóa phải phụ thuộc hoàn toàn vào *toàn bộ* khóa chính.

Trong Bảng 1NF, PK là `(Mã hóa đơn, Sản phẩm)`.
* `Tên khách hàng` chỉ phụ thuộc vào `Mã hóa đơn`.
* `Số điện thoại` chỉ phụ thuộc vào `Mã hóa đơn`.
* `Tổng tiền` chỉ phụ thuộc vào `Mã hóa đơn`.

Ba thuộc tính này không phụ thuộc vào `Sản phẩm`, do đó chúng vi phạm 2NF:

**Bảng 1: HoaDon (Hóa Đơn)**
| Mã hóa đơn (PK) | Tên khách hàng | Số điện thoại | Tổng tiền |
| :--- | :--- | :--- | :--- |
| HD001 | An | 0912345678 | 50,000 |
| HD002 | Bình | 0987654321 | 80,000 |

**Bảng 2: ChiTietHoaDon (Chi Tiết Hóa Đơn)**
| Mã hóa đơn (PK, FK) | Sản phẩm (PK) |
| :--- | :--- |
| HD001 | Bút bi |
| HD001 | Vở |
| HD001 | Thước |
| HD002 | Sách |
| HD002 | Bút chì |

---

### Chuẩn hóa 3NF (Third Normal Form)

**Quy tắc:** Phải ở 2NF. Loại bỏ các phụ thuộc hàm bắc cầu (Transitive Functional Dependency). Mọi thuộc tính không phải khóa phải phụ thuộc *trực tiếp* vào khóa chính.

Xử lý phụ thuộc bắc cầu trong bảng `HoaDon`:
`Mã hóa đơn` → `Số điện thoại` → `Tên khách hàng`

Chúng ta tách bảng `HoaDon` thành `KhachHang` và `HoaDon` (mới). Bảng `ChiTietHoaDon` đã ở 3NF nên giữ nguyên.

**Bảng 1: KhachHang (Khách Hàng)**
| Số điện thoại (PK) | Tên khách hàng |
| :--- | :--- |
| 0912345678 | An |
| 0987654321 | Bình |

**Bảng 2: HoaDon (Hóa Đơn)**
| Mã hóa đơn (PK) | Số điện thoại (FK) | Tổng tiền |
| :--- | :--- | :--- |
| HD001 | 0912345678 | 50,000 |
| HD002 | 0987654321 | 80,000 |

**Bảng 3: ChiTietHoaDon (Chi Tiết Hóa Đơn)**
| Mã hóa đơn (PK, FK) | Sản phẩm (PK) |
| :--- | :--- |
| HD001 | Bút bi |
| HD001 | Vở |
| HD001 | Thước |
| HD002 | Sách |
| HD002 | Bút chì |



**Kết quả:** Dữ liệu đã được chuẩn hóa 3NF.
* **Bảng KhachHang:** Lưu thông tin khách hàng.
* **Bảng HoaDon:** Lưu thông tin về giao dịch, liên kết với khách hàng qua `Số điện thoại` (FK).
* **Bảng ChiTietHoaDon:** Lưu thông tin các sản phẩm trong một hóa đơn, liên kết với hóa đơn qua `Mã hóa đơn` (FK).
