---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:09:37.488776-07:00
description: "Debugger l\xE0 m\u1ED9t c\xF4ng c\u1EE5 gi\xFAp l\u1EADp tr\xECnh vi\xEA\
  n hi\u1EC3u r\xF5 h\u01A1n v\u1EC1 vi\u1EC7c code c\u1EE7a h\u1ECD th\u1EF1c s\u1EF1\
  \ \u0111ang th\u1EF1c hi\u1EC7n nh\u1EEFng g\xEC khi n\xF3 ch\u1EA1y. \u0110\xF3\
  \ l\xE0 chi\u1EBFc k\xEDnh l\xFAp gi\xFAp ch\xFAng\u2026"
lastmod: '2024-03-13T22:44:36.772838-06:00'
model: gpt-4-0125-preview
summary: "Debugger l\xE0 m\u1ED9t c\xF4ng c\u1EE5 gi\xFAp l\u1EADp tr\xECnh vi\xEA\
  n hi\u1EC3u r\xF5 h\u01A1n v\u1EC1 vi\u1EC7c code c\u1EE7a h\u1ECD th\u1EF1c s\u1EF1\
  \ \u0111ang th\u1EF1c hi\u1EC7n nh\u1EEFng g\xEC khi n\xF3 ch\u1EA1y. \u0110\xF3\
  \ l\xE0 chi\u1EBFc k\xEDnh l\xFAp gi\xFAp ch\xFAng\u2026"
title: "S\u1EED d\u1EE5ng b\u1ED9 g\u1EE1 l\u1ED7i"
---

## Làm thế nào:
PHP đi kèm với một debugger tương tác có tên là Xdebug. Dưới đây là cách sử dụng nó.

Đầu tiên, hãy đảm bảo bạn đã cài đặt và cấu hình Xdebug trong tệp `php.ini` của bạn:

```
zend_extension=/usr/local/lib/php/extensions/no-debug-non-zts-xxxxxxxx/xdebug.so
xdebug.mode=debug
xdebug.start_with_request=yes
```

Tiếp theo, viết một script PHP đơn giản với một lỗi:

```PHP
<?php
function add($a, $b) {
    return $a - $b; // Ôi! Đáng lẽ phải là cộng, không phải trừ
}

$result = add(1, 2);
echo "Kết quả là: $result"; // Đầu ra cần là 3, không phải -1
```

Sử dụng một IDE như PhpStorm, đặt một điểm dừng bằng cách nhấp vào cạnh số dòng. Chạy debugger và xem biến thay đổi như thế nào khi bạn bước qua các bước thực thi. Khi bạn bước qua hàm `add`, bạn sẽ nhận thấy `$result` trở thành -1, điều này là không mong muốn.

## Sâu hơn:
Trong lịch sử, PHP chủ yếu được sử dụng cho các script nhỏ, và việc debug là việc thêm các câu lệnh `var_dump()` và `print_r()` khắp nơi trong code. Theo thời gian, với việc PHP trở thành một nhân tố quan trọng trong phát triển web, các công cụ phức tạp hơn như Xdebug và Zend Debugger được sử dụng.

Các lựa chọn thay thế cho Xdebug bao gồm pcov và phpdbg. Những cái này cung cấp các tính năng khác nhau nhưng có thể không hoàn chỉnh như Xdebug. phpdbg là một debugger nhẹ, cụ thể cho PHP và được phân phối cùng với PHP từ phiên bản 5.6, và pcov là một bộ điều khiển đo phủ code.

Khi triển khai một debugger, nhớ rằng bạn không bao giờ nên bật debugger trên máy chủ sản xuất của mình, vì nó có thể tiết lộ các lỗ hổng bảo mật và làm giảm hiệu suất.

## Xem thêm:
- [Tài liệu Xdebug](https://xdebug.org/docs/)
- [Hướng dẫn Debug với PhpStorm](https://www.jetbrains.com/help/phpstorm/debugging.html)
- [PHP.net về phpdbg](https://www.php.net/manual/en/book.phpdbg.php)
- [pcov trên GitHub](https://github.com/krakjoe/pcov)
