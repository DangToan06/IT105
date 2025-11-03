# Hệ thống blog cá nhân

## 1. Phân rã theo 3 tầng
![alt text](Bai05(1).png)
## 2. Các module chính

### Presentation

| Module                | Chức năng                                                 |
| --------------------- | --------------------------------------------------------- |
| **PostController**    | Giao tiếp với client để tạo, xem, chỉnh sửa, xóa bài viết |
| **CommentController** | Quản lý bình luận (thêm, sửa, xóa)                        |
| **UserController**    | Đăng ký, đăng nhập, phân quyền người dùng                 |


### Business Logic

| Module             | Chức năng                                                    |
| ------------------ | ------------------------------------------------------------ |
| **PostService**    | Xử lý logic bài viết (tạo bài, cập nhật, hiển thị, tìm kiếm) |
| **CommentService** | Quản lý logic liên quan đến bình luận                        |
| **UserService**    | Quản lý người dùng, xác thực đăng nhập, mã hóa mật khẩu      |

### Data Access

| Module                | Chức năng                                     |
| --------------------- | --------------------------------------------- |
| **PostRepository**    | Thực hiện CRUD bài viết                       |
| **CommentRepository** | CRUD bình luận                                |
| **UserRepository**    | CRUD thông tin người dùng, xác thực tài khoản |

## 3. Vẽ sơ đồ lớp
![alt text](Bai05(2).png)
