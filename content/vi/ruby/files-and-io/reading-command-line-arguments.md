---
title:                "Đọc các đối số dòng lệnh"
aliases:
- vi/ruby/reading-command-line-arguments.md
date:                  2024-01-28T22:06:29.781501-07:00
model:                 gpt-4-0125-preview
simple_title:         "Đọc các đối số dòng lệnh"

tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/ruby/reading-command-line-arguments.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Cái gì và Tại sao?
Đọc các đối số dòng lệnh trong Ruby cho phép các kịch bản nhận đầu vào ngay khi chúng được chạy, như cấu hình tùy chọn hoặc truyền dữ liệu. Các lập trình viên sử dụng chúng để làm cho các kịch bản trở nên động và có thể thích ứng mà không cần cố định giá trị.

## Làm thế nào:
Để lấy các đối số dòng lệnh, Ruby cung cấp một mảng đơn giản: `ARGV`. Nó chứa tất cả các đối số được truyền vào, theo thứ tự chúng được đưa ra.

```Ruby
# hello.rb
name = ARGV[0] || "Thế giới"
puts "Xin chào, #{name}!"

# Chạy bằng: ruby hello.rb Alice
# Đầu ra: Xin chào, Alice!
```

Để xử lý nhiều đối số:

```Ruby
# greet.rb
name, time_of_day = ARGV
puts "Chào buổi #{time_of_day || 'ngày'}, #{name || 'bạn'}!"

# Chạy bằng: ruby greet.rb Bob Buổi sáng
# Đầu ra: Chào buổi Buổi sáng, Bob!
```

Tạo tùy chọn với một vòng lặp:

```Ruby
# options.rb
options = {}
ARGV.each do |arg|
  key, value = arg.split('=')
  options[key.to_sym] = value
end
p options

# Chạy bằng: ruby options.rb name=Tom age=30
# Đầu ra: {:name=>"Tom", :age=>"30"}
```

## Sâu hơn
Đọc các đối số dòng lệnh là một thực hành cũ như chính giao diện dòng lệnh. Nó liên quan đến việc sử dụng đầu vào của người dùng mà không cần GUI—cần thiết cho tự động hóa hoặc khi chạy kịch bản trên máy chủ.

`ARGV` của Ruby không phải là duy nhất; nhiều ngôn ngữ có điều gì đó tương tự. Tuy nhiên, cài đặt của Ruby tập trung vào sự đơn giản và cú pháp rõ ràng—không rắc rối, chỉ là một mảng.

Bên dưới bề mặt, `ARGV` chỉ là một thực thể của `Array` được điền trước với các đối số xuất hiện sau tên kịch bản trong lời gọi lệnh. Ruby thiết lập nó trước khi mã của bạn thậm chí được chạy, làm cho nó ngay lập tức sẵn sàng để sử dụng.

Có phương án thay thế? Chắc chắn. Đối với nhu cầu phức tạp, như phân tích cờ (ví dụ, `--verbose` hay `-v`), Ruby có lớp `OptionParser` trong thư viện chuẩn. Nó có thể xử lý nhiều hơn `ARGV`, như giá trị mặc định, chuyển đổi kiểu tự động và tạo thông điệp trợ giúp.

Đôi khi, bạn chỉ muốn biết liệu một đối số có được cung cấp hay không, bỏ qua giá trị của nó. Với mục đích đó, `ARGV.include?` giải quyết vấn đề.

## Xem thêm
- Giới thiệu về `OptionParser`: [https://ruby-doc.org/stdlib-2.7.0/libdoc/optparse/rdoc/OptionParser.html](https://ruby-doc.org/stdlib-2.7.0/libdoc/optparse/rdoc/OptionParser.html)
- Thêm về các đối số dòng lệnh trong Ruby: [https://www.rubyguides.com/2018/12/ruby-argv/](https://www.rubyguides.com/2018/12/ruby-argv/)
