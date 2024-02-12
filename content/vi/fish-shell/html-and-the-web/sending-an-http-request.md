---
title:                "Gửi một yêu cầu HTTP"
aliases:
- vi/fish-shell/sending-an-http-request.md
date:                  2024-01-28T22:07:44.495514-07:00
model:                 gpt-4-0125-preview
simple_title:         "Gửi một yêu cầu HTTP"

tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/fish-shell/sending-an-http-request.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Cái gì & Tại sao?

Gửi các yêu cầu HTTP là một cách để giao tiếp với các máy chủ web, tìm nạp hoặc gửi dữ liệu khi cần. Lập trình viên sử dụng các yêu cầu HTTP để tương tác với các API hoặc dịch vụ web, cho phép các ứng dụng truy cập vào các nguồn, dịch vụ và dữ liệu trên internet.

## Làm thế nào:

Fish không có các lệnh tích hợp sẵn để gửi các yêu cầu HTTP, nhưng bạn có thể sử dụng `curl` ngay từ shell:

```Fish
curl http://api.example.com/data
```

Đối với một yêu cầu POST với dữ liệu JSON:

```Fish
curl -X POST -H "Loại-Nội-Dung: ứng dụng/json" -d '{"key":"value"}' http://api.example.com/data
```

Để lưu trữ phản hồi:

```Fish
set response (curl -X GET http://api.example.com/data)
```

Và đây là những gì bạn có thể thấy sau một yêu cầu GET:

```Fish
{
  "response": "Một số dữ liệu từ máy chủ"
}
```

## Sâu hơn

Trong lịch sử, các shell UNIX và Linux luôn hữu ích cho các nhiệm vụ mạng. Ngày xưa, các công cụ như `telnet` thường được sử dụng cho mục đích như vậy. Ngày nay, các chương trình tiện ích như `curl` và `wget` là lựa chọn hàng đầu. `curl` là một công cụ đa năng hỗ trợ nhiều giao thức, và thường được sử dụng vì sự đơn giản và linh hoạt của nó.

Python hoặc Node.js có thể được sử dụng khi bạn cần xử lý yêu cầu phức tạp hơn. Nhưng đối với các nhiệm vụ nhanh chóng hoặc các script đơn giản, `curl` trong Fish hiệu quả và có hiệu lực.

Thực hiện một yêu cầu HTTP thông qua Fish thường nghĩa là dựa vào các công cụ bên thứ ba. Fish được thiết kế để là một shell dòng lệnh thông minh và thân thiện với người dùng, không phải là một công cụ làm mọi việc. Khi bạn kết hợp nó với sức mạnh của các tiện ích như `curl`, bạn có được điều tốt nhất từ cả hai thế giới: sự dễ sử dụng của Fish và khả năng của `curl`.

## Xem thêm

- Tìm hiểu thêm về `curl`: https://curl.se/docs/manual.html
- Tài liệu về Shell Fish: https://fishshell.com/docs/current/index.html
- Tổng quan cơ bản về HTTP: https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview
- Khám phá APIs với `httpie`, một lựa chọn thay thế cho `curl`: https://httpie.io/
