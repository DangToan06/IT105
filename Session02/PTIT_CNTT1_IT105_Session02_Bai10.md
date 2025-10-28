### **BÁO CÁO PHÂN TÍCH SƠ BỘ: HỆ THỐNG QUẢN LÝ TUYỂN DỤNG**
---

#### **1. Giới thiệu**

Báo cáo này nhằm cung cấp cái nhìn tổng quan ban đầu về các yếu tố chính sẽ ảnh hưởng đến việc xây dựng và triển khai một Hệ thống Quản lý Tuyển dụng mới. Mục tiêu của hệ thống là **tự động hóa và tối ưu hóa quy trình tuyển dụng**, từ khâu đăng tin, sàng lọc hồ sơ đến quản lý phỏng vấn và gửi thư mời nhận việc, qua đó nâng cao hiệu suất và chất lượng tuyển dụng.

---

#### **2. Phân tích Môi trường Hệ thống**

Hệ thống sẽ không hoạt động độc lập mà chịu ảnh hưởng bởi nhiều yếu tố trong và ngoài công ty.

* **Người dùng:**
    * **Chuyên viên Tuyển dụng (Recruiter):** Người dùng chính, thực hiện mọi thao tác hàng ngày.
    * **Trưởng phòng/Bộ phận (Hiring Manager):** Người đưa ra yêu cầu tuyển dụng và tham gia phỏng vấn, đánh giá ứng viên.
    * **Ứng viên (Candidate):** Tương tác với hệ thống qua cổng thông tin tuyển dụng để nộp hồ sơ và theo dõi kết quả.
    * **Quản lý Nhân sự (HR Manager):** Xem báo cáo, đánh giá hiệu quả tuyển dụng.
* **Phần cứng & Phần mềm:**
    * Hệ thống cần hoạt động trên **nền tảng web**, tương thích với các trình duyệt phổ biến (Chrome, Firefox) trên máy tính của nhân viên.
    * Cần có giao diện thân thiện trên **thiết bị di động** cho ứng viên.
* **Hệ thống bên ngoài:**
    * **Tích hợp với các trang tuyển dụng:** Cần có khả năng tự động đăng tin lên các kênh như VietnamWorks, TopCV.
    * **Tích hợp với Lịch (Google Calendar/Outlook):** Để tự động hóa việc lên lịch phỏng vấn.
    * **Tích hợp với Website công ty:** Để đồng bộ các vị trí đang tuyển dụng lên trang "Tuyển dụng".
* **Quy trình nghiệp vụ:**
    * Hệ thống phải mô phỏng và cải tiến **quy trình tuyển dụng hiện tại** của công ty, bao gồm các bước: tạo yêu cầu, đăng tin, nhận hồ sơ, sàng lọc, phỏng vấn (nhiều vòng), và ra quyết định.
* **Luật lệ:**
    * Hệ thống phải tuân thủ **Luật Lao động Việt Nam** và **Nghị định 13/2023/NĐ-CP về Bảo vệ dữ liệu cá nhân**, đảm bảo thông tin của ứng viên được bảo mật tuyệt đối.

---

#### **3. Phân tích Các bên liên quan (Stakeholders)**

Xác định đúng các bên liên quan và mối quan tâm của họ là chìa khóa thành công.

| Stakeholder | Vai trò | Mối quan tâm | Mức độ ưu tiên |
| :--- | :--- | :--- | :--- |
| **Trưởng phòng/Bộ phận** | Người có nhu cầu tuyển dụng | • Tìm được ứng viên phù hợp nhanh nhất.<br>• Dễ dàng xem và đánh giá hồ sơ. | **Critical**|
| **Chuyên viên Tuyển dụng** | Người vận hành hệ thống | • Tự động hóa các công việc lặp đi lặp lại.<br>• Quản lý tất cả ứng viên ở một nơi.<br>• Dễ dàng giao tiếp với ứng viên & quản lý. | **Critical**|
| **Ứng viên** | Người nộp hồ sơ | • Quy trình nộp đơn đơn giản, nhanh chóng.<br>• Nhận được phản hồi về trạng thái hồ sơ. | **Major** |
| **Ban Giám đốc** | Nhà tài trợ dự án | • Giảm chi phí và thời gian tuyển dụng.<br>• Có số liệu để đo lường hiệu quả. | **Critical** |

---

#### **4. Nguồn và Kỹ thuật Thu thập Yêu cầu**

Để đảm bảo hệ thống đáp ứng đúng nhu cầu, chúng tôi đề xuất kết hợp các kỹ thuật sau:

1.  **Phân tích tài liệu:** Bắt đầu bằng việc nghiên cứu **"Quy trình tuyển dụng"** và các biểu mẫu (form) hiện tại của công ty.
2.  **Phỏng vấn:** Tổ chức các buổi phỏng vấn sâu với **Chuyên viên Tuyển dụng** và một vài **Trưởng phòng** để hiểu rõ khó khăn và mong muốn của họ.
3.  **Khảo sát:** Gửi bảng khảo sát ngắn cho tất cả **Trưởng phòng** để thu thập ý kiến trên diện rộng về các tính năng cần ưu tiên.

---

#### **5. Gợi ý Yêu cầu Hệ thống**

Dựa trên phân tích ban đầu, hệ thống cần có các yêu cầu sau:

* **Yêu cầu chức năng (Hệ thống sẽ LÀM GÌ?):**
    1.  **Đăng tin tuyển dụng:** Cho phép tạo tin tuyển dụng và tự động đăng lên nhiều kênh đã được tích hợp.
    2.  **Quản lý hồ sơ ứng viên:** Tự động thu thập hồ sơ từ các nguồn, cho phép tìm kiếm và lọc hồ sơ theo từ khóa, kỹ năng.
    3.  **Quản lý lịch phỏng vấn:** Cho phép lên lịch phỏng vấn và tự động gửi email mời cho ứng viên và người phỏng vấn.
    4.  **Báo cáo & Thống kê:** Tự động tạo báo cáo về thời gian tuyển dụng, hiệu quả của từng kênh, tỷ lệ ứng viên qua các vòng.

* **Yêu cầu phi chức năng (Hệ thống sẽ hoạt động NHƯ THẾ NÀO?):**
    1.  **Bảo mật (Security):** Mọi dữ liệu cá nhân của ứng viên phải được mã hóa. Hệ thống cần phân quyền chi tiết để đảm bảo chỉ người có thẩm quyền mới xem được thông tin.
    2.  **Hiệu năng (Performance):** Chức năng tìm kiếm hồ sơ phải trả về kết quả trong vòng 3 giây, ngay cả khi cơ sở dữ liệu có hàng chục ngàn hồ sơ.
    3.  **Tính dễ sử dụng (Usability):** Giao diện phải trực quan, giúp một chuyên viên tuyển dụng mới có thể sử dụng thành thạo các chức năng chính chỉ sau 1 buổi đào tạo.

---

#### **6. Đề xuất Cấu trúc Tài liệu Mô tả Yêu cầu (SRS)**

Để đảm bảo dự án đi đúng hướng, chúng tôi sẽ biên soạn một tài liệu Đặc tả Yêu cầu Phần mềm (SRS) chi tiết theo cấu trúc chuẩn:

1.  **Mở đầu:** Mục đích, phạm vi, định nghĩa.
2.  **Mô tả tổng quan:** Bối cảnh, chức năng chính, đặc điểm người dùng, các ràng buộc.
3.  **Yêu cầu cụ thể:** Chi tiết hóa toàn bộ các yêu cầu chức năng, phi chức năng, và yêu cầu về giao diện tích hợp.

---

#### **7. Kết luận và Bước tiếp theo**

Hệ thống Quản lý Tuyển dụng là một khoản đầu tư chiến lược, hứa hẹn mang lại lợi ích lớn về hiệu suất và chi phí.

Chúng tôi đề xuất bước tiếp theo là chính thức khởi động giai đoạn **"Thu thập Yêu cầu Chi tiết"** bằng các kỹ thuật đã nêu ở Mục 4.
