





































gitignore
*.log
.DS_Store
Thumbs.db
.vscode/
.idea/
👉 Thực hiện Commit 1:

bash
git add .gitignore
git commit -m "feat: initialize repository and add gitignore"
Tạo file src/index.html: (Nhớ thay đổi toàn bộ thông tin trong dấu [...] thành thông tin thật)

html
<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DevOps Hackathon - Đề 002 - Bùi Đức Lợi</title>
    <style>
    body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; background-color: #f4f6f9; margin: 0; padding: 20px; color: #333; }
</style>

</head>
<body>
    <div class="container">
        <h1>Xin chào đến với Ptit Rikkei DevOps Lab - Bùi Đức Lợi - PTIT-HN-184 - K24-CNTT2</h1>
        <h2>Thông tin sinh viên</h2>
        <table>
            <tr><th>Họ và tên</th><td>Bùi Đức Lợi</td></tr>
            <tr><th>Mã sinh viên</th><td>PTIT-HN-184</td></tr>
            <tr><th>Lớp</th><td>K24-CNTT2</td></tr>
            <tr><th>Email</th><td>zeikezan12345@gmail.com</td></tr>
            <tr><th>Tài khoản Linux</th><td>loibd-k24cntt2</td></tr>
            <tr><th>GitHub</th><td><a href="https://github.com/LLL2006" target="_blank">LLL2006</a></td></tr>
        </table>
        <h2>Thông tin bài thi</h2>
        <table>
            <tr><th>Đề thi</th><td>Đề số 002</td></tr>
            <tr><th>Chủ đề</th><td>Quản lý sản phẩm (Shop)</td></tr>
            <tr><th>Cổng Nginx</th><td>8082</td></tr>
            <tr><th>IP máy chủ</th><td>221.121.4.90</td></tr>
            <tr><th>Ngày thi</th><td>08/10/2026</td></tr>
            <tr><th>Repository</th><td><a href="https://github.com/LLL2006/devops-hackathon-de002-loibd" target="_blank">devops-hackathon-de002-loibd</a></td></tr>
        </table>
        <h2>Giới thiệu hệ thống</h2>
        <div class="desc-box">
            Hệ thống Quản lý sản phẩm (Shop) được xây dựng nhằm tối ưu hóa quy trình quản lý hàng hóa, theo dõi tồn kho và xử lý đơn hàng nhanh chóng. Giải pháp giúp doanh nghiệp dễ dàng kiểm soát danh mục sản phẩm, giá cả và chương trình khuyến mãi theo thời gian thực. Nền tảng được thiết kế với kiến trúc hiện đại, đảm bảo tính sẵn sàng cao, bảo mật và vận hành ổn định trên nền tảng Nginx.
        </div>
    </div>
</body>
</html>
👉 Thực hiện Commit 2:

bash
git add src/index.html
git commit -m "feat: add index.html with student and shop system details"
Tạo file nginx/loibd-k24cntt2.conf: (Ví dụ tên file là nginx/nguyenvana-k24cntt1.conf)

nginx
server {
listen 8082;
listen [::]:8082;
server_name 221.121.4.90;
root /var/www/devops-hackathon-de002-loibd/src;
index index.html;
access_log /var/log/nginx/loibd-k24cntt2.access.log;
error_log /var/log/nginx/loibd-k24cntt2.error.log;
location / {
allow all;
try_files $uri $uri/ =404;
}
}
👉 Thực hiện Commit 3:

bash
git add nginx/
git commit -m "feat: add nginx server block config"
Tạo file README.md (Khung theo yêu cầu đề thi):

markdown
# DevOps Hackathon – Đề 002: Quản lý sản phẩm (Shop)

## 1. Thông tin sinh viên
| Họ và tên | Mã sinh viên | Lớp | Tài khoản Linux | GitHub | Cổng Nginx |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Bùi Đức Lợi | PTIT-HN-184 | K24-CNTT2 | loibd-k24cntt2 | [LLL2006](https://github.com/LLL2006) | 8082 |

## 2. Môi trường triển khai
- Hệ điều hành: Ubuntu 24.04 LTS (VPS)
- Phiên bản Web Server: Nginx
- Version Control: Git
- Nơi chạy: VPS

## 3. Cấu trúc dự án
```text
devops-hackathon-de002-loibd/
├── src/
│   └── index.html
├── nginx/
│   └── loibd-k24cntt2.conf
├── screenshots/
│   ├── 01-user.png
│   ├── 02-nginx.png
│   ├── 03-ufw.png
│   ├── 04-website.png
│   ├── 05-git-log.png
│   └── 06-update.png
├── .gitignore
└── README.md


4. Cấu hình Nginx
Tham số trong template	Giá trị đã điền	Giải thích
<PORT>	8082	Cổng riêng được phân bổ cho website (>= 8080)
<SERVER_NAME>	221.121.4.90	Địa chỉ IP của máy chủ VPS (hostname -I)
<WEB_ROOT>	/var/www/devops-hackathon-de002-loibd/src	Đường dẫn tuyệt đối trỏ vào thư mục chứa web static
<INDEX_FILE>	index.html	Trang mặc định khi truy cập domain/IP
<TEN_TAI_KHOAN>	loibd-k24cntt2	Tên người dùng dùng để phân tách file log access/error
<ALLOW_DIRECTIVE>	allow all;	Chỉ thị Nginx cho phép mọi request từ bên ngoài
5. Hình ảnh minh chứng
01. Tài khoản người dùng

02. Trạng thái Nginx

03. Cấu hình tường lửa UFW

04. Giao diện Website

05. Lịch sử Git Log

06. Cập nhật Website lần 2

👉 *Thực hiện Commit 4 và Push lên GitHub:*
```bash
git add README.md
git commit -m "docs: add README template and configuration details"
# Đẩy code lên GitHub
git remote add origin https://github.com/LLL2006/devops-hackathon-de002-loibd.git
git branch -M main
git push -u origin main
BƯỚC 3: DEPLOY LÊN VPS & CẤU HÌNH NGINX, TƯỜNG LỬA (40 ĐIỂM)
Quay lại cửa sổ Terminal Bitvise (đang ở user loibd-k24cntt2):

3.1. Clone repo và phân quyền
bash
# Clone code từ GitHub về đúng thư mục quy định
sudo git clone https://github.com/LLL2006/devops-hackathon-de002-loibd.git /var/www/devops-hackathon-de002-loibd
# Chuyển quyền sở hữu thư mục về cho tài khoản cá nhân
sudo chown -R loibd-k24cntt2:loibd-k24cntt2 /var/www/devops-hackathon-de002-loibd
# Phân quyền chuẩn: thư mục 755, file 644 (TUYỆT ĐỐI KHÔNG DÙNG 777)
sudo find /var/www/devops-hackathon-de002-loibd -type d -exec chmod 755 {} \;
sudo find /var/www/devops-hackathon-de002-loibd -type f -exec chmod 644 {} \;
3.2. Cấu hình và kích hoạt Nginx
bash
# Copy file conf vào sites-available
sudo cp /var/www/devops-hackathon-de002-loibd/nginx/loibd-k24cntt2.conf /etc/nginx/sites-available/
# Tạo symlink sang sites-enabled
sudo ln -s /etc/nginx/sites-available/loibd-k24cntt2.conf /etc/nginx/sites-enabled/
# Gỡ bỏ site mặc định default để giải phóng cổng 80 và tránh xung đột
sudo rm -f /etc/nginx/sites-enabled/default
# Kiểm tra cú pháp Nginx
sudo nginx -t
# Reload lại Nginx
sudo systemctl reload nginx
📸 CHỤP ẢNH MINH CHỨNG 02: 02-nginx.png
Chạy lệnh sau:

bash
sudo nginx -t && systemctl status nginx --no-pager
👉 Chụp màn hình Terminal (thấy rõ syntax is ok / test is successful và trạng thái active (running)). Lưu ảnh thành 02-nginx.png.

3.3. Cấu hình tường lửa UFW
bash
# BẮT BUỘC: Mở cổng SSH 22 trước tiên để không bị mất kết nối VPS!
sudo ufw allow 22/tcp
# Mở cổng riêng của bài thi
sudo ufw allow 8082/tcp
# Bật tường lửa (nhập 'y' nếu được hỏi)
sudo ufw enable
📸 CHỤP ẢNH MINH CHỨNG 03: 03-ufw.png
Chạy lệnh:

bash
sudo ufw status verbose
👉 Chụp màn hình Terminal (thấy rõ Status: active, có dòng 22/tcp ALLOW IN Anywhere và 8082/tcp ALLOW IN Anywhere cho cả IPv4 và IPv6). Lưu ảnh thành 03-ufw.png.

📸 CHỤP ẢNH MINH CHỨNG 04: 04-website.png
Mở trình duyệt web trên máy tính của bạn, gõ vào thanh địa chỉ: http://221.121.4.90:8082
👉 Chụp toàn bộ trang web hiển thị đầy đủ thông tin. Lưu ảnh thành 04-website.png.

BƯỚC 4: THỰC HIỆN CẬP NHẬT LẦN 2 & CHỤP CÁC ẢNH CÒN LẠI (20 ĐIỂM)
4.1. Cập nhật website lần 2
Mở file src/index.html (trên máy local bạn làm git), thêm 1 dòng vào bên dưới tiêu đề <h1>:

html
<p style="color: #2e7d32; font-weight: bold;">Cập nhật lần 2 - 11:30 08/10/2026</p>
(Thay ngày giờ thành giờ hiện tại bạn thực hành)

Commit và Push lên GitHub:

bash
git add src/index.html
git commit -m "feat: update index.html version 2 with timestamp"
git push
Trên Terminal VPS, chạy git pull để nhận code mới:

bash
cd /var/www/devops-hackathon-de002-loibd
git pull
📸 CHỤP ẢNH MINH CHỨNG 06: 06-update.png
Vào trình duyệt http://221.121.4.90:8082, bấm Ctrl + F5 để tải lại trang.
👉 Chụp màn hình thấy dòng chữ "Cập nhật lần 2...". Lưu ảnh thành 06-update.png.

📸 CHỤP ẢNH MINH CHỨNG 05: 05-git-log.png
Trên terminal, gõ lệnh:

bash
git log --oneline
👉 Chụp màn hình Terminal thấy danh sách các commit rõ ràng (tối thiểu 5 commit). Lưu ảnh thành 05-git-log.png.

BƯỚC 5: ĐẨY TOÀN BỘ ẢNH LÊN GITHUB & HOÀN TẤT NỘP BÀI
Copy toàn bộ 6 file ảnh vừa chụp:
01-user.png
02-nginx.png
03-ufw.png
04-website.png
05-git-log.png
06-update.png vào thư mục screenshots/ của dự án.
Commit và đẩy 6 ảnh lên GitHub:
bash
git add screenshots/
git commit -m "docs: add screenshots for submission"
git push
Lên trình duyệt vào trang repo GitHub của bạn: https://github.com/LLL2006/devops-hackathon-de002-loibd
Kiểm tra xem chế độ repo đã là Public chưa.
Kéo xuống xem file README.md xem tất cả các ảnh đã hiển thị đầy đủ, nét rõ hay chưa.
Copy link GitHub này và dán nộp lên hệ thống RAIA theo đúng yêu cầu đề bài!

