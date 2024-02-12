---
title:                "Làm việc với XML"
aliases:
- /vi/elm/working-with-xml/
date:                  2024-01-28T22:12:34.722114-07:00
model:                 gpt-4-0125-preview
simple_title:         "Làm việc với XML"

tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/elm/working-with-xml.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Gì và Tại sao?
Làm việc với XML bao gồm việc phân tích cú pháp, biến đổi, và tạo ra các tài liệu XML trong Elm. Việc này được thực hiện để tương tác với nhiều dịch vụ web và hệ thống cũ dùng XML làm định dạng dữ liệu của họ.

## Làm thế nào:
Trong Elm, bạn xử lý XML sử dụng gói `elm/xml`. Dưới đây là cái nhìn nhanh về cách phân tích cú pháp một đoạn XML:

```Elm
import Xml.Decode exposing (..)
import Xml.Decode.Pipeline exposing (..)

xmlString = """
<book id="123">
    <title>Elm in Action</title>
    <author>Robin Heggelund Hansen</author>
</book>
"""

type alias Book =
    { id : String
    , title : String
    , author : String
    }

bookDecoder : Decoder Book
bookDecoder =
    decode Book
        |> required "id" (attribute "id")
        |> required "title" (child "title" (content text))
        |> required "author" (child "author" (content text))

case Xml.Decode.fromString bookDecoder xmlString of
    Ok book ->
        -- Làm gì đó với book đã giải mã ở đây
        Debug.toString book

    Err error ->
        -- Xử lý lỗi
        Debug.toString error
```

Đầu ra mẫu, với giả định không có lỗi:

```Elm
"{ id = \"123\", title = \"Elm in Action\", author = \"Robin Heggelund Hansen\" }"
```

## Sâu hơn
XML (Ngôn ngữ Đánh dấu Mở rộng) đã xuất hiện từ cuối những năm 90, thời điểm mà web chứa đựng nhiều văn bản và cần một cách có cấu trúc nhưng linh hoạt để chứa dữ liệu là rất quan trọng. Do sự dài dòng và phức tạp, XML đã mất một số lượng đất so với JSON. Tuy nhiên, XML vẫn còn phổ biến, đặc biệt là trong môi trường doanh nghiệp hoặc các giao thức như SOAP.

Cách tiếp cận của Elm đối với XML là hàm (functional) và kiểm tra kiểu một cách an toàn. Sử dụng gói `elm/xml` có nghĩa là bạn chấp nhận triết lý của Elm về sự rõ ràng và tin cậy. Khi nói đến phân tích cú pháp, gói này cung cấp một loạt các bộ giải mã mà bạn kết hợp để xử lý cấu trúc XML.

So với các phương án khác như DOMParser của JavaScript hoặc ElementTree của Python, phương pháp của Elm có thể có vẻ dài dòng hơn nhưng đảm bảo an toàn. Không có ngoại lệ thời gian chạy do trường bị thiếu hoặc sai lệch kiểu; nếu có gì không ổn, bạn sẽ nhận được lỗi tại thời điểm biên dịch.

Các hàm giải mã của `elm/xml` dựa trên việc ánh xạ các nút XML sang các kiểu trong Elm. Bạn xây dựng bộ giải mã phản ánh hình dạng dữ liệu của mình, đảm bảo ứng dụng Elm của bạn xử lý XML một cách nghiêm ngặt như chính cấu trúc dữ liệu nội bộ của nó.

Việc tạo ra XML trong Elm không phổ biến nhưng có thể thực hiện được với `elm/xml` và phần đối ứng là `Xml.Encode`.

## Xem thêm
- Hướng dẫn Elm về JSON cũng áp dụng cho tư duy XML: [https://guide.elm-lang.org/interop/json.html](https://guide.elm-lang.org/interop/json.html)
- Tiêu chuẩn XML của W3C để hiểu sâu hơn về XML: [https://www.w3.org/XML/](https://www.w3.org/XML/)
