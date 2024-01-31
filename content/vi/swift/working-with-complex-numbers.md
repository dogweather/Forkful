---
title:                "Làm việc với số phức"
date:                  2024-01-28T22:12:27.223409-07:00
model:                 gpt-4-0125-preview
simple_title:         "Làm việc với số phức"

tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/swift/working-with-complex-numbers.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Cái gì & Tại sao?
Số phức có một phần thực và một phần ảo (như 3 + 4i). Lập trình viên sử dụng chúng trong Swift cho các nhiệm vụ như xử lý tín hiệu, giải quyết một số vấn đề toán học, và mô phỏng vật lý.

## Làm thế nào:
Swift không hỗ trợ số phức một cách sẵn có, nhưng chúng ta có thể tự lập trình:

```Swift
struct ComplexNumber {
    var real: Double
    var imaginary: Double
    
    func add(_ other: ComplexNumber) -> ComplexNumber {
        return ComplexNumber(real: real + other.real, imaginary: imaginary + other.imaginary)
    }
    
    // Các phương pháp khác như trừ, nhân, v.v.
}

let first = ComplexNumber(real: 2, imaginary: 3)
let second = ComplexNumber(real: 1, imaginary: 4)
let result = first.add(second)
print("Kết quả: \(result.real) + \(result.imaginary)i")
// Kết quả mẫu: Kết quả: 3.0 + 7.0i
```

## Sâu hơn
Số phức xuất hiện vào thế kỷ 16 trong các phương trình đại số. Chúng là yếu tố thiết yếu trong cơ học lượng tử, lý thuyết điều khiển, và nhiều lĩnh vực khác. Swift của Apple không có thư viện tiêu chuẩn cho số phức, không giống như các ngôn ngữ như Python hay C++. Các lựa chọn thay thế để tự lập trình bao gồm sử dụng gói Numerics bao gồm hỗ trợ số phức hoặc đóng gói thư viện phức của C++ với khả năng tương tác của Swift.

## Xem thêm
- Swift Numerics: [https://github.com/apple/swift-numerics](https://github.com/apple/swift-numerics)
