---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:08:35.086875-07:00
description: "Trong Ruby, vi\u1EC7c g\u1EEDi m\u1ED9t y\xEAu c\u1EA7u HTTP v\u1EDB\
  i x\xE1c th\u1EF1c c\u01A1 b\u1EA3n bao g\u1ED3m vi\u1EC7c th\xEAm t\xEAn ng\u01B0\
  \u1EDDi d\xF9ng v\xE0 m\u1EADt kh\u1EA9u v\xE0o ti\xEAu \u0111\u1EC1 y\xEAu c\u1EA7\
  u c\u1EE7a b\u1EA1n. L\u1EADp tr\xECnh vi\xEAn l\xE0m\u2026"
lastmod: '2024-03-13T22:44:37.340180-06:00'
model: gpt-4-0125-preview
summary: "Trong Ruby, vi\u1EC7c g\u1EEDi m\u1ED9t y\xEAu c\u1EA7u HTTP v\u1EDBi x\xE1\
  c th\u1EF1c c\u01A1 b\u1EA3n bao g\u1ED3m vi\u1EC7c th\xEAm t\xEAn ng\u01B0\u1EDD\
  i d\xF9ng v\xE0 m\u1EADt kh\u1EA9u v\xE0o ti\xEAu \u0111\u1EC1 y\xEAu c\u1EA7u c\u1EE7\
  a b\u1EA1n."
title: "G\u1EEDi m\u1ED9t y\xEAu c\u1EA7u HTTP v\u1EDBi x\xE1c th\u1EF1c c\u01A1 b\u1EA3\
  n"
weight: 45
---

## Cách thực hiện:
Để gửi một yêu cầu HTTP với xác thực cơ bản, bạn thường sử dụng module `Net::HTTP` trong Ruby. Dưới đây là một ví dụ nhanh:

```Ruby
require 'net/http'
require 'uri'

uri = URI('http://example.com')
username = 'your_username'
password = 'your_password'

request = Net::HTTP::Get.new(uri)
request.basic_auth(username, password)

phản hồi = Net::HTTP.start(uri.hostname, uri.port) {|http|
  http.request(request)
}

puts phản hồi.body
```

Nếu bạn chạy mã này với thông tin đăng nhập hợp lệ, bạn sẽ thấy nội dung của phản hồi được in ra. Nếu thông tin đăng nhập không hợp lệ, bạn sẽ nhận được thông báo lỗi.

## Tìm hiểu kỹ hơn
Xác thực cơ bản có một lịch sử lâu dài trong các giao thức web, trở lại với các RFC đầu tiên định nghĩa hoạt động của internet. Đó là một phương pháp kiểm soát truy cập đơn giản: tên người dùng và mật khẩu được mã hóa bằng Base64 và truyền trong tiêu đề HTTP.

Tuy nhiên, xác thực cơ bản truyền thông tin đăng nhập dưới dạng văn bản thuần túy (mặc dù đã được mã hóa), vì vậy nó không an toàn qua HTTP. Sử dụng HTTPS sẽ tốt hơn để giữ thông tin đăng nhập an toàn khỏi những ánh mắt tò mò.

Có những phương pháp thay thế an toàn hơn như OAuth, thường được sử dụng cho xác thực API. OAuth cho phép người dùng ủy quyền truy cập của bên thứ ba mà không chia sẻ thông tin đăng nhập. Tuy nhiên, xác thực cơ bản vẫn được sử dụng, đặc biệt là cho các ứng dụng nội bộ và việc viết script nhanh chóng.

Một chi tiết cần lưu ý là `Net::HTTP` của Ruby không xử lý Xác thực Cơ bản nguyên thủy cho đến khi bạn rõ ràng sử dụng phương thức `basic_auth`. Cũng rất quan trọng để xử lý các ngoại lệ và phản hồi lỗi có thể xuất hiện từ yêu cầu HTTP.

## Xem Thêm
- Tài liệu thư viện tiêu chuẩn Ruby `Net::HTTP`: https://ruby-doc.org/stdlib-3.0.0/libdoc/net/http/rdoc/Net/HTTP.html
- RFC 7617, 'Lược đồ Xác thực HTTP "Cơ bản"': https://tools.ietf.org/html/rfc7617
- Giới thiệu về OAuth cho xác thực: https://oauth.net/2/
- Thêm thông tin về Ruby và yêu cầu HTTP: https://www.rubyguides.com/2019/08/ruby-http-request/
