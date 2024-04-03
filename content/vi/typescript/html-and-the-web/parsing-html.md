---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:04:06.440217-07:00
description: "Ph\xE2n t\xEDch c\xFA ph\xE1p HTML c\xF3 ngh\u0129a l\xE0 l\u1ECDc qua\
  \ m\xE3 HTML \u0111\u1EC3 t\xECm ki\u1EBFm, tr\xEDch xu\u1EA5t ho\u1EB7c thao t\xE1\
  c th\xF4ng tin. L\u1EADp tr\xECnh vi\xEAn l\xE0m \u0111i\u1EC1u n\xE0y \u0111\u1EC3\
  \ t\u01B0\u01A1ng t\xE1c v\u1EDBi n\u1ED9i dung\u2026"
lastmod: '2024-03-13T22:44:36.316042-06:00'
model: gpt-4-0125-preview
summary: "Ph\xE2n t\xEDch c\xFA ph\xE1p HTML c\xF3 ngh\u0129a l\xE0 l\u1ECDc qua m\xE3\
  \ HTML \u0111\u1EC3 t\xECm ki\u1EBFm, tr\xEDch xu\u1EA5t ho\u1EB7c thao t\xE1c th\xF4\
  ng tin."
title: "Ph\xE2n T\xEDch C\xFA Ph\xE1p HTML"
weight: 43
---

## Làm thế nào:
Để bắt đầu, cài đặt một thư viện như `node-html-parser`. Dưới đây là lệnh terminal:

```bash
npm install node-html-parser
```

Bây giờ, hãy phân tích cú pháp một số HTML cơ bản trong TypeScript:

```typescript
import { parse } from 'node-html-parser';

const html = `<ul class="fruits">
                <li>Táo</li>
                <li>Chuối</li>
              </ul>`;

const root = parse(html);
console.log(root.querySelector('.fruits').textContent);  // "Táo Chuối"
```

Và nếu bạn muốn chỉ lấy chuối:

```typescript
const bananas = root.querySelectorAll('li')[1].textContent;
console.log(bananas);  // "Chuối"
```

## Sâu hơn
Việc phân tích cú pháp HTML không phải là mới—nó đã xuất hiện từ những ngày đầu của web. Ban đầu, các nhà phát triển có thể đã sử dụng biểu thức chính quy, nhưng điều đó trở nên rối rắm nhanh chóng. Bước vào bộ phân tích cú pháp DOM: ổn định, nhưng gắn liền với trình duyệt.

Các thư viện như `node-html-parser` giúp loại bỏ đi sự phiền toái. Chúng cho phép bạn truy vấn HTML giống như bạn sẽ làm với jQuery, nhưng phía máy chủ với Node.js. Nó nhanh chóng, dễ dung nạp với HTML "bẩn", và thân thiện với DOM.

Cũng có `jsdom`, mô phỏng một môi trường trình duyệt hoàn chỉnh. Nó nặng hơn nhưng tỉ mỉ hơn, tạo ra một Mô hình Đối tượng Tài liệu (DOM) đầy đủ để thao tác và tương tác.

Đừng quên Cheerio, hoặc. Nó kết hợp tốc độ với cú pháp giống jQuery và kích thước nhỏ gọn, đặt mình một cách hạnh phúc giữa hai cái trên.

## Xem Thêm
Nếu bạn khao khát biết thêm, hãy nhúng vào những cái này:
- [Quy định Phân tích cú pháp và Chuyển dạng DOM của W3C](https://www.w3.org/TR/DOM-Parsing/)
- [node-html-parser trên GitHub](https://github.com/taoqf/node-html-parser)
- [Kho lưu trữ jsdom trên GitHub](https://github.com/jsdom/jsdom)
- [Website Cheerio](https://cheerio.js.org/)
