# Hệ thống quản lý bán hàng

## 1. Phân tích kiến trúc tổng thể

### Có 4 thành phần chính

+ Frontend Layer
+ Backend Layer (API + Business Logic)
+ Database Layer
+ External Services Layer

## 2. Các thành phần chính của hệ thống

- 2.1. Frontend (Web + Mobile)

    - Chức năng:

        - Giao diện người dùng để tương tác với hệ thống.

        - Gửi và nhận dữ liệu qua API từ backend.

    - Công nghệ thường dùng:

        - Web: ReactJS, Angular, hoặc VueJS

        - Mobile: React Native, Flutter hoặc Swift/Kotlin

    - Nhiệm vụ chính:

        - Hiển thị sản phẩm, giỏ hàng, thông tin tài khoản

        - Gửi yêu cầu đăng nhập, mua hàng, thanh toán tới backend

        - Nhận phản hồi và hiển thị kết quả cho người dùng

- 2.2. Backend (API & Business Logic)

    - Chức năng:

        - Cung cấp API cho frontend

        - Xử lý logic nghiệp vụ (thanh toán, quản lý đơn hàng, kiểm tra tồn kho, ...)

        - Xác thực người dùng (Authentication & Authorization)

    - Công nghệ thường dùng:

        - Node.js (Express, NestJS), Java (Spring Boot), hoặc .NET Core

    - Thành phần con:

        - API Layer: nhận request từ frontend → trả response JSON

        - Service Layer: xử lý nghiệp vụ (tạo đơn hàng, tính tổng tiền, áp mã giảm giá, v.v.)

        - Data Access Layer: truy xuất và ghi dữ liệu vào database

- 2.3. Database (Lưu trữ dữ liệu)

    - Chức năng:

        - Lưu thông tin sản phẩm, khách hàng, đơn hàng, thanh toán, v.v.

    - Công nghệ thường dùng:

        - SQL: MySQL, PostgreSQL

        - NoSQL: MongoDB (cho dữ liệu linh hoạt như lịch sử duyệt sản phẩm, giỏ hàng tạm thời)

    - Các bảng/collection chính:

        - Users (khách hàng, quản trị viên)

        - Products (sản phẩm)

        - Orders (đơn hàng)

        - Cart (giỏ hàng)

        - Payments (thanh toán)

- 2.4. External Services (Dịch vụ bên ngoài)

    - Chức năng:

        - Tích hợp các hệ thống của bên thứ ba giúp hoàn thiện quy trình mua hàng.

    - Ví dụ:

        - Thanh toán: Momo, VNPay, Stripe, PayPal

        - Giao vận: Giao Hàng Nhanh, Giao Hàng Tiết Kiệm

        - Email/SMS: SendGrid, Twilio

        - Analytics: Google Analytics, Firebase

## 3. Hình vẽ