---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 21:57:49.527155-07:00
description: "Chuy\u1EC3n \u0111\u1ED5i m\u1ED9t ng\xE0y th\xE0nh chu\u1ED7i thay\
  \ \u0111\u1ED5i \u0111\u1ED1i t\u01B0\u1EE3ng ng\xE0y th\xE0nh \u0111\u1ECBnh d\u1EA1\
  ng v\u0103n b\u1EA3n. L\u1EADp tr\xECnh vi\xEAn l\xE0m \u0111i\u1EC1u n\xE0y \u0111\
  \u1EC3 d\u1EC5 \u0111\u1ECDc h\u01A1n, l\u01B0u tr\u1EEF ho\u1EB7c hi\u1EC3n th\u1ECB\
  \ ng\xE0y cho\u2026"
lastmod: '2024-03-13T22:44:36.334583-06:00'
model: gpt-4-0125-preview
summary: "Chuy\u1EC3n \u0111\u1ED5i m\u1ED9t ng\xE0y th\xE0nh chu\u1ED7i thay \u0111\
  \u1ED5i \u0111\u1ED1i t\u01B0\u1EE3ng ng\xE0y th\xE0nh \u0111\u1ECBnh d\u1EA1ng\
  \ v\u0103n b\u1EA3n."
title: "Chuy\u1EC3n \u0111\u1ED5i m\u1ED9t ng\xE0y th\xE0nh chu\u1ED7i"
weight: 28
---

## Làm thế nào:
```TypeScript
// Chuyển đổi đơn giản sử dụng toLocaleString()
let date = new Date();
let dateString = date.toLocaleString();
console.log(dateString); // "4/3/2023, 1:15:30 PM" (sẽ thay đổi tùy theo ngôn ngữ)

// Định dạng ISO sử dụng toISOString()
let isoString = date.toISOString();
console.log(isoString); // "2023-04-03T13:15:30.000Z"

// Định dạng tùy chỉnh sử dụng toLocaleDateString()
let customString = date.toLocaleDateString('en-US', {
  year: 'numeric',
  month: 'long',
  day: 'numeric',
});
console.log(customString); // "April 3, 2023"
```

## Tìm hiểu sâu hơn
Hãy nghĩ về định dạng chuỗi ngày như là hộ chiếu của nó, cho phép nó di chuyển qua các ranh giới hệ thống - từ cơ sở dữ liệu đến trang web. Lịch sử, chúng ta đã gặp vấn đề với các định dạng ngày không nhất quán, đó là lý do tại sao các tiêu chuẩn như ISO 8601 được giới thiệu. Điều này làm cho việc trao đổi ngày trở nên đơn giản trên toàn thế giới.

Các phương pháp thay thế cho các phương pháp được xây dựng sẵn? Thư viện! Moment.js đã là lựa chọn hàng đầu trong nhiều năm, nhưng ngày nay date-fns hoặc Luxon được ưa chuộng hơn - chúng nhẹ hơn và có tính mô-đun cao hơn.

Bản chất của những chuyển đổi này nằm ở các phương pháp được sử dụng. `toLocaleString()` dựa vào ngôn ngữ của người dùng, làm cho nó hoàn hảo để hiển thị cho người dùng. `toISOString()`, tuy nhiên, giữ trung thành với định dạng ISO 8601, điều này rất tuyệt vời cho việc tuần tự hóa và lưu trữ ngày trong một định dạng tiêu chuẩn. Và `toLocaleDateString()` cho bạn kiểm soát về hình thức, phục vụ cho nhu cầu phong cách cụ thể.

## Xem thêm
- [Đối tượng Ngày - MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)
- [Tài liệu date-fns](https://date-fns.org/docs/Getting-Started)
- [Tài liệu Luxon](https://moment.github.io/luxon/)
- [Định dạng ngày và thời gian ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)
