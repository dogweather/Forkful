---
title:                "Lấy ngày hiện tại"
aliases:
- vi/ruby/getting-the-current-date.md
date:                  2024-01-28T22:01:44.584999-07:00
model:                 gpt-4-0125-preview
simple_title:         "Lấy ngày hiện tại"

tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/ruby/getting-the-current-date.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Cái gì & Tại sao?
Việc lấy ngày hiện tại trong Ruby cực kỳ đơn giản: lấy ngày của hôm nay. Các lập trình viên cần nó cho nhiều tác vụ khác nhau từ ghi log và đánh dấu thời gian cho tới lập lịch và kiểm tra tính hợp lệ.

## Làm thế nào:
Ruby giúp việc lấy ngày hiện tại trở nên rất dễ dàng. Dưới đây là cách làm:

```ruby
require 'date'

# Lấy ngày hiện tại
current_date = Date.today
puts current_date
```

Khi chạy đoạn mã này, nó sẽ in ra cái gì đó như thế này (tùy thuộc vào ngày bạn chạy nó):

```
2023-04-07
```

Bạn muốn có cả thời gian nữa? Dưới đây là mã nguồn:

```ruby
require 'time'

# Lấy ngày và giờ hiện tại
current_datetime = Time.now
puts current_datetime
```

Và kết quả đầu ra sẽ bao gồm cả dấu thời gian:

```
2023-04-07 12:34:56 +0900
```

## Sâu hơn nữa
Ngày xưa, các Rubyist cần đến các thư viện bên ngoài để quản lý ngày và giờ. Nhập cuộc thư viện chuẩn của Ruby với các lớp `Date` và `Time`, và nhu cầu cho những thứ phụ trợ chủ yếu đã thành quá khứ.

`Date` xử lý, ừ, ngày - ngày, tháng và năm. Để chính xác hơn, `DateTime` kết hợp ngày và giờ, nhưng nếu bạn chỉ cần giờ hoặc chi tiết cụ thể hơn như giây hoặc múi giờ, `Time` sẽ giúp bạn.

Những lựa chọn thay thế cho các lớp built-in của Ruby bao gồm các gems như 'timecop' để kiểm thử mã phụ thuộc vào thời gian, và 'chronic' để phân tích ngày từ ngôn ngữ tự nhiên.

Về cơ bản, `Date.today` kéo ngày từ hệ thống của bạn. Nó giữ mọi thứ đơn giản nhưng bỏ qua múi giờ. `Time.now` đi xa hơn, tính toán múi giờ với một độ lệch mặc định từ Coordinated Universal Time (UTC).

## Xem thêm
* Tài liệu của Ruby về lớp Time: [https://ruby-doc.org/core-2.7.0/Time.html](https://ruby-doc.org/core-2.7.0/Time.html)
* Gem 'timecop' để giả lập với thời gian: [https://github.com/travisjeffery/timecop](https://github.com/travisjeffery/timecop)
* Gem 'chronic' để phân tích ngày bằng ngôn ngữ tự nhiên: [https://github.com/mojombo/chronic](https://github.com/mojombo/chronic)
