# Ex 4: Nhận biết các loại hệ thống thông tin và mô hình phát triển phù hợp.

| Loại hệ thống | Vai trò hệ thống | Giải Thích |
| :--- | :--- | :--- |
| TPS(Transaction Processing System) | Cối lõi của hệ thống | Ghi nhập các xử lý giao dịch như tạo đơn, cập nhập trạng thái, xác nhận Giao Hàng |
| MIS(Management Information System) | Phân tích và báo cáo | Cung cấp các báo cáo tổng hợp về số lượng đơn, hiệu suất nhân viên giao hàng, tỉ lệ giao hàng thành công.. |
| DSS (Decision Support System) | Tối ưu tuyến đường va ra quyết định | Hỗ trợ phân tích tuyến đường, dự báo nhu cầ vận chuyển, gợi ý cách phận bổ hàng |
| EIS (Executive Information System) | Phục Vụ Quản lý cấp cao | Tồn hợp chỉ số KPI, biểu đồ hiệu suất, và xu hướng kinh doanh, để lãnh đạo ra quết định chiến lươc |

### Mô hình phát triển Phần mền

| Mô Hình | Đặc điểm chính | Ưu điểm | Kết Luận |
| :--- | :--- | :--- | :--- |
| Waterfall | Phát triển theo giai đoạn cố định: phân tích -> thiết kế -> Lập trình -> kiểm thử -> triển khai | Phù họp cho dự án ổn định, ít that đổi, yêu cầu.Tuy nhiên logistics có nhiều biến động thực tế. | Ko Phù hợp |
| Agile/Scrum | Phát triên linh hoạt theo từng chu kì ngắn (Sprint) có thể cập nhập tính năng theo phàn hồi người dùn | Rất Phù hợp với ngành logisticsơi yêu cầu thay đổi liên tục (ví dụ: thêm phương thức giao, tích hợp bản đồ GPS mới). | Khuyến nghi dùng |
| Spiral Model | Tập trung vào quản lý rủi ro, phát triển theo vòng lặp (iteration). | Phù hợp với các dự án phức tạp, rủi ro cao (ví dụ: tích hợp hệ thống AI route optimization). | Có thể áp dụng song song với Agile nếu hệ thống quy mô lớn. |