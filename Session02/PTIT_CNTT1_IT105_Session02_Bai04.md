# Cấu trúc tài liệu SRS cho Hệ thống học trực tuyến

## 1. Mở đầu

- 1.1. Mục đích: Giải thích lý do tài liệu này được tạo ra. Nó định rõ đối tượng độc giả và cách sử dụng tài liệu trong suốt vòng đời dự án.

- 1.2. Phạm vi: Mô tả những gì hệ thống sẽ làm và (quan trọng không kém) những gì hệ thống sẽ không làm. Ví dụ, hệ thống sẽ quản lý khóa học và học viên, nhưng sẽ không tích hợp với hệ thống kế toán của trường.

- 1.3. Định nghĩa: Liệt kê và giải thích tất cả các thuật ngữ chuyên ngành hoặc từ viết tắt được sử dụng trong tài liệu. Điều này đảm bảo mọi người tham gia đều hiểu thống nhất các khái niệm.

- 1.4. Tài liệu tham khảo: Liệt kê tất cả các tài liệu khác có liên quan đến dự án. Ví dụ: tài liệu khảo sát người dùng, tài liệu đặc tả của đối tác, các tiêu chuẩn kỹ thuật.

- 1.5. Tổng quan tài liệu: Tóm tắt ngắn gọn cấu trúc của phần còn lại của tài liệu SRS. Giúp người đọc dễ dàng tìm thấy thông tin họ cần.

## 2. Mô tả tổng quan

- 2.1. Bối cảnh sản phẩm (Product Perspective): Đặt hệ thống trong mối quan hệ với các hệ thống khác. Ví dụ, đây là một hệ thống độc lập hay là một module của một hệ thống quản lý trường học lớn hơn?

- 2.2. Chức năng chính (Product Functions): Tóm tắt các chức năng chính mà hệ thống sẽ cung cấp ở mức cao. Ví dụ: quản lý khóa học, tổ chức lớp học trực tuyến, kiểm tra và đánh giá, báo cáo tiến độ học tập.

- 2.3. Đặc điểm người dùng (User Characteristics): Mô tả các nhóm người dùng sẽ tương tác với hệ thống (ví dụ: Học viên, Giảng viên, Quản trị viên). Phần này nêu rõ trình độ kỹ thuật và nhu cầu của từng nhóm.

- 2.4. Các ràng buộc (Constraints): Liệt kê các yếu tố giới hạn việc thiết kế và phát triển. Ví dụ: hệ thống phải được xây dựng trên nền tảng công nghệ cụ thể, phải tuân thủ luật An ninh mạng, hoặc ngân sách không vượt quá X.

- 2.5. Giả định và Phụ thuộc (Assumptions and Dependencies): Nêu rõ các giả định được đưa ra trong quá trình viết yêu cầu (ví dụ: giả định người dùng có kết nối internet ổn định) và các yếu tố bên ngoài mà hệ thống phụ thuộc vào.

## 3. Yêu cầu cụ thể

- 3.1. Yêu cầu chức năng (Functional Requirements):

  - Mô tả chi tiết hệ thống sẽ làm gì. Các yêu cầu này thường được nhóm theo tính năng, ví dụ:

    - Quản lý Người dùng: Đăng ký, đăng nhập, quản lý hồ sơ...

    - Quản lý Khóa học: Tạo/sửa/xóa khóa học, tải lên tài liệu, video...

    - Tương tác Học tập: Xem bài giảng, làm bài kiểm tra, nộp bài tập, thảo luận trên diễn đàn...

- 3.2. Yêu cầu phi chức năng (Non-functional Requirements):

  - Mô tả hệ thống nên hoạt động như thế nào, định nghĩa các tiêu chí chất lượng, bao gồm:

    - Bảo mật (Security): Mật khẩu phải được mã hóa, dữ liệu người dùng phải được bảo vệ.

    - Hiệu năng (Performance): Thời gian tải trang không quá 3 giây, hệ thống phải phục vụ được 1000 người dùng truy cập đồng thời.

    - Tính khả dụng (Usability): Giao diện phải thân thiện, dễ sử dụng cho cả giảng viên không rành về công nghệ.

- 3.3. Yêu cầu về giao diện bên ngoài (External Interface Requirements):

  - Mô tả cách hệ thống tương tác với các thành phần phần cứng, phần mềm hoặc hệ thống khác. Ví dụ: tích hợp với cổng thanh toán online để bán khóa học, hoặc kết nối với Zoom API để tạo lớp học ảo
