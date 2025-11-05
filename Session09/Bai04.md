### Phân tích thuộc tính các thực thể

| Entity | Attribute | Kiểu dữ liệu | Vai trò |
| :--- | :--- | :--- | :--- |
| **User** | UserID | Integer | Khóa chính, định danh duy nhất cho mỗi người dùng. |
| **User** | HoTen | String | Lưu trữ tên đầy đủ của người dùng. |
| **User** | Email | String | Dùng để đăng nhập, liên lạc (thường là duy nhất). |
| **User** | MatKhau | String (Hashed) | Lưu mật khẩu đã mã hóa để xác thực người dùng. |
| **User** | VaiTro | String / Enum | Phân biệt người dùng là 'Học viên' hay 'Giảng viên'. |
| **Course** | CourseID | Integer  | Khóa chính, định danh duy nhất cho mỗi khóa học. |
| **Course** | TenKhoaHoc | String | Tên hiển thị của khóa học. |
| **Course** | MoTa | Text | Cung cấp mô tả chi tiết về nội dung khóa học. |
| **Course** | GiaTien | Decimal | Chi phí mà người dùng phải trả để tham gia khóa học. |
| **Course** | GiangVienID | Integer  | Khóa ngoại, liên kết đến **User** (người có VaiTro là 'Giảng viên'). |
| **Enrollment** | EnrollmentID | Integer  | Khóa chính, định danh duy nhất cho một lượt đăng ký. |
| **Enrollment** | UserID | Integer  | Khóa ngoại, liên kết đến **User** (người học) đã đăng ký. |
| **Enrollment** | CourseID | Integer  | Khóa ngoại, liên kết đến **Course** mà người dùng đăng ký. |
| **Enrollment** | NgayDangKy | Datetime | Ghi lại thời điểm chính xác khi người dùng đăng ký. |
| **Enrollment** | TrangThai | String / Enum | Theo dõi tiến độ (ví dụ: 'Đang học', 'Đã hoàn thành', 'Đã hủy'). |