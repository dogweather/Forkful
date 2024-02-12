---
title:                "Xóa các ký tự phù hợp với một mẫu"
aliases:
- vi/fish-shell/deleting-characters-matching-a-pattern.md
date:                  2024-01-28T21:59:17.580075-07:00
model:                 gpt-4-0125-preview
simple_title:         "Xóa các ký tự phù hợp với một mẫu"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/fish-shell/deleting-characters-matching-a-pattern.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Cái gì & Tại sao?

Xóa các ký tự phù hợp với một mẫu cụ thể chính là quá trình lọc bỏ các ký tự hoặc chuỗi không mong muốn khỏi chuỗi hoặc nội dung tệp dựa trên các quy tắc, được biết đến là mẫu. Lập trình viên thực hiện điều này để làm sạch dữ liệu, chuẩn bị cho quá trình xử lý, hoặc để trích xuất thông tin có ý nghĩa mà không có "tiếng ồn".

## Làm thế nào:

```Fish Shell
# Xóa số từ một chuỗi
set string "Fish123Shell"
echo $string | string replace -ra '[0-9]' ''
# Kết quả: FishShell

# Loại bỏ tất cả trừ các chữ cái thường
set noisy_string "F!i@s#h$%S^h&e*l(l)__+"
echo $noisy_string | string match -r '[a-z]+'
# Kết quả: ishhell
```

## Đi sâu hơn

Trong Fish Shell, điều kỳ diệu xảy ra với tiện ích `string`, một công cụ tiện lợi có sẵn cho các thao tác chuỗi - được giới thiệu trong phiên bản 2.3.0. Trước đây, người dùng sẽ phải dùng đến các công cụ UNIX quen thuộc như `sed` hoặc `awk`. Tại sao lại thay đổi? Sự đơn giản và tích hợp. Có một giải pháp nội bộ làm cho việc thao tác chuỗi trở nên đơn giản hơn, khiến các script dễ đọc và bảo trì hơn.

Có lựa chọn khác không? Chắc chắn, `sed` cũ kỹ vẫn có thể làm được việc:

```Fish Shell
set old_school_string "Fish@Shell2023"
echo $old_school_string | sed 's/[0-9]//g'
# Kết quả: Fish@Shell
```

Nhưng tại sao không tận dụng công cụ của chính Fish? Để thực hiện, `string replace` có tùy chọn `-r` cho phép sử dụng mẫu regex. `-a` áp dụng lệnh cho tất cả các trận đấu, và thêm một '' ở cuối báo hiệu cho nó thay thế bằng không cái gì, tức là xóa. Sử dụng `string match` khi tìm kiếm một mẫu cần giữ, thay vì cái cần bỏ.

## Xem thêm

- Tài liệu chính thức của Fish Shell về `string`: https://fishshell.com/docs/current/cmds/string.html
- Hướng dẫn Regex để đi sâu vào các mẫu: https://www.regular-expressions.info/
- Sed & Awk, sức mạnh văn bản cổ điển: giới thiệu: https://www.gnu.org/software/sed/manual/sed.html, http://www.grymoire.com/Unix/Awk.html
