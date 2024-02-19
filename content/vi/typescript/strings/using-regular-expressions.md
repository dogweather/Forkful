---
aliases:
- /vi/typescript/using-regular-expressions/
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:10:14.626476-07:00
description: "Bi\u1EC3u th\u1EE9c ch\xEDnh quy, hay c\xF2n g\u1ECDi l\xE0 regex, l\xE0\
  \ m\u1ED9t c\xF4ng c\u1EE5 m\u1EA1nh m\u1EBD \u0111\u1EC3 t\xECm ki\u1EBFm v\xE0\
  \ kh\u1EDBp m\u1EABu trong l\u1EADp tr\xECnh. C\xE1c l\u1EADp tr\xECnh vi\xEAn s\u1EED\
  \ d\u1EE5ng regex cho nh\u1EEFng t\xE1c\u2026"
lastmod: 2024-02-18 23:08:50.404038
model: gpt-4-0125-preview
summary: "Bi\u1EC3u th\u1EE9c ch\xEDnh quy, hay c\xF2n g\u1ECDi l\xE0 regex, l\xE0\
  \ m\u1ED9t c\xF4ng c\u1EE5 m\u1EA1nh m\u1EBD \u0111\u1EC3 t\xECm ki\u1EBFm v\xE0\
  \ kh\u1EDBp m\u1EABu trong l\u1EADp tr\xECnh. C\xE1c l\u1EADp tr\xECnh vi\xEAn s\u1EED\
  \ d\u1EE5ng regex cho nh\u1EEFng t\xE1c\u2026"
title: "S\u1EED d\u1EE5ng bi\u1EC3u th\u1EE9c ch\xEDnh quy"
---

{{< edit_this_page >}}

## Gì và Tại sao?
Biểu thức chính quy, hay còn gọi là regex, là một công cụ mạnh mẽ để tìm kiếm và khớp mẫu trong lập trình. Các lập trình viên sử dụng regex cho những tác vụ như xác minh dữ liệu người dùng, tìm kiếm trong văn bản, hoặc thao tác với chuỗi vì nó hiệu quả và đa năng.

## Làm thế nào:

Hãy nhảy vào TypeScript và xem regex được sử dụng như thế nào cho các tác vụ phổ biến.

```TypeScript
// Định nghĩa một mẫu regex cho địa chỉ email
const emailPattern = /\S+@\S+\.\S+/;

// Kiểm tra xem một chuỗi có khớp với mẫu email hay không
const email = "user@example.com";
console.log(emailPattern.test(email)); // Kết quả: true

// Tìm và thay thế các chữ số trong một chuỗi
const replaceDigits = "Item 25 costs $30".replace(/\d+/g, '#');
console.log(replaceDigits); // Kết quả: "Item # costs $#"

// Trích xuất các phần cụ thể từ một chuỗi sử dụng nhóm bắt
const data = "April 10, 2021";
const datePattern = /(\w+) (\d+), (\d+)/;
const [, month, day, year] = datePattern.exec(data) || [];
console.log(month, day, year); // Kết quả: "April" "10" "2021"
```

## Sâu hơn

Trở lại những năm 1950, nhà toán học Stephen Kleene mô tả biểu thức chính quy như một mô hình để đại diện cho các ngôn ngữ chính quy, sau này trở thành một phần thiết yếu trong khoa học máy tính. Nhanh chóng về sau, regex trở nên phổ biến trong lập trình để xử lý văn bản.

Mặc dù regex là một công cụ đa năng cho các thao tác với chuỗi, nó không phải không có những lựa chọn khác. Tùy thuộc vào độ phức tạp của tác vụ, đôi khi các phương thức chuỗi như `includes()`, `startsWith()`, `endsWith()`, hoặc thậm chí phân tích cú pháp với một thư viện có thể tốt hơn. Ví dụ, phân tích một chuỗi JSON phức tạp sử dụng regex có thể là một cơn ác mộng - hãy sử dụng bộ phân tích JSON thay thế.

Về việc triển khai, regex trong JavaScript và TypeScript dựa trên đặc tả ngôn ngữ ECMAScript. Bên dưới cùng, các engine sử dụng máy trạng thái để khớp mẫu một cách hiệu quả. Đáng lưu ý là các thao tác regex có thể tốn kém về mặt hiệu năng, đặc biệt là với các mẫu viết kém - hãy cảnh giác với "catastrophic backtracking".

## Xem Thêm

- Tài liệu Web MDN về Biểu Thức Chính Quy: [MDN Regular Expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions)
- Regex101: Một công cụ để kiểm tra và gỡ lỗi mẫu regex [Regex101](https://regex101.com/)
- Sách "Mastering Regular Expressions" cho hiểu biết sâu sắc: [O'Reilly](https://www.oreilly.com/library/view/mastering-regular-expressions/0596528124/)
