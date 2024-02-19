---
aliases:
- /vi/ruby/parsing-html/
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:04:33.249923-07:00
description: "Ph\xE2n t\xEDch c\xFA ph\xE1p HTML c\xF3 ngh\u0129a l\xE0 ph\xE2n t\xE1\
  ch m\u1ED9t kh\u1ED1i m\xE3 HTML \u0111\u1EC3 hi\u1EC3u r\xF5 c\u1EA5u tr\xFAc v\xE0\
  \ n\u1ED9i dung c\u1EE7a n\xF3. C\xE1c l\u1EADp tr\xECnh vi\xEAn th\u1EF1c hi\u1EC7\
  n \u0111i\u1EC1u n\xE0y \u0111\u1EC3 tr\xEDch xu\u1EA5t\u2026"
lastmod: 2024-02-18 23:08:51.282396
model: gpt-4-0125-preview
summary: "Ph\xE2n t\xEDch c\xFA ph\xE1p HTML c\xF3 ngh\u0129a l\xE0 ph\xE2n t\xE1\
  ch m\u1ED9t kh\u1ED1i m\xE3 HTML \u0111\u1EC3 hi\u1EC3u r\xF5 c\u1EA5u tr\xFAc v\xE0\
  \ n\u1ED9i dung c\u1EE7a n\xF3. C\xE1c l\u1EADp tr\xECnh vi\xEAn th\u1EF1c hi\u1EC7\
  n \u0111i\u1EC1u n\xE0y \u0111\u1EC3 tr\xEDch xu\u1EA5t\u2026"
title: "Ph\xE2n T\xEDch C\xFA Ph\xE1p HTML"
---

{{< edit_this_page >}}

## Cái gì & Tại sao?
Phân tích cú pháp HTML có nghĩa là phân tách một khối mã HTML để hiểu rõ cấu trúc và nội dung của nó. Các lập trình viên thực hiện điều này để trích xuất dữ liệu, thao túng nội dung, hoặc chuyển đổi thông tin giữa các định dạng và hệ thống.

## Cách thực hiện:
Để phân tích cú pháp HTML trong Ruby, hãy cài đặt gem 'Nokogiri' bằng câu lệnh `gem install nokogiri`. Nokogiri giống như một công cụ đa năng cho việc làm việc với HTML và XML trong Ruby. Dưới đây là một ví dụ nhanh:

```ruby
require 'nokogiri'
require 'open-uri'

# Tải nội dung HTML từ một trang web
html_content = URI.open('http://example.com').read

# Phân tích cú pháp HTML
doc = Nokogiri::HTML(html_content)

# Trích xuất tiêu đề
title = doc.xpath('//title').text
puts "Tiêu đề của trang là: #{title}"
```

Điều này sẽ cho kết quả như sau: `Tiêu đề của trang là: Example Domain`.

## Đi sâu hơn
Trong những ngày đầu của Ruby, các lựa chọn để phân tích cú pháp HTML bị hạn chế. REXML được tích hợp sẵn nhưng chậm. Sau đó, Hpricot xuất hiện nhưng nhanh chóng biến mất. Nokogiri ra mắt vào năm 2008, kết hợp sự dễ dàng của Hpricot với tốc độ và sức mạnh của libxml, một bộ công cụ XML đã được chứng minh.

Trong thế giới phân tích cú pháp, luôn luôn có những lựa chọn thay thế. Một số người tuyên thệ với thư viện 'rexml' được tích hợp sẵn hoặc 'oga', một trình phân tích cú pháp XML/HTML khác cho Ruby. Nhưng Nokogiri vẫn được yêu thích vì sự mạnh mẽ và tốc độ của nó, chưa kể đến vô vàn tính năng đa dạng của nó.

Bên trong, Nokogiri chuyển đổi HTML thành một Mô hình Đối tượng Tài liệu (DOM)—một cấu trúc dạng cây. Điều này làm cho việc điều hướng và thao tác các phần tử trở nên dễ dàng. Sử dụng XPath và các bộ chọn CSS, bạn có thể xác định chính xác bất kỳ thông tin nào bạn cần.

## Xem thêm
- Gem Nokogiri: [https://nokogiri.org/](https://nokogiri.org/)
- Tài liệu rexml của Ruby: [https://ruby-doc.org/stdlib-2.6.3/libdoc/rexml/rdoc/REXML/Document.html](https://ruby-doc.org/stdlib-2.6.3/libdoc/rexml/rdoc/REXML/Document.html)
- Trình phân tích cú pháp thay thế 'oga': [https://github.com/YorickPeterse/oga](https://github.com/YorickPeterse/oga)
- Tìm hiểu về XPath: [https://www.w3schools.com/xml/xpath_intro.asp](https://www.w3schools.com/xml/xpath_intro.asp)
