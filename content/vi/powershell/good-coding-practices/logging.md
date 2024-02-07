---
title:                "Ghi log"
date:                  2024-01-28T22:03:02.806981-07:00
model:                 gpt-4-0125-preview
simple_title:         "Ghi log"

tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/powershell/logging.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Gì và Tại sao?
Logging là việc để lại dấu vết qua code của bạn - đó là cách bạn theo dõi những gì đang xảy ra khi script của bạn được thực thi tự do. Lập trình viên log để debug, theo dõi hành vi ứng dụng, giám sát hiệu suất và để ý đến bất kỳ điều gì nghịch ngợm.

## Cách thực hiện:
Dưới đây là thông tin chi tiết về cách thêm một số logging cơ bản vào script của bạn:

```PowerShell
# Tạo một thông điệp log đơn giản
Write-Host "Info: Bắt đầu quá trình script."

# Ghi vào một file
"Info: Đây là một thông điệp log." | Out-File -Append myLog.log

# Sử dụng cmdlet có sẵn để log chi tiết hơn
Start-Transcript -Path "./detailedLog.log"
Write-Output "Cảnh báo: Có điều gì đó không ổn."
# ... script của bạn thực hiện công việc
Stop-Transcript

# Kết quả của detailedLog.log
******************************
Khởi đầu ghi chép Windows PowerShell 
Thời gian bắt đầu: 20230324112347
Tên người dùng: PShellGuru@example.com
Chạy với quyền người dùng: PShellGuru@example.com
Tên cấu hình: 
Máy: PS-DEVBOX (Microsoft Windows NT 10.0.17763.0)
Ứng dụng chủ: C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe
ID quá trình: 2024
Phiên bản PS: 7.1.2
```

Bây giờ, trong log của bạn, có một báo cáo chi tiết về những gì code của bạn đã làm.

## Sâu hơn:
Lịch sử logging cũng cũ như chính lập trình. Nó giống như sổ log của thuyền trưởng nhưng dành cho phần mềm. Trước đây, có thể là in ấn hay máy đánh chữ; giờ đây tất cả là về file và hệ thống quản lý log phức tạp.

Khi bạn đang đào sâu vào PowerShell, `Write-Host` nhanh và dơ bẩn, nhưng chỉ đơn thuần là phun ra văn bản ra console, không tốt cho việc lưu trữ. `Out-File` cho bạn một cách đơn giản để đưa văn bản vào một file, nhưng để có được cái chất, bạn sẽ muốn sử dụng `Start-Transcript` và `Stop-Transcript` ghi lại mọi thứ—đầu vào, đầu ra, toàn bộ công việc.

Có sự lựa chọn khác không? Chắc chắn, nếu bạn đang triển khai ở quy mô doanh nghiệp, bạn có thể xem xét Windows Event Log hoặc sử dụng phần mềm như Logstash, nhưng cho việc script hàng ngày của bạn, hãy gắn bó với công cụ của PowerShell. Về việc triển khai, hãy nhớ log một cách thông minh – ít quá thì vô dụng, nhiều quá thì chỉ là tiếng ồn.

## Xem thêm:
Kiểm tra những điều này để nắm vững mọi thứ về logging trong PowerShell:
