---
title:                "Phân Tích Cú Pháp HTML"
date:                  2024-01-28T22:04:20.003186-07:00
model:                 gpt-4-0125-preview
simple_title:         "Phân Tích Cú Pháp HTML"

tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/c-sharp/parsing-html.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Lý do & Tại sao?
Phân tích cú pháp HTML có nghĩa là trích xuất thông tin từ các tài liệu HTML. Các lập trình viên thực hiện điều này để tương tác với nội dung web một cách lập trình, thu thập dữ liệu, hoặc tự động hóa các tương tác web.

## Cách thực hiện:
Hãy bắt đầu với một thư viện phổ biến của .NET dành cho phân tích cú pháp HTML: HtmlAgilityPack.

Đầu tiên, cài đặt nó qua NuGet:
```shell
Install-Package HtmlAgilityPack
```

Tiếp theo, tải một tài liệu HTML và lấy một số nút:

```C#
using System;
using HtmlAgilityPack;

class Program
{
    static void Main()
    {
        var web = new HtmlWeb();
        var doc = web.Load("http://example.com");

        foreach (var node in doc.DocumentNode.SelectNodes("//a[@href]"))
        {
            Console.WriteLine($"Text: {node.InnerText}, Link: {node.Attributes["href"].Value}");
        }
    }
}
```
Đoạn mã trên lấy tất cả các thẻ neo với thuộc tính `href` và in ra văn bản và liên kết của chúng.

Kết quả mẫu có thể trông như thế này:

```
Text: Home, Link: http://example.com/home
Text: About, Link: http://example.com/about
...
```

## Sâu hơn nữa
HtmlAgilityPack (HAP) đã là lựa chọn hàng đầu cho việc phân tích cú pháp kể từ đầu những năm 2000. Nó được yêu thích vì sự linh hoạt và dễ sử dụng, mô phỏng sát với DOM trong trình duyệt.

Có sự thay thế không? Chắc chắn rồi. AngleSharp là một thư viện mới hơn, với hỗ trợ bất đồng bộ và tuân thủ gần gũi hơn với các tiêu chuẩn web hiện tại. Đối với các tác vụ đơn giản, bạn thậm chí có thể sử dụng Regex, nhưng cảnh báo - HTML không được tạo ra để thân thiện với regex. Đây là một giải pháp khá mạnh mẽ ở mức tốt nhất.

Về cách thực hiện, HAP phân tích HTML được cung cấp thành một cấu trúc giống DOM, cho phép bạn truy vấn và thao tác các nút sử dụng XPath hoặc LINQ. Nó đủ mạnh mẽ để xử lý HTML kém chất lượng, tạo ra lợi thế trong việc thu thập trang web thực tế, thường không hoàn hảo.

## Xem thêm
- HtmlAgilityPack trên GitHub: [https://github.com/zzzprojects/html-agility-pack](https://github.com/zzzprojects/html-agility-pack)
- AngleSharp GitHub & tài liệu: [https://github.com/AngleSharp/AngleSharp](https://github.com/AngleSharp/AngleSharp)
- Bài viết về các phương pháp tốt nhất trong thu thập dữ liệu web: (liên kết đến nguồn uy tín với hướng dẫn và tính hợp pháp của việc thu thập dữ liệu web).
