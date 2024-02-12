---
title:                "Phân tích ngày từ chuỗi kí tự"
aliases:
- /vi/typescript/parsing-a-date-from-a-string/
date:                  2024-01-28T22:04:42.665806-07:00
model:                 gpt-4-0125-preview
simple_title:         "Phân tích ngày từ chuỗi kí tự"

tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/typescript/parsing-a-date-from-a-string.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Tại sao & Lý do?
Phân tích cú pháp một ngày từ một chuỗi nghĩa là chuyển đổi văn bản thành một đối tượng Ngày (Date). Lập trình viên làm điều này để thao tác và sử dụng ngày theo định dạng mà máy tính hiểu được.

## Làm thế nào:

```TypeScript
// Phân tích cú pháp cơ bản sử dụng hàm tạo Date
const myDate = new Date('2020-01-01');
console.log(myDate.toString()); // Đầu ra: Wed Jan 01 2020 ...

// Phân tích cú pháp với một thư viện như date-fns
import { parseISO } from 'date-fns';

const myParsedDate = parseISO('2020-01-01');
console.log(myParsedDate.toString()); // Đầu ra: Wed Jan 01 2020 ...
```

Đầu ra mẫu cho cả hai:
```
Wed Jan 01 2020 00:00:00 GMT+0000 (Giờ Phối hợp Quốc tế)
```

## Sâu hơn

Phân tích cú pháp ngày từ chuỗi luôn là một điểm đau trong JavaScript, ngôn ngữ cơ bản của TypeScript. Việc phân tích cú pháp không chính xác hoặc không nhất quán trên các trình duyệt khác nhau đã khiến các lập trình viên tìm kiếm các giải pháp đáng tin cậy hơn.

Trong quá khứ, Moment.js là thư viện hàng đầu cho việc phân tích cú pháp và thao tác ngày, nhưng giờ đây nó được coi là một dự án lỗi thời. Các lựa chọn thay thế như date-fns và Day.js cung cấp chức năng tương tự với kích thước nhỏ gọn hơn.

Phân tích cú pháp bao gồm việc xử lý các định dạng, múi giờ và địa phương. Các quốc gia khác nhau có thể có các định dạng ngày khác nhau, ví dụ, `MM/DD/YYYY` so với `DD/MM/YYYY`. Múi giờ có thể làm méo điểm thời gian thực tế được biểu diễn nếu không được xử lý đúng cách.

Phải chú trọng đặc biệt khi triển khai một trình phân tích cú pháp:

1. **Nhất quán**: Đảm bảo ngày được phân tích cú pháp theo cùng một cách trên tất cả các môi trường mà ứng dụng của bạn chạy.
2. **Xác thực**: Kiểm tra xem chuỗi có phải là một ngày hợp lệ không.
3. **Xử lý Địa phương & Múi giờ**: Sử dụng các thư viện hoặc API tích hợp sẵn như `Intl.DateTimeFormat` để xử lý điều này.

Các thư viện tóm tắt những phức tạp này, cho phép bạn phân tích cú pháp chuỗi thành các đối tượng ngày thông qua các lời gọi hàm đơn giản.

## Xem thêm

- Tài liệu về Date của MDN: [MDN Date](https://developer.mozilla.org/vi/docs/Web/JavaScript/Reference/Global_Objects/Date)
- Tài liệu về date-fns: [date-fns](https://date-fns.org/)
- Trang web của Day.js: [Day.js](https://day.js.org/)
- Bối cảnh lịch sử về Moment.js: [Moment.js](https://momentjs.com/docs/#/-project-status/)
