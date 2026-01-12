# Copy Folder Google Drive to Google Drive - 1TouchPro

<a href="https://colab.research.google.com/github/nqthaivl/Copy-Folder-Google-Drive-to-Google-Drive/blob/main/Copy_Folder_Google_Drive_to_Google_Drive.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab">
</a>

## 🌟 Giới thiệu

Công cụ này giúp bạn sao chép toàn bộ cấu trúc thư mục từ Google Drive này sang Google Drive khác (bao gồm cả Shared Drive) một cách nhanh chóng. Công cụ hỗ trợ xử lý đệ quy thư mục con, kiểm tra trùng lặp file và giới hạn dung lượng sao chép hàng ngày.

## 🛠 Hướng dẫn sử dụng chi tiết

Để công cụ hoạt động chính xác và tránh lỗi, bạn cần thực hiện theo đúng thứ tự các bước sau trên Google Colab:

### Bước 1: Khởi tạo giao diện (Cell Input)
Tìm đến ô mã nguồn đầu tiên có tiêu đề **#@title Input**, nhấn nút **Play (Run cell)**. Các ô nhập liệu sẽ hiện ra:

* **Your drive:** Dán đường dẫn (link) thư mục **Đích** (nơi sẽ chứa dữ liệu copy đến).
* **Shared drive:** Dán đường dẫn (link) thư mục **Nguồn** (nơi chứa dữ liệu cần copy đi).
* **Từ trang / Đến trang:** Để mặc định là `0` nếu muốn copy toàn bộ thư mục.
* **Dung lượng tối đa (GB):** Mặc định là `700` (Để tránh chạm ngưỡng giới hạn 750GB/ngày của Google).
* **Bỏ file, folder:** Nhập từ khóa muốn bỏ qua (ví dụ: `.mp4, .zip`), các từ khóa phân tách bằng dấu phẩy.

> [!IMPORTANT]
> **LƯU Ý QUAN TRỌNG:** Sau khi dán link vào các ô nhập liệu, bạn **PHẢI nhấn phím ENTER** ở mỗi ô hoặc click chuột ra vùng trắng bên ngoài. Nếu không nhấn Enter, Google Colab sẽ không ghi nhận dữ liệu và báo lỗi `Missing required parameter "fileId"`.

### Bước 2: Xác thực và Chạy (Cell Run)
1.  Tìm đến ô mã nguồn thứ hai có tiêu đề **#@title Run** và nhấn nút **Play**.
2.  Một cửa sổ xác thực của Google sẽ hiện ra:
    * Chọn tài khoản Google của bạn.
    * Nhấn **Allow (Cho phép)** để cấp quyền cho mã nguồn truy cập và sao chép file trong Drive của bạn.

### Bước 3: Theo dõi tiến độ
Sau khi xác thực thành công, chương trình sẽ hiển thị log chi tiết:
* Liệt kê danh sách file tìm thấy.
* Tự động tạo thư mục con nếu chưa có.
* Hiển thị tên file đang copy, dung lượng và tốc độ (MB/s).
* Thông báo **Done** kèm tổng dung lượng và thời gian thực hiện khi hoàn tất.

---

## ⚠️ Lưu ý và Giới hạn

1.  **Giới hạn 750GB:** Google Drive áp dụng hạn ngạch copy tối đa khoảng **750GB/ngày** cho mỗi tài khoản cá nhân. Nếu quá trình dừng lại giữa chừng do hết hạn ngạch, hãy thử lại sau 24 giờ.
2.  **Quyền truy cập:** Đảm bảo tài khoản chạy Colab có quyền **Người xem (Viewer)** ở folder nguồn và quyền **Người chỉnh sửa (Editor)** ở folder đích.
3.  **Duy trì kết nối:** Google Colab có thể tự ngắt nếu tab trình duyệt bị đóng hoặc máy tính đi vào chế độ ngủ (Sleep). Với các thư mục hàng trăm GB, hãy thỉnh thoảng kiểm tra tiến độ.

---
 
