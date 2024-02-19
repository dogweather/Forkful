---
aliases:
- /vi/powershell/printing-debug-output/
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:04:45.199938-07:00
description: "In th\xF4ng tin debug gi\u1ED1ng nh\u01B0 \u0111ang tr\xF2 chuy\u1EC7\
  n v\u1EDBi m\xE3 l\u1EC7nh c\u1EE7a b\u1EA1n. \u0110\xF3 l\xE0 vi\u1EC7c ch\xE8\
  n c\xE1c l\u1EC7nh in \u0111\u1EC3 hi\u1EC3n th\u1ECB nh\u1EEFng g\xEC \u0111ang\
  \ di\u1EC5n ra b\xEAn d\u01B0\u1EDBi c\xF9ng c\u1EE7a ch\u01B0\u01A1ng\u2026"
lastmod: 2024-02-18 23:08:50.937111
model: gpt-4-0125-preview
summary: "In th\xF4ng tin debug gi\u1ED1ng nh\u01B0 \u0111ang tr\xF2 chuy\u1EC7n v\u1EDB\
  i m\xE3 l\u1EC7nh c\u1EE7a b\u1EA1n. \u0110\xF3 l\xE0 vi\u1EC7c ch\xE8n c\xE1c l\u1EC7\
  nh in \u0111\u1EC3 hi\u1EC3n th\u1ECB nh\u1EEFng g\xEC \u0111ang di\u1EC5n ra b\xEA\
  n d\u01B0\u1EDBi c\xF9ng c\u1EE7a ch\u01B0\u01A1ng\u2026"
title: "In ra th\xF4ng tin g\u1EE1 l\u1ED7i"
---

{{< edit_this_page >}}

## Cái gì & Tại sao?

In thông tin debug giống như đang trò chuyện với mã lệnh của bạn. Đó là việc chèn các lệnh in để hiển thị những gì đang diễn ra bên dưới cùng của chương trình. Các lập trình viên làm điều này để kiểm tra các biến, quá trình thực thi, và để hiểu tại sao mọi thứ có thể đang gặp vấn đề.

## Làm thế nào:

Hãy giữ nó đơn giản và thực sự làm điều gì đó. Chúng ta sẽ hiển thị giá trị của một biến, cách một vòng lặp tiến triển, và bắt lỗi cứng đầu có thể xuất hiện.

```PowerShell
# Hiển thị giá trị của một biến
$name = "PowerShell Guru"
Write-Host "Giá trị của name là: $name"

# Giám sát tiến độ của một vòng lặp
for ($i = 0; $i -lt 5; $i++) {
    Write-Host "Chúng ta đang ở vòng lặp số: $i"
}

# Bắt và in một lỗi
try {
    Get-Item "C:\NonExistent\File.txt" -ErrorAction Stop
} catch {
    Write-Host "Ối: $_"
}
```

Đầu ra mẫu:

```
Giá trị của name là: PowerShell Guru
Chúng ta đang ở vòng lặp số: 0
Chúng ta đang ở vòng lặp số: 1
Chúng ta đang ở vòng lặp số: 2
Chúng ta đang ở vòng lặp số: 3
Chúng ta đang ở vòng lặp số: 4
Ối: Không thể tìm thấy đường dẫn 'C:\NonExistent\File.txt' vì nó không tồn tại.
```

## Sâu hơn

Trở lại những ngày xưa cũ của lập trình, sửa lỗi thường có nghĩa là lỗi vật lý thực sự gây rối với phần cứng. Chúng ta đã đi được một chặng đường dài kể từ đó, giờ đây sử dụng thuật ngữ "bug" cho các vấn đề về mã lệnh, và "debugging" để sửa chúng.

Lệnh `Write-Host` là người bạn PowerShell dùng để in ra màn hình, điều này tốt cho các kịch bản cơ bản. Nhưng có những cách mát mẻ hơn để làm điều đó: `Write-Verbose`, `Write-Debug`, `Write-Output`, và `Write-Information` giống như các hương vị đầu ra khác nhau cho các trường hợp sử dụng khác nhau. Chúng cho phép bạn kiểm soát độ chi tiết, điều này tuyệt vời khi bạn cần làm cho kịch bản của mình im lặng hoặc ghi chép mọi thứ mà không làm loãng bảng điều khiển.

Khi đến với thực thi, xử lý lỗi của PowerShell đặc biệt là sang trọng. Bạn có thể bắt các loại ngoại lệ khác nhau với các khối `try`, `catch`, `finally` và quyết định cách phản ứng. Đó giống như một cuộc phiêu lưu tự chọn cho quản lý lỗi.

## Xem thêm

- [Về Try, Catch, Finally](https://docs.microsoft.com/en-us/powershell/scripting/learn/deep-dives/everything-about-exceptions?view=powershell-7.1)
