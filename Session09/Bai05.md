### Phân tích các kiểu quan hệ (Relationship Types)

| Tình huống | Thực thể 1 | Thực thể 2 | Kiểu quan hệ | Giải thích |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **Sinh Viên** | **Mã Sinh Viên** | **1-1 (Một-Một)** | Một sinh viên chỉ sở hữu *một* mã sinh viên duy nhất, và một mã sinh viên đó cũng chỉ thuộc về *một* sinh viên duy nhất. (Trong thiết kế CSDL, `Mã Sinh Viên` thường là *thuộc tính khóa chính* của thực thể `Sinh Viên` thay vì là một thực thể riêng). |
| 2 | **Khách Hàng** | **Đơn Hàng** | **1-N (Một-Nhiều)** | Một khách hàng (1) có thể có *nhiều* đơn hàng (N). Nhưng một đơn hàng cụ thể chỉ thuộc về *một* khách hàng (1). |
| 3 | **Sinh Viên** | **Môn Học** | **N-N (Nhiều-Nhiều)** | Một sinh viên (N) có thể đăng ký học *nhiều* môn học (N). Ngược lại, một môn học (N) cũng có *nhiều* sinh viên (N) tham gia. (Quan hệ này khi triển khai CSDL sẽ cần một bảng trung gian, ví dụ: `DANG_KY_HOC`). |



---