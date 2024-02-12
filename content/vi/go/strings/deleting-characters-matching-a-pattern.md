---
title:                "Xóa các ký tự khớp với một mô hình"
date:                  2024-02-03T17:55:58.645173-07:00
model:                 gpt-4-0125-preview
simple_title:         "Xóa các ký tự khớp với một mô hình"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/go/deleting-characters-matching-a-pattern.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Gì và Tại sao?

Xóa các ký tự phù hợp với một mẫu nhất định liên quan đến việc loại bỏ các ký tự hoặc chuỗi ký tự cụ thể khỏi chuỗi, dựa trên các quy tắc được xác định bởi một mẫu (thường qua biểu thức chính quy). Lập trình viên thường xuyên cần thực hiện công việc này để làm sạch dữ liệu, tiền xử lý cho phân tích, định dạng đầu ra, hoặc đơn giản là thao tác chuỗi để đáp ứng yêu cầu của ứng dụng.

## Làm thế nào:

Trong Go, việc xóa các ký tự phù hợp với mẫu có thể được thực hiện một cách hiệu quả sử dụng gói `regexp`. Ở đây, chúng tôi sẽ chỉ cách loại bỏ tất cả các chữ số, sau đó là tất cả các ký tự không phải chữ và số từ một chuỗi như các ví dụ.

1. **Loại bỏ tất cả các chữ số:**

```go
package main

import (
    "fmt"
    "regexp"
)

func main() {
    text := "Go1 là tốt, nhưng Go2 sẽ tốt hơn! Bây giờ: 2023."
	
    // Biên dịch biểu thức chính quy cho các chữ số
    re, err := regexp.Compile("[0-9]+")
    if err != nil {
        fmt.Println("Lỗi khi biên dịch regex:", err)
        return
    }
	
    // Thay thế các chữ số bằng chuỗi trống
    result := re.ReplaceAllString(text, "")
	
    fmt.Println(result) // Kết quả: Go là tốt, nhưng Go sẽ tốt hơn! Bây giờ: .
}
```

2. **Loại bỏ tất cả các ký tự không phải chữ và số:**

```go
package main

import (
    "fmt"
    "regexp"
)

func main() {
    text := "Go là #1 @ ngôn ngữ lập trình!"
	
    // Biên dịch biểu thức chính quy cho các ký tự không phải chữ và số
    re, err := regexp.Compile("[^a-zA-Z0-9]+")
    if err != nil {
        fmt.Println("Lỗi khi biên dịch regex:", err)
        return
    }
	
    // Thay thế các ký tự không phải chữ và số bằng chuỗi trống
    result := re.ReplaceAllString(text, "")
	
    fmt.Println(result) // Kết quả: Golà1ngônngữlậptrình
}
```

## Tìm hiểu sâu

Gói `regexp` trong Go cung cấp một giao diện mạnh mẽ cho việc khớp mẫu và thao tác với biểu thức chính quy. Mọi triển khai của nó đều được dẫn xuất từ RE2, một thư viện biểu thức chính quy được thiết kế để đảm bảo thời gian thực hiện tuyến tính, tránh khả năng gặp phải vấn đề "quay lui thảm họa" xuất hiện trong một số động cơ regex khác. Điều này làm cho regex của Go tương đối an toàn và hiệu quả cho một loạt ứng dụng rộng lớn.

Mặc dù gói `regexp` là một giải pháp toàn diện để xử lý các mẫu, cần lưu ý rằng đối với việc thao tác chuỗi đơn giản hoặc cụ thể cao, các hàm chuỗi khác như `strings.Replace()`, `strings.Trim()`, hoặc cắt chuỗi có thể cung cấp các giải pháp hiệu suất cao hơn. Biểu thức chính quy là một công cụ mạnh mẽ, nhưng chi phí tính toán tương đối của chúng có nghĩa là đối với các thao tác có thể được xác định mà không cần chúng, việc khám phá các giải pháp thư viện tiêu chuẩn đôi khi có thể dẫn đến mã đơn giản và hiệu quả hơn.
