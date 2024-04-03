---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:04:14.469372-07:00
description: "Chuy\u1EC3n \u0111\u1ED5i m\u1ED9t ng\xE0y t\u1EEB m\u1ED9t chu\u1ED7\
  i li\xEAn quan \u0111\u1EBFn vi\u1EC7c \u0111\u1ECDc th\xF4ng tin ng\xE0y th\xE1\
  ng \u0111\u01B0\u1EE3c \u0111\u1ECBnh d\u1EA1ng d\u01B0\u1EDBi d\u1EA1ng v\u0103\
  n b\u1EA3n v\xE0 chuy\u1EC3n \u0111\u1ED5i n\xF3 th\xE0nh c\u1EA5u tr\xFAc d\u1EEF\
  \ li\u1EC7u ng\xE0y\u2026"
lastmod: '2024-03-13T22:44:37.223622-06:00'
model: gpt-4-0125-preview
summary: "Chuy\u1EC3n \u0111\u1ED5i m\u1ED9t ng\xE0y t\u1EEB m\u1ED9t chu\u1ED7i li\xEA\
  n quan \u0111\u1EBFn vi\u1EC7c \u0111\u1ECDc th\xF4ng tin ng\xE0y th\xE1ng \u0111\
  \u01B0\u1EE3c \u0111\u1ECBnh d\u1EA1ng d\u01B0\u1EDBi d\u1EA1ng v\u0103n b\u1EA3\
  n v\xE0 chuy\u1EC3n \u0111\u1ED5i n\xF3 th\xE0nh c\u1EA5u tr\xFAc d\u1EEF li\u1EC7\
  u ng\xE0y m\xE0 ch\u01B0\u01A1ng tr\xECnh c\xF3 th\u1EC3 hi\u1EC3u \u0111\u01B0\u1EE3\
  c."
title: "Ph\xE2n t\xEDch ng\xE0y t\u1EEB chu\u1ED7i k\xED t\u1EF1"
weight: 30
---

## Làm thế nào:
```Fish Shell
# Phân tích cú pháp ngày cơ bản sử dụng hàm `strptime`
set date_string "2023-04-15"
set -l format "%Y-%m-%d"
set -l parsed_date (string tolower (date -u --date=$date_string +"$format"))

echo $parsed_date # Kết quả: 2023-04-15
```

```Fish Shell
# Xử lý nhiều định dạng ngày bằng cách sử dụng switch
set date_string1 "15-04-2023"
set date_string2 "April 15, 2023"

function parse_date -a date_string
    switch $date_string
        case "*-*-*"
            date --date=$date_string +%Y-%m-%d
        case "* *, *"
            date --date=$date_string +%Y-%m-%d
    end
end

echo (parse_date $date_string1) # Kết quả: 2023-04-15
echo (parse_date $date_string2) # Kết quả: 2023-04-15
```

## Tìm hiểu sâu
Fish Shell không có các hàm phân tích cú pháp ngày được tích hợp sẵn như một số ngôn ngữ khác. Thay vào đó, nó dựa vào các công cụ bên ngoài như `date`. Lệnh `date` rất linh hoạt, và với sự giúp đỡ từ `strptime` (phân tích cú pháp chuỗi thời gian), là một hàm thư viện chuẩn C, nó có thể xử lý nhiều định dạng ngày.

Trước `date` và `strptime`, lập trình viên viết bộ phân tích cú pháp tùy chỉnh—thường xuyên bị lỗi và phức tạp. Bây giờ, các công cụ xử lý các vấn đề về múi giờ và năm nhuận, giúp chúng ta tránh những phiền toái.

Có phương án thay thế? Chắc chắn, các ngôn ngữ kịch bản như Python có thư viện ngày-giờ mạnh mẽ như `datetime`. Nhưng Fish, với tư cách là một 'shell', thích sự nhẹ nhàng, các chương trình dòng lệnh cho công việc như thế này.

Trong các ví dụ của chúng tôi, chúng tôi đã sử dụng `switch` để chọn định dạng ngày để `date` phân tích cú pháp. Nó sạch sẽ và có thể mở rộng. Muốn thêm định dạng? Thêm nhiều khối `case`.

Tại sao sử dụng `string tolower` trong ví dụ đầu tiên? Điều này liên quan đến tính nhất quán, đảm bảo chuỗi định dạng và đầu ra có chữ cái viết thường đồng nhất. Một chi tiết nhỏ, nhưng nó minh họa sự ưa thích của Fish đối với các thao tác chuỗi đơn giản.

## Xem Thêm
- Trang hướng dẫn `date`: `man date`
- Tài liệu về thao tác chuỗi của Fish Shell: [https://fishshell.com/docs/current/cmds/string.html](https://fishshell.com/docs/current/cmds/string.html)
- Các ví dụ sử dụng lệnh ngày chung: [https://www.gnu.org/software/coreutils/manual/html_node/date-invocation.html](https://www.gnu.org/software/coreutils/manual/html_node/date-invocation.html)
