# BÀI LÀM – HACKATHON 02

- **Mã đề:** 07
- **Họ tên: Đoàn Nguyễn Minh Tâm**
- **Lớp: HCM-KS26-CNTT2**
- **Link repository: https://github.com/HCM-KS26-IT108-CNTT2/HCM-KS26-CNTT2_Nhap-mon-CNTT_Hackathon02.git**
- **Hệ điều hành (Windows/macOS): Windows**

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
pwd
ls -force
mv .\lich_lam_viec.txt docs
mkdir backup
cp .\data\hoa_don_spa_thang_7.xlsx .\backup\
rm .\temp_707.tmp
dir .\logs\
```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
  Directory: D:\starter-kit\spa-website


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/11/2026   1:46 PM                backup
d-----        11/11/2026   1:36 PM                data
d-----        11/11/2026   1:46 PM                docs
d-----        11/11/2026   1:35 PM                evidence
d-----        11/11/2026   1:36 PM                logs
d-----        11/11/2026   1:32 PM                web
---h--         11/3/2026   7:07 AM             75 .env
-a----        11/11/2026   1:39 PM           2546 bai_lam.md


    Directory: D:\starter-kit\spa-website\backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM           6149 hoa_don_spa_thang_7.xlsx


    Directory: D:\starter-kit\spa-website\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM           6149 hoa_don_spa_thang_7.xlsx


    Directory: D:\starter-kit\spa-website\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM            149 lich_lam_viec.txt


    Directory: D:\starter-kit\spa-website\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         11/3/2026   7:07 AM            939 service.log


    Directory: D:\starter-kit\spa-website\web


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        11/11/2026   1:32 PM                images
------         11/3/2026   7:07 AM            597 app.js
------         11/3/2026   7:07 AM            523 index.html
------         11/3/2026   7:07 AM            460 style.css


    Directory: D:\starter-kit\spa-website\web\images


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
------         11/3/2026   7:07 AM           3091 logo-lotuscare.png
```

## 4.3. Lọc log truy cập website

### a) Lệnh lọc các dòng status=500

```shell
get-content .\logs\service.log | findstr "status=500" > .\logs\loi_500.txt
```

### 2 dòng đầu tiên trong logs/loi_500.txt

```text
2026-07-28 08:12:50 POST /api/dat-lich status=500
2026-07-28 08:19:23 POST /api/dat-lich status=500
```

### b) Lệnh đếm số dòng status=404 và kết quả

```shell
get-content .\logs\service.log | findstr "status=404" | measure-object
```

```text
Count    : 4
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

## 4.4. Chạy script tong_hop (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
# Ghi lệnh vào đây (xoá dòng này)

```

### Nội dung file logs/tong_hop.txt

```text
=== BAO CAO SU CO WEBSITE ===

2026-07-28 08:16:12 GET /images/phong-spa-3.jpg status=404
2026-07-28 08:39:18 GET /uu-dai-cu status=404
2026-07-28 08:46:40 GET /tin-tuc status=404
2026-07-28 08:48:51 GET /tin-tuc status=404




Count    : 6
Average  : 
Sum      : 
Maximum  : 
Minimum  : 
Property : 
```

## 4.5. README.md và bảo vệ thông tin bí mật

> README.md, .gitignore và .env.example được chấm trực tiếp trên file ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [ ] README.md: Heading 1, mô tả có **in đậm** và *in nghiêng*, bảng, code block, task list, blockquote
- [ ] .gitignore có dòng `.env` (tên file đúng, không có đuôi .txt)
- [ ] .env.example có đủ tên biến, giá trị để trống (tên file đúng, không có đuôi .txt)

## 4.6. Kiểm tra trang web bằng DevTools (F12) và báo cáo lỗi

### Bảng lỗi

| STT | Tab DevTools phát hiện lỗi | Tên file hoặc thông báo lỗi | Cách khắc phục |
| --- | --- | --- | --- |
| 1 | Network | logo.png | mở web/index.html bằng VS code, tại dòng 10 có đoạn src="images/logo.png"; thay logo.png bằng đúng tên file ảnh trong thư mục web/images. Lưu file, tải lại trang (Windows: Ctrl + Shift + R; macOS: Cmd + Shift + R) để logo hiển thị. |
| 2 | Console | Uncaught ReferenceError: hienThiGoiDichVu is not defined |  |

> Ảnh chụp màn hình lưu trong thư mục `evidence/` (network.png, console.png).

### Báo cáo lỗi gửi trưởng nhóm

- **Context: Dạ em chào anh, em đang dùng windows 11 và em đang gặp vấn đề trong việc sửa lỗi web ạ** 
- **Expected: Em muốn trang web có thể hiển thị được bảng giá gói dịch vụ của spa** 
- **Actual: Khi em vào trang web thì bảng giá của spa không hiện và in ra dòng lỗi màu đỏ ở tab console ạ** 
- **Log: dạ dòng lỗi này ạ: Uncaught ReferenceError: hienThiGoiDichVu is not defined app.js:18** 

### Câu tìm kiếm Google

```text
site:stackoverflow.com "Uncaught ReferenceError"
```

## 4.7. Excel

> Phần Excel được chấm trực tiếp trên file `data/hoa_don_spa_thang_7.xlsx`, không cần ghi vào đây.
