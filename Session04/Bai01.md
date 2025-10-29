# Bài 1

## 1. Lớp sách

- **Vai trò**: Đại diện cho một cuốn sách cụ thể trong thư viện. Lớp này lưu trữ tất cả các thông tin chi tiết về cuốn sách đó.

- **Thuộc tính**: maSach, tenSach, tacGia, namXuatBan, trangThai (ví dụ: có sẵn, đã cho mượn).

## 2. Lớp độc giả

- **Vai trò**: Đại diện cho người đọc (người mượn sách). Lớp này quản lý thông tin của độc giả và các hành động liên quan đến việc mượn/trả sách.

- **Thuộc tính**: maDocGia, hoTen, danhSachSachDangMuon.

- **Phương thức**: muonSach(), traSach().

## 3. Lớp NhanVien (Nhân viên thư viện)
- **Vai trò**: Đại diện cho nhân viên thư viện. Lớp này chịu trách nhiệm quản lý các hoạt động của thư viện như quản lý sách, độc giả và các giao dịch mượn/trả.

- **Thuộc tính**: maNhanVien, hoTen.

- **Phương thức**: themSach(), xoaSach(), lapPhieuMuon().

## 4. Lớp PhieuMuon (Phiếu mượn)
- **Vai trò**: Mặc dù không được đề cập tường minh, lớp này rất cần thiết để thể hiện mối quan hệ "mượn" giữa DocGia và Sach. Nó đại diện cho một giao dịch mượn sách cụ thể.

- **Thuộc tính**: maPhieu, maDocGia, maSach, ngayMuon, ngayTra.