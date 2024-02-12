---
title:                "Gửi một yêu cầu HTTP"
aliases:
- vi/go/sending-an-http-request.md
date:                  2024-02-03T18:09:15.936698-07:00
model:                 gpt-4-0125-preview
simple_title:         "Gửi một yêu cầu HTTP"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/go/sending-an-http-request.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Gì & Tại sao?

Gửi một yêu cầu HTTP đề cập đến việc khởi tạo một cuộc gọi từ ứng dụng Go của bạn tới một web server, API, hoặc bất kỳ dịch vụ dựa trên HTTP nào khác. Lập trình viên thực hiện điều này để tương tác với tài nguyên web, lấy dữ liệu, gửi biểu mẫu, hoặc giao tiếp với các dịch vụ khác trên internet.

## Làm thế nào:

Trong Go, việc gửi một yêu cầu HTTP và xử lý phản hồi liên quan đến việc sử dụng gói `net/http`. Dưới đây là một ví dụ từng bước cho thấy cách gửi một yêu cầu GET đơn giản và đọc phản hồi:

```go
package main

import (
    "fmt"
    "io/ioutil"
    "log"
    "net/http"
)

func main() {
    // Định nghĩa URL của tài nguyên
    url := "http://example.com"

    // Sử dụng http.Get để gửi yêu cầu GET
    resp, err := http.Get(url)
    if err != nil {
        log.Fatal(err)
    }
    // Đóng body của phản hồi khi hàm kết thúc
    defer resp.Body.Close()

    // Đọc body của phản hồi
    body, err := ioutil.ReadAll(resp.Body)
    if err != nil {
        log.Fatal(err)
    }

    // Chuyển body phản hồi thành chuỗi và in ra
    fmt.Println(string(body))
}
```

Mẫu đầu ra (được rút ngắn cho gọn):
```
<!doctype html>
<html>
<head>
    <title>Example Domain</title>
...
</html>
```

Để gửi một yêu cầu POST với dữ liệu biểu mẫu, bạn có thể sử dụng `http.PostForm`:

```go
package main

import (
    "fmt"
    "io/ioutil"
    "net/http"
    "net/url"
)

func main() {
    // Định nghĩa URL và dữ liệu biểu mẫu
    url := "http://example.com/form"
    data := url.Values{}
    data.Set("key", "value")

    // Gửi yêu cầu POST với dữ liệu biểu mẫu
    resp, err := http.PostForm(url, data)
    if err != nil {
        panic(err)
    }
    defer resp.Body.Close()

    // Đọc và in phản hồi
    body, err := ioutil.ReadAll(resp.Body)
    if err != nil {
        panic(err)
    }

    fmt.Println(string(body))
}
```

## Sâu hơn

Gói `net/http` trong Go cung cấp một cách mạnh mẽ và linh hoạt để tương tác với các máy chủ HTTP. Thiết kế của nó phản ánh nhấn mạnh của Go vào sự đơn giản, hiệu quả, và độ bền. Ban đầu, các chức năng như xử lý tải trọng JSON hoặc XML yêu cầu việc tự mình tạo ra body của yêu cầu và thiết lập các headers phù hợp. Khi Go phát triển, cộng đồng đã phát triển các gói ở cấp độ cao hơn giúp đơn giản hóa những công việc này, chẳng hạn như `gorilla/mux` cho việc định tuyến và `gjson` cho việc thao tác JSON.

Một điểm đáng chú ý của khách hàng HTTP Go là việc sử dụng giao diện và cấu trúc, như `http.Client` và `http.Request`, cho phép tùy chỉnh và kiểm thử rộng rãi. Ví dụ, bạn có thể chỉnh sửa `http.Client` để hết thời gian yêu cầu hoặc giữ kết nối sống cho hiệu suất.

Một lựa chọn thay thế được xem xét cho các tương tác HTTP đơn giản hơn là sử dụng các thư viện bên thứ ba như "Resty" hoặc "Gentleman." Những gói này cung cấp một trừu tượng cấp cao hơn cho yêu cầu HTTP, làm cho các tác vụ phổ biến trở nên ngắn gọn hơn. Tuy nhiên, việc hiểu và sử dụng gói `net/http` cơ bản là rất quan trọng để xử lý các kịch bản tương tác HTTP phức tạp hoặc độc đáo hơn, cung cấp một nền tảng mà các tính năng đồng thời của Go và thư viện chuẩn mạnh mẽ có thể được khai thác triệt để.
