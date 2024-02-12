---
title:                "Tải trang web"
aliases:
- vi/bash/downloading-a-web-page.md
date:                  2024-01-28T21:59:21.946145-07:00
model:                 gpt-4-0125-preview
simple_title:         "Tải trang web"

tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/bash/downloading-a-web-page.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Cái gì & Tại sao?
Tải xuống một trang web có nghĩa là lấy dữ liệu từ internet và lưu trữ cục bộ. Lập trình viên thực hiện điều này cho các mục đích như web scraping, phân tích ngoại tuyến, hoặc sao lưu.

## Cách thực hiện:
Công cụ tiêu biểu cho công việc này? `curl`. Đó là một tiện ích dòng lệnh mạnh mẽ giúp tải dữ liệu từ web. Dưới đây là trường hợp sử dụng đơn giản nhất:

```Bash
curl https://example.com -o webpage.html
```

Lệnh này tải HTML của `example.com` và ghi nó vào một tệp có tên là `webpage.html`. Kiểm tra đầu ra:

```Bash
# Đầu ra mẫu
  % Tổng cộng    % Đã nhận % Đã chuyển  Tốc độ trung bình   Thời gian   Thời gian     Thời gian  Hiện tại
                                 Tải xuống  Tải lên   Tổng cộng   Đã dùng    Còn lại  Tốc độ
100  1256  100  1256    0     0   6458      0 --:--:-- --:--:-- --:--:--  6497
```

Muốn xem bạn đang tải gì trong thời gian thực không? Bỏ qua `-o` và việc tải xuống sẽ in ngay trong bảng điều khiển của bạn:

```Bash
curl https://example.com
```

## Sâu hơn
`curl` đã xuất hiện từ năm 1997, tạo chỗ đứng cho mình trong các thao tác web. Tại sao lại chọn `curl` thay vì tải xuống bằng trình duyệt? Tự động hóa và thân thiện với kịch bản. Nó không tương tác và có thể dễ dàng tích hợp vào các kịch bản bash.

Các lựa chọn thay thế đáng nhắc: `wget`, một công cụ dòng lệnh khác có khả năng tải xuống các trang web một cách đệ quy. Đối với các công việc scraping nặng nhọc hoặc khi cần một ngữ cảnh trình duyệt thực sự, các lập trình viên chuyển sang sử dụng các công cụ như Selenium, Puppeteer, hoặc Scrapy.

Tìm hiểu sâu hơn về cách hoạt động của `curl`: Nó hỗ trợ nhiều giao thức, từ HTTP và HTTPS đến FTP, cùng với một loạt các lựa chọn (--header, --cookie, --user-agent, v.v.) để tinh chỉnh các yêu cầu. Hơn nữa, nó thường đã được cài đặt sẵn trên các hệ thống dựa trên Unix.

## Tham khảo thêm
- Tài liệu Curl: https://curl.haxx.se/docs/manpage.html
- Hướng dẫn Wget: https://www.gnu.org/software/wget/manual/wget.html
- Giới thiệu về web scraping với Python: https://realpython.com/python-web-scraping-practical-introduction/
