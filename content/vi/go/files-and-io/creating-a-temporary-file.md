---
title:                "Tạo một tệp tạm thời"
aliases:
- /vi/go/creating-a-temporary-file/
date:                  2024-02-03T17:55:53.842860-07:00
model:                 gpt-4-0125-preview
simple_title:         "Tạo một tệp tạm thời"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/go/creating-a-temporary-file.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Cái gì & Tại sao?

Việc tạo một tệp tạm thời trong Go cho phép tạo ra một tệp không lưu trữ lâu dài, được thiết kế để sử dụng trong thời gian ngắn, chủ yếu là cho các nhiệm vụ như lưu trữ dữ liệu trung gian hoặc hỗ trợ trong các công việc xử lý hàng loạt. Lập trình viên sử dụng tính năng này để an toàn xử lý dữ liệu mà không ảnh hưởng đến hệ thống tệp vĩnh viễn hoặc cần dọn dẹp thủ công.

## Làm thế nào:

Trong Go, gói `ioutil` ban đầu cung cấp các tiện ích cho việc tạo tệp tạm thời. Tuy nhiên, Go 1.16 đã thúc đẩy việc sử dụng các chức năng của gói `os` và `io/ioutil` vào những vị trí được tổ chức tốt hơn. Bây giờ, gói `os` và `io` được ưu tiên sử dụng để xử lý tệp tạm thời.

Dưới đây là hướng dẫn từng bước để tạo, viết vào và xóa một tệp tạm thời:

1. **Tạo Tệp Tạm Thời:**

Sử dụng hàm `os.CreateTemp`, bạn có thể tạo một tệp tạm thời. Nếu không chỉ định một thư mục, nó sử dụng thư mục tạm thời mặc định của hệ điều hành của bạn.

```go
package main

import (
    "io/ioutil"
    "log"
    "os"
)

func main() {
    tmpFile, err := ioutil.TempFile("", "example.*.txt")
    if err != nil {
        log.Fatal(err)
    }
    log.Printf("Đã tạo tệp tạm thời: %s\n", tmpFile.Name())

    defer os.Remove(tmpFile.Name()) // Dọn dẹp
}
```

2. **Viết vào Tệp Tạm Thời:**

Việc viết vào tệp có thể đạt được bằng phương thức `Write` hoặc các hàm viết khác từ gói `io` hoặc `bufio`.

```go
_, err = tmpFile.Write([]byte("Xin chào, Thế giới!"))
if err != nil {
    log.Fatal(err)
}
```

3. **Đọc từ Tệp Tạm Thời:**

Việc đọc tương tự, sử dụng phương thức `Read` của tệp, hoặc sử dụng các tiện ích từ gói `io` hoặc `bufio`.

```go
data, err := ioutil.ReadFile(tmpFile.Name())
if err != nil {
    log.Fatal(err)
}
log.Printf("Dữ liệu đã đọc: %s\n", string(data))
```

4. **Xóa Tệp Tạm Thời:**

Mặc dù câu lệnh `defer os.Remove(tmpFile.Name())` tại giai đoạn tạo bảo đảm rằng tệp tạm thời sẽ bị xóa sau khi chương trình kết thúc, việc xóa rõ ràng có thể được quản lý theo nhu cầu.

Đầu ra mẫu:
```
2023/04/01 15:00:00 Đã tạo tệp tạm thời: /tmp/example.123456.txt
2023/04/01 15:00:00 Dữ liệu đã đọc: Xin chào, Thế giới!
```

## Sâu hơn nữa

Cơ chế đằng sau việc Go xử lý tệp tạm thời đã phát triển. Ban đầu, việc tạo tệp tạm thời chủ yếu được quản lý bởi hàm `ioutil.TempFile` hiện đã lỗi thời, phản ánh xu hướng rộng lớn trong phát triển phần mềm hướng tới việc xử lý tệp một cách an toàn và hiệu quả hơn. Việc chuyển các chức năng này vào gói `os` và `io` với Go 1.16 biểu thị một sự thúc đẩy rộng rãi hơn nhằm tinh gọn thư viện chuẩn của ngôn ngữ và khuyến khích sử dụng các API thống nhất và đồng bộ hơn.

Mặc dù việc sử dụng tệp tạm thời là một thực hành phổ biến và thường là cần thiết trong lập trình, nhưng quan trọng là phải lưu ý rằng việc dựa quá nhiều vào chúng để lưu trữ lượng lớn dữ liệu hoặc cho các tác vụ dài hạn có thể dẫn đến vấn đề về hiệu suất. Hơn nữa, khi việc tạo tệp tạm thời không được kiểm soát chặt chẽ hoặc khi chúng không được dọn dẹp đầy đủ, có thể dẫn đến rò rỉ tài nguyên có thể ảnh hưởng tiêu cực đến hệ thống tệp. Trong các kịch bản đòi hỏi lưu trữ vĩnh viễn hoặc cần xử lý dòng dữ liệu lớn, các lựa chọn khác như cơ sở dữ liệu hoặc cửa hàng dữ liệu trong bộ nhớ thường cung cấp hiệu suất và độ tin cậy tốt hơn so với tệp tạm thời.
