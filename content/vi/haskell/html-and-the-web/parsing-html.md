---
aliases:
- /vi/haskell/parsing-html/
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:04:06.053813-07:00
description: "Ph\xE2n t\xEDch c\xFA ph\xE1p HTML c\xF3 ngh\u0129a l\xE0 tr\xEDch xu\u1EA5\
  t d\u1EEF li\u1EC7u t\u1EEB t\xE0i li\u1EC7u HTML\u2014sau t\u1EA5t c\u1EA3, HTML\
  \ l\xE0 k\u1EBFt c\u1EA5u c\u1EE7a web. L\u1EADp tr\xECnh vi\xEAn ph\xE2n t\xED\
  ch c\xFA ph\xE1p HTML \u0111\u1EC3 t\u1EF1\u2026"
lastmod: 2024-02-18 23:08:50.742479
model: gpt-4-0125-preview
summary: "Ph\xE2n t\xEDch c\xFA ph\xE1p HTML c\xF3 ngh\u0129a l\xE0 tr\xEDch xu\u1EA5\
  t d\u1EEF li\u1EC7u t\u1EEB t\xE0i li\u1EC7u HTML\u2014sau t\u1EA5t c\u1EA3, HTML\
  \ l\xE0 k\u1EBFt c\u1EA5u c\u1EE7a web. L\u1EADp tr\xECnh vi\xEAn ph\xE2n t\xED\
  ch c\xFA ph\xE1p HTML \u0111\u1EC3 t\u1EF1\u2026"
title: "Ph\xE2n T\xEDch C\xFA Ph\xE1p HTML"
---

{{< edit_this_page >}}

## Cái Gì và Tại Sao?

Phân tích cú pháp HTML có nghĩa là trích xuất dữ liệu từ tài liệu HTML—sau tất cả, HTML là kết cấu của web. Lập trình viên phân tích cú pháp HTML để tự động hóa việc trích xuất dữ liệu, chuyển giao nội dung, hoặc biến đổi nó thành các định dạng khác nhau.

## Làm Thế Nào:

Hãy bắt tay vào một số mã lệnh, sử dụng thư viện `tagsoup` để phân tích một đoạn HTML đơn giản. Đầu tiên, hãy chắc chắn cài đặt gói từ Hackage qua `cabal install tagsoup`.

```Haskell
import Text.HTML.TagSoup

-- Hãy phân tích một đoạn HTML đơn giản
let html = "<html><body><p>Hello, Haskell!</p></body></html>"

-- Phân tích cú pháp nó
let parsedHtml = parseTags html

-- Tìm các đoạn văn
let paragraphs = partitions (~== "<p>") parsedHtml

-- Lấy văn bản từ đoạn đầu tiên
let firstParagraphText = innerText $ head paragraphs

-- Vào đây!
print firstParagraphText
```

Kết quả mẫu:
```
"Hello, Haskell!"
```
Đoạn mã này phân tích một chuỗi HTML, tìm kiếm các thẻ đoạn văn và in ra văn bản chứa trong đoạn đầu tiên. Gọn gàng và ngọt ngào.

## Sâu Hơn

Việc phân tích cú pháp HTML trong Haskell chưa bao giờ trở nên dễ dàng như ngày nay. Có một thời, mọi người tự làm trình phân tích cú pháp của riêng họ hoặc đấu tranh với các thư viện cấp thấp hơn, phân tích HTML như thể đó là miền Tây hoang dã.

Ngày nay, bạn có nhiều lựa chọn. `tagsoup`, như chúng tôi đã sử dụng, tuyệt vời cho khi cấu trúc HTML được xem xét nhiều hơn là một quy tắc—nó khoan dung với HTML hỗn loạn của thực tế. Nếu bạn đang tìm kiếm sự ngặt nghèo hơn, `html-conduit` kết hợp với `xml-conduit` từ gói `conduit` có thể là sự lựa chọn dành cho bạn. Chúng sử dụng phương pháp truyền dữ liệu và khắt khe hơn về cấu trúc.

Bên trong, các thư viện này chuyển đổi HTML thành một cây hoặc một bữa súp thẻ. Chúng cung cấp các hàm tiện ích để truy vấn và thao tác dữ liệu này, làm cho việc phân tích cú pháp HTML ít đau đầu hơn. Hãy nghĩ về chúng như một bản đồ tìm kho báu, nơi X đánh dấu thẻ đoạn văn.

## Xem Thêm

- [`tagsoup` trên Hackage](https://hackage.haskell.org/package/tagsoup)
- [`html-conduit` trên Hackage](https://hackage.haskell.org/package/html-conduit)
- [Tài liệu về Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/) - Mặc dù không phải Haskell, nhưng cách tiếp cận 'bữa súp thẻ' của Beautiful Soup đã ảnh hưởng lên các thư viện tương tự trong thế giới Haskell.
- [Hàm và Toán tử XPath và XQuery trên W3C](https://www.w3.org/TR/xpath-functions/) - Việc đi sâu vào các tiêu chuẩn có thể thông tin về cấu trúc và truy vấn của các tài liệu XML/HTML, hữu ích cho việc hiểu các chiến lược phân tích cú pháp phía sau.
