---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 21:56:26.367950-07:00
description: "So s\xE1nh hai ng\xE0y c\xF3 ngh\u0129a l\xE0 ki\u1EC3m tra xem ch\xFA\
  ng c\xF3 gi\u1ED1ng nhau kh\xF4ng, ho\u1EB7c x\xE1c \u0111\u1ECBnh ng\xE0y n\xE0\
  o \u0111\u1EBFn tr\u01B0\u1EDBc ho\u1EB7c sau. C\xE1c l\u1EADp tr\xECnh vi\xEAn\
  \ l\xE0m \u0111i\u1EC1u n\xE0y \u0111\u1EC3 x\u1EED l\xFD\u2026"
lastmod: '2024-03-13T22:44:36.224572-06:00'
model: gpt-4-0125-preview
summary: "So s\xE1nh hai ng\xE0y c\xF3 ngh\u0129a l\xE0 ki\u1EC3m tra xem ch\xFAng\
  \ c\xF3 gi\u1ED1ng nhau kh\xF4ng, ho\u1EB7c x\xE1c \u0111\u1ECBnh ng\xE0y n\xE0\
  o \u0111\u1EBFn tr\u01B0\u1EDBc ho\u1EB7c sau."
title: "So s\xE1nh hai ng\xE0y"
weight: 27
---

## Làm Thế Nào:
Elixir làm cho việc so sánh ngày trở nên dễ dàng. Dưới đây là ví dụ so sánh ngày hôm nay với ngày mai:

```elixir
{:ok, today} = Date.new(2023, 4, 1)
{:ok, tomorrow} = Date.new(2023, 4, 2)

# So sánh nếu giống nhau
Date.compare(today, today) # => :eq
# Đầu ra: :eq (bằng nhau)

# Ngày nào đến trước?
Date.compare(today, tomorrow) # => :lt
# Đầu ra: :lt (ít hơn)

# Ngày nào đến sau?
Date.compare(tomorrow, today) # => :gt
# Đầu ra: :gt (nhiều hơn)
```

## Tìm Hiểu Sâu
Trong lịch sử, việc so sánh ngày không phải lúc nào cũng là tính năng có sẵn trong các ngôn ngữ lập trình, và các lập trình viên sẽ phải tự tính toán sự chênh lệch theo giây hoặc ngày. Tuy nhiên, thư viện tiêu chuẩn của Elixir bao gồm mô-đun `Date` với hàm `compare/2` giúp đơn giản hóa nhiệm vụ này.

Các phương pháp thay thế cho việc quản lý thời gian sâu hơn tồn tại trong Elixir, như sử dụng mô-đun `DateTime` để so sánh thời gian chính xác đến giây hoặc microgiây.

Khi so sánh ngày, Elixir tính đến sự phức tạp của hệ thống lịch. Nó xử lý các năm nhuận, sự khác biệt về độ dài của các tháng, và các loại lịch khác nhau, dựa vào mô-đun `:calendar` của Erlang để đảm bảo độ chính xác.

## Tham Khảo Thêm
- Tài liệu mô-đun Date của Elixir: [https://hexdocs.pm/elixir/Date.html](https://hexdocs.pm/elixir/Date.html)
- Mô-đun lịch của Erlang: [http://erlang.org/doc/man/calendar.html](http://erlang.org/doc/man/calendar.html)
- Timex - thư viện Elixir cho ngày và giờ: [https://hexdocs.pm/timex/Timex.html](https://hexdocs.pm/timex/Timex.html)
