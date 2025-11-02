# Phân tích Yêu cầu Hệ thống Bán khóa học trực tuyến (E-learning)

## 1. Xác định Stakeholders
Dưới đây là bảng phân tích các bên liên quan chính (stakeholders) của hệ thống:

| Stakeholder | Vai trò | Nguồn yêu cầu |
| :--- | :--- | :--- |
| **Học viên (Student)** | Người dùng cuối, tham gia mua và học các khóa học. | Yêu cầu về tìm kiếm, thanh toán, trải nghiệm học tập, theo dõi tiến độ. |
| **Giảng viên (Instructor)** | Người tạo và quản lý nội dung khóa học. | Yêu cầu về việc tải lên video/tài liệu, tạo bài kiểm tra, quản lý học viên, xem thống kê. |
| **Quản trị viên (Admin)** | Người quản lý, vận hành toàn bộ hệ thống. | Yêu cầu về quản lý người dùng, duyệt khóa học, xử lý thanh toán, báo cáo tổng thể, cấu hình hệ thống. |
| **Chủ sở hữu hệ thống (Owner)**| Đơn vị đầu tư, quyết định chiến lược kinh doanh. | Yêu cầu về lợi nhuận, xây dựng thương hiệu, tích hợp đối tác, báo cáo doanh thu. |

---

## 2. Phân tích Yêu cầu

### 2.1. Yêu cầu chức năng (Functional Requirements)

Các yêu cầu chức năng được phân nhóm theo nghiệp vụ chính:

**A. Quản lý Người dùng (Chung)**
* **FR-01:** Hệ thống cho phép người dùng (học viên, giảng viên) đăng ký tài khoản mới.
* **FR-02:** Hệ thống cho phép người dùng đăng nhập bằng email/mật khẩu.
* **FR-03:** Hệ thống cho phép người dùng sử dụng chức năng "Quên mật khẩu".
* **FR-04:** Hệ thống cho phép người dùng (học viên, giảng viên) cập nhật thông tin cá nhân.
* **FR-05 (Admin):** Admin có quyền tạo, khóa, và xóa tài khoản người dùng.

**B. Quản lý Khóa học (Giảng viên & Admin)**
* **FR-06 (Giảng viên):** Giảng viên có thể tạo khóa học mới (nhập tiêu đề, mô tả, giá tiền, ảnh bìa).
* **FR-07 (Giảng viên):** Giảng viên có thể tải lên nội dung bài giảng (video, tài liệu PDF, text).
* **FR-08 (Giảng viên):** Giảng viên có thể tạo các bài kiểm tra (trắc nghiệm, tự luận) cho khóa học.
* **FR-09 (Giảng viên):** Giảng viên có thể xem danh sách học viên đã đăng ký khóa học của mình.
* **FR-10 (Admin):** Admin có quyền duyệt và cho phép hiển thị/gỡ bỏ khóa học khỏi hệ thống.

**C. Chức năng Học tập (Học viên)**
* **FR-11:** Học viên có thể tìm kiếm khóa học theo tên, chủ đề, hoặc giảng viên.
* **FR-12:** Học viên có thể xem thông tin chi tiết của khóa học (mô tả, nội dung, đánh giá).
* **FR-13:** Học viên có thể thêm khóa học vào giỏ hàng và tiến hành thanh toán (qua cổng thanh toán, chuyển khoản).
* **FR-14:** Học viên có thể truy cập vào các khóa học đã mua trong "Bảng điều khiển cá nhân".
* **FR-15:** Học viên có thể xem nội dung bài giảng (video, tài liệu).
* **FR-16:** Hệ thống phải lưu lại tiến độ học tập của học viên (ví dụ: bài học đã xem).
* **FR-17:** Học viên có thể làm bài kiểm tra và xem kết quả.
* **FR-18:** Học viên có thể để lại đánh giá (rating) và bình luận cho khóa học.

**D. Báo cáo & Thống kê**
* **FR-19 (Giảng viên):** Giảng viên có thể xem báo cáo doanh thu từ các khóa học của mình.
* **FR-20 (Admin):** Admin có thể xem báo cáo tổng quan về doanh thu, số lượng người dùng mới, số lượng khóa học được mua.

### 2.2. Yêu cầu phi chức năng (Non-functional Requirements)

Các yêu cầu về đặc tính vận hành và chất lượng của hệ thống:

* **NFR-01 (Hiệu suất - Performance):**
    * Thời gian tải trang chủ và trang chi tiết khóa học phải dưới 3 giây.
    * Video bài giảng phải được streaming mượt mà, không bị giật/đứng hình với kết nối mạng trung bình.
* **NFR-02 (Bảo mật - Security):**
    * Mật khẩu người dùng phải được mã hóa một chiều (hashed) trong CSDL.
    * Hệ thống phải sử dụng HTTPS (SSL) để mã hóa toàn bộ dữ liệu truyền tải.
    * Phải có cơ chế bảo vệ chống sao chép/tải về trái phép video bài giảng (ví dụ: DRM hoặc watermarking).
    * Dữ liệu thanh toán (thẻ tín dụng) không được lưu trữ trực tiếp trên hệ thống mà phải xử lý qua cổng thanh toán tuân thủ PCI DSS.
* **NFR-03 (Tính khả dụng - Availability):**
    * Hệ thống phải đảm bảo thời gian hoạt động (uptime) 99.9%.
* **NFR-04 (Tính dễ sử dụng - Usability):**
    * Giao diện người dùng (UI) phải thân thiện, rõ ràng và dễ điều hướng cho cả học viên và giảng viên.
    * Hệ thống phải có thiết kế đáp ứng (Responsive Design), hiển thị tốt trên các thiết bị di động (điện thoại, máy tính bảng).
* **NFR-05 (Khả năng mở rộng - Scalability):**
    * Hệ thống phải có khả năng xử lý đồng thời ít nhất 1000 người dùng truy cập cùng lúc.
    * Kiến trúc hệ thống phải cho phép dễ dàng nâng cấp (ví dụ: thêm máy chủ) khi số lượng người dùng tăng lên.
* **NFR-06 (Tính tương thích - Compatibility):**
    * Hệ thống phải hoạt động ổn định trên các trình duyệt web phổ biến: Chrome, Firefox, Safari, Edge (phiên bản mới nhất).