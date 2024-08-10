# Copy Folder Google Drive to Google Drive - 1TouchPro
<a href="https://colab.research.google.com/github/nqthaivl/Copy-Folder-Google-Drive-to-Google-Drive/blob/main/Copy_Folder_Google_Drive_to_Google_Drive.ipynb"><img data-canonical-src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab" src="https://camo.githubusercontent.com/f5e0d0538a9c2972b5d413e0ace04cecd8efd828d133133933dfffec282a4e1b/68747470733a2f2f636f6c61622e72657365617263682e676f6f676c652e636f6d2f6173736574732f636f6c61622d62616467652e737667"></a>
## Giới thiệu

Chào mừng bạn đến với dự án "Copy Folder Google Drive to Google Drive - 1TouchPro". Dự án này giúp bạn sao chép toàn bộ nội dung của một thư mục trên Google Drive sang một thư mục khác trên cùng Google Drive hoặc tài khoản Google Drive khác.

## Hướng dẫn sử dụng

### 1. Yêu cầu

- Tài khoản Google.
- Quyền truy cập vào Google Drive API.
- Google Colab (hoặc môi trường hỗ trợ IPython Notebook).

### 2. Chuẩn bị

Để chạy mã nguồn, hãy làm theo các bước sau:

1. **Cài đặt Thư viện:**
   Không cần cài đặt thêm thư viện ngoài những gì có sẵn trong Google Colab.

2. **Nhập thông tin đầu vào:**

   - **Drive đích (dest_text):** Nhập liên kết đến thư mục trên Google Drive mà bạn muốn sao chép đến.
   - **Drive nguồn (source_text):** Nhập liên kết đến thư mục Google Drive mà bạn muốn sao chép từ đó.
   - **Từ trang (from_page):** Số trang đầu tiên để bắt đầu sao chép. Đặt là 0 nếu không phân trang.
   - **Đến trang (to_page):** Số trang cuối cùng để dừng sao chép. Đặt là 0 nếu không phân trang.
   - **Dung lượng tối đa (max_download_size_text):** Dung lượng tối đa (GB) cho phép sao chép. Chương trình sẽ dừng nếu tổng dung lượng vượt quá giá trị này.
   - **Loại bỏ (exclude_str_text):** Các chuỗi cần loại bỏ khỏi tên file hoặc thư mục trong quá trình sao chép. Nhiều chuỗi có thể được phân cách bằng dấu phẩy.

### 3. Chạy Mã Nguồn

Sau khi nhập tất cả các thông tin cần thiết, chạy đoạn mã sau:

```python
destDriveLink = dest_text.value
sourceDriveLink = source_text.value
fromPage = int(from_page_text.value)
toPage = int(to_page_text.value)

downloader = DownloadFromDrive()
downloader._limit_size = float(max_download_size_text.value)
downloader.excluded_strings = [ext.strip() for ext in exclude_str_text.value.split(",") if ext.strip()]
downloader.copy_drive_to_drive(destDriveLink, sourceDriveLink, fromPage, toPage)
