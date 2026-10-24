# BÀI LÀM – THI THỬ HACKATHON 01

- **Mã đề:** Thi thử
- **Họ tên:** Phạm Duy Quang
- **Lớp:** CNTT2
- **Link repository:** https://github.com/quangdev05/CNTT2_Nhap-mon-CNTT_ThiThu
- **Hệ điều hành (Windows/macOS):** Windows

## 4.2. Thao tác máy tính cơ bản bằng CLI

### Các lệnh đã chạy

```shell
pwd
gci -Force
mv "nhap_hang.txt" docs
mv "logo_van_phong_pham.png" media
cp "media/logo_van_phong_pham.png" backup
rm "temp_131.tmp"
cd logs
gci
cd ..
gci -R -Force

```

### Kết quả liệt kê toàn bộ dự án (Windows: Get-ChildItem -Recurse -Force; macOS: ls -aR)

```text
Directory:
    D:\Github\CNTT2_Nhap-mon-CNTT_ThiThu\starter-kit\van-phong-pham-website


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----        10/23/2026     08:47                backup
d-----        10/23/2026     08:41                data
d-----        10/23/2026     08:45                docs
d-----        10/23/2026     08:41                logs
d-----        10/23/2026     08:46                media
-a----        10/19/2026     09:41             78 .env
-a----        10/23/2026     08:53           2462 bai_lam.md


    Directory: D:\Github\CNTT2_Nhap-mon-CNTT_ThiThu\starter-kit\van-phong-p
    ham-website\backup


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026     09:41           6053 logo_van_phong_pham.png


    Directory: D:\Github\CNTT2_Nhap-mon-CNTT_ThiThu\starter-kit\van-phong-p
    ham-website\data


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026     09:41           6105 don_ban_thang_10.xlsx


    Directory: D:\Github\CNTT2_Nhap-mon-CNTT_ThiThu\starter-kit\van-phong-p
    ham-website\docs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026     09:41             51 nhap_hang.txt


    Directory: D:\Github\CNTT2_Nhap-mon-CNTT_ThiThu\starter-kit\van-phong-p
    ham-website\logs


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026     09:41           1053 shop.log


    Directory: D:\Github\CNTT2_Nhap-mon-CNTT_ThiThu\starter-kit\van-phong-p
    ham-website\media


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        10/19/2026     09:41           6053 logo_van_phong_pham.png

```

## 4.3. Lọc log thủ công

### Lệnh đã chạy

```shell
gc logs/shop.log
gc logs/shop.log | select-string "ERROR"
gc logs/shop.log | select-string "ERROR" > logs/daily_report.txt

```

### 2 dòng lỗi đầu tiên trong daily_report.txt

```text
2025-10-28 08:24:28 [ERROR] Thanh toan bi tu choi
2025-10-28 08:30:28 [ERROR] Thanh toan bi tu choi

```

## 4.4. Thao tác với tài liệu Markdown (README.md)

> README.md được chấm trực tiếp trên file `README.md` ở gốc dự án. Đánh dấu `[x]` vào các mục đã làm để tự kiểm tra.

- [x] Heading 1: tên dự án
- [x] Mô tả ngắn có cả **in đậm** và _in nghiêng_
- [x] Bảng `Thư mục | Nội dung`, ít nhất 3 dòng dữ liệu
- [x] Code block chứa lệnh PowerShell/Terminal liệt kê nội dung dự án
- [x] Task list ít nhất 2 công việc, có ít nhất 1 mục đã hoàn thành
- [x] Blockquote nhắc không upload `.env`

## 4.5. Chạy script auto_report (.ps1 hoặc .sh)

### Lệnh chạy (Windows: nếu dùng Phụ lục 2 thì ghi cả 2 lệnh)

```shell
./auto_report.ps1

```

### Nội dung file logs/auto_report.txt

```text
=== BAO CAO LOI ===

2025-10-28 08:24:28 [ERROR] Thanh toan bi tu choi
2025-10-28 08:30:28 [ERROR] Thanh toan bi tu choi
2025-10-28 08:33:28 [ERROR] Ket noi kho du lieu that bai
2025-10-28 08:39:28 [ERROR] Ket noi kho du lieu that bai
2025-10-28 08:42:28 [ERROR] Ket noi kho du lieu that bai
2025-10-28 09:12:28 [ERROR] Thanh toan bi tu choi




```

## 4.6. Đếm số dòng lỗi

### Lệnh

```shell
gc logs/shop.log | select-string "ERROR" | Measure-Object

```

### Kết quả đếm (Windows: giá trị Count; macOS: con số in ra)

```text
Count    : 6

```

## 4.7. Báo cáo tổng hợp

### Các lệnh đã chạy

```shell
"=== TONG HOP LOG ===" > logs/tong_hop.txt
gc logs/shop.log | Select-String "WARNING" >> logs/tong_hop.txt
gc logs/shop.log | Select-String "ERROR" | Measure-Object | Select-Object -exp Count >> logs\tong_hop.txt

```

### Nội dung file logs/tong_hop.txt

```text
=== TONG HOP LOG ===

2025-10-28 08:51:28 [WARNING] Thoi gian tai trang cham
2025-10-28 08:54:28 [WARNING] Anh san pham dung luong lon
2025-10-28 08:57:28 [WARNING] Thoi gian tai trang cham


6


```

## 4.8. Excel

> Phần Excel được chấm trực tiếp trên file `data/don_ban_thang_10.xlsx`, không cần ghi vào đây.
