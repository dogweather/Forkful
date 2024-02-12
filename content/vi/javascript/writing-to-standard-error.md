---
title:                "Ghi vào lỗi chuẩn"
aliases:
- vi/javascript/writing-to-standard-error.md
date:                  2024-01-28T22:14:06.246726-07:00
model:                 gpt-4-0125-preview
simple_title:         "Ghi vào lỗi chuẩn"

tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/javascript/writing-to-standard-error.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Gì và Tại sao?
Viết vào lỗi chuẩn (stderr) là việc xuất văn bản ra luồng lỗi. Nó tách biệt đầu ra bình thường (stdout) khỏi các lỗi, cho phép gỡ lỗi và phân tích log dễ dàng hơn.

## Cách thực hiện:

```javascript
// Viết một thông báo lỗi đơn giản vào stderr
console.error('Lỗi: Đã xảy ra sự cố');

// Ví dụ với đầu ra được định dạng
const errorCode = 404;
console.error(`Lỗi: Không tìm thấy trang - Mã ${errorCode}`);
```

Đầu ra mẫu:
```
Lỗi: Đã xảy ra sự cố
Lỗi: Không tìm thấy trang - Mã 404
```

## Sâu hơn
Theo lịch sử, các hệ thống giống Unix phân biệt giữa đầu ra chuẩn và lỗi chuẩn để cho phép xử lý riêng biệt các tin nhắn bình thường và tin nhắn lỗi. Trong khi `console.log` trong Javascript viết vào stdout, `console.error` cụ thể viết vào stderr.
Các phương án thay thế cho viết vào stderr bao gồm sử dụng `process.stderr.write()`, không bao gồm một ký tự dòng mới ở cuối, không giống như `console.error`.
Về cách thực hiện, khi viết script Node.js, đầu ra từ `console.error()` có thể được chuyển hướng riêng biệt từ `console.log()` khi thực thi một script từ dòng lệnh, điều này có thể hữu ích cho việc đăng nhập lỗi vào một tệp khác.

## Xem thêm
- MDN Web Docs về Console: https://developer.mozilla.org/en-US/docs/Web/API/Console/error
- Tài liệu Node.js về `process.stderr`: https://nodejs.org/api/process.html#process_process_stderr
- Giải thích về stdout so với stderr: https://www.jstor.org/stable/25860673
