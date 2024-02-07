---
title:                "Làm việc với XML"
date:                  2024-02-03T18:13:42.738341-07:00
model:                 gpt-4-0125-preview
simple_title:         "Làm việc với XML"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/go/working-with-xml.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Làm thế nào & Tại sao?

Làm việc với XML trong Go bao gồm việc phân tích cú pháp (đọc) và tạo (viết) các tài liệu XML - một định dạng chuẩn cho giao tiếp dữ liệu có cấu trúc. Lập trình viên làm điều này để lưu trữ dữ liệu, cài đặt cấu hình, hoặc trao đổi dữ liệu giữa các hệ thống, đặc biệt là trong các môi trường nơi XML là định dạng dữ liệu ưa thích hoặc kế thừa.

## Cách thực hiện:

### Phân tích cú pháp XML trong Go
Để phân tích cú pháp XML trong Go, bạn sử dụng gói `encoding/xml`. Gói này cung cấp các công cụ cần thiết để giải mã (phân tích cú pháp) XML thành cấu trúc Go. Ví dụ, xem xét dữ liệu XML sau đây đại diện cho một quyển sách:

```xml
<book id="123">
    <title>Learning Go</title>
    <author>John Doe</author>
    <pages>359</pages>
</book>
```

Để phân tích cú pháp này, hãy định nghĩa một cấu trúc phản ánh cấu trúc XML:

```go
package main

import (
    "encoding/xml"
    "fmt"
    "os"
)

type Book struct {
    XMLName xml.Name `xml:"book"`
    ID      string   `xml:"id,attr"`
    Title   string   `xml:"title"`
    Author  string   `xml:"author"`
    Pages   int      `xml:"pages"`
}

func main() {
    data := []byte(`
<book id="123">
    <title>Learning Go</title>
    <author>John Doe</author>
    <pages>359</pages>
</book>
`)

    var book Book
    err := xml.Unmarshal(data, &book)
    if err != nil {
        panic(err)
    }

    fmt.Printf("Book: %+v\n", book)
}
```

Kết quả đầu ra:

```
Book: {XMLName:{Space: Local:book} ID:123 Title:Learning Go Author:John Doe Pages:359}
```

### Tạo XML trong Go
Để tạo một tài liệu XML từ các cấu trúc dữ liệu Go, bạn lại sử dụng gói `encoding/xml`. Lần này, bạn chuyển cấu trúc Go thành XML. Xem xét cấu trúc `Book` trước đó:

```go
package main

import (
    "encoding/xml"
    "fmt"
    "os"
)

func main() {
    book := &Book{
        ID:     "123",
        Title:  "Learning Go",
        Author: "John Doe",
        Pages:  359,
    }

    output, err := xml.MarshalIndent(book, "", "    ")
    if err != nil {
        panic(err)
    }

    fmt.Println(xml.Header + string(output))
}
```

Kết quả đầu ra:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<book id="123">
    <title>Learning Go</title>
    <author>John Doe</author>
    <pages>359</pages>
</book>
```

## Tìm hiểu sâu

Độ phức tạp và dài dòng của XML đã khiến JSON và các định dạng khác trở nên phổ biến hơn cho nhiều ứng dụng. Tuy nhiên, khả năng biểu diễn dữ liệu phân cấp phức tạp của XML và sự sử dụng rộng rãi của nó trong các hệ thống kế thừa và các lĩnh vực cụ thể (ví dụ, dịch vụ SOAP) đảm bảo tính liên quan của nó.

Gói `encoding/xml` trong Go cung cấp các cơ chế mạnh mẽ để làm việc với XML, nhưng cần lưu ý các hạn chế của nó. Ví dụ, việc xử lý không gian tên XML có thể gặp khó khăn và có thể yêu cầu hiểu biết chi tiết hơn về thông số kỹ thuật XML so với các trường hợp sử dụng đơn giản hơn. Ngoài ra, trong khi kiểu định kiểu tĩnh của Go và khả năng chuyển đổi và giải mã của gói `encoding/xml` nói chung là hiệu quả, các lập trình viên có thể gặp phải thách thức với các cấu trúc lồng nhau sâu hoặc khi xử lý các tài liệu XML không ánh xạ gọn gàng vào hệ thống kiểu của Go.

Đối với hầu hết các ứng dụng hiện đại, các lựa chọn thay thế như JSON đơn giản và hiệu quả hơn. Tuy nhiên, khi làm việc trong các ngữ cảnh cần XML - do hệ thống kế thừa, tiêu chuẩn ngành cụ thể, hoặc nhu cầu biểu diễn dữ liệu phức tạp - thư viện chuẩn của Go cung cấp các công cụ mạnh mẽ để hoàn thành công việc. Như mọi khi, sự lựa chọn định dạng dữ liệu tốt nhất phụ thuộc vào yêu cầu cụ thể của ứng dụng và môi trường.
