---
title:                "Kiểm tra xem thư mục có tồn tại không"
date:                  2024-01-28T21:56:38.822660-07:00
model:                 gpt-4-0125-preview
simple_title:         "Kiểm tra xem thư mục có tồn tại không"

tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/ruby/checking-if-a-directory-exists.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Điều gì & Tại sao?
Kiểm tra nếu một thư mục tồn tại có nghĩa là xác nhận xem một thư mục có mặt trong hệ thống tệp tin hay không. Lập trình viên thực hiện điều này để tránh lỗi trước khi thực hiện các thao tác tệp tin như đọc từ hoặc viết vào một thư mục.

## Cách thực hiện:

Trong Ruby, bạn có thể sử dụng phương thức `Dir.exist?` để kiểm tra nếu một thư mục tồn tại. Dưới đây là cách nó trông như thế nào:

```ruby
if Dir.exist?("/path/to/directory")
  puts "Thư mục tồn tại!"
else
  puts "Không có thư mục nào như vậy."
end
```

Kết quả mẫu khi thư mục tồn tại:

```
Thư mục tồn tại!
```

Và khi nó không tồn tại:

```
Không có thư mục nào như vậy.
```

## Sâu hơn

Lịch sử, Ruby đã cung cấp nhiều cách để tương tác với hệ thống tệp tin. `Dir.exist?` giờ đây là phương thức được ưa chuộng do sự rõ ràng và đơn giản của nó, nhưng mã nguồn cũ có thể sử dụng `File.directory?`. Cả hai phương thức này có nghĩa gần như là như nhau và có thể hoán đổi cho nhau.

```ruby
# Sử dụng File.directory? để đạt được kết quả tương tự
if File.directory?("/path/to/directory")
  puts "Thư mục tồn tại!"
else
  puts "Không có thư mục nào như vậy."
end
```

Tại sao lại có sự trùng lặp? Đó là một phần của nguyên tắc Ruby về việc cung cấp nhiều cách hơn cho lập trình viên để thực hiện thao tác. Tuy nhiên, `Dir.exist?` có thể được coi là cách chính xác về mặt ngữ nghĩa để kiểm tra cụ thể các thư mục.

Về mặt cài đặt bên dưới, khi bạn gọi `Dir.exist?`, Ruby yêu cầu hệ điều hành kiểm tra hệ thống tệp tin, xem đường dẫn được chỉ định có trỏ đến một thư mục hay không.

Khi nói đến các phương án thay thế, ngoài việc kiểm tra đường dẫn thủ công, bạn cũng có thể bắt các ngoại lệ phát sinh từ việc cố gắng truy cập vào một thư mục không tồn tại. Tuy nhiên, điều này không được khuyến khích vì nó tốn kém hơn về nguồn lực hệ thống và ít rõ ràng hơn đối với người đọc mã nguồn.

## Tham khảo thêm

Để tìm hiểu sâu hơn về việc xử lý tệp tin và thư mục trong Ruby, hãy tham khảo các nguồn tài liệu sau:

- Ruby Docs về lớp `Dir`: [https://ruby-doc.org/core/Dir.html](https://ruby-doc.org/core/Dir.html)
- Ruby Docs về lớp `File`: [https://ruby-doc.org/core/File.html](https://ruby-doc.org/core/File.html)
- Về các thực hành lập trình tốt trong xử lý lỗi: [https://www.honeybadger.io/blog/ruby-exception-vs-standarderror-whats-the-difference/](https://www.honeybadger.io/blog/ruby-exception-vs-standarderror-whats-the-difference/)
