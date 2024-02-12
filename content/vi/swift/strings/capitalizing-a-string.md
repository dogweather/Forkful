---
title:                "Viết hoa một chuỗi"
aliases:
- vi/swift/capitalizing-a-string.md
date:                  2024-01-28T21:56:00.852741-07:00
model:                 gpt-4-0125-preview
simple_title:         "Viết hoa một chuỗi"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/swift/capitalizing-a-string.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Cái Gì & Tại Sao?
Việc viết hoa có nghĩa là thay đổi chữ cái đầu tiên của từ thành chữ in hoa; trong chuỗi ký tự, thường liên quan đến việc định dạng hoặc làm cho văn bản thân thiện với người dùng hơn. Các lập trình viên viết hoa chuỗi ký tự để tăng tính dễ đọc, tuân thủ quy tắc ngữ pháp, hoặc phù hợp với hướng dẫn về phong cách.

## Làm Thế Nào:
Swift làm cho việc viết hoa chuỗi ký tự trở nên trực tiếp. Dưới đây là một hướng dẫn nhanh:

```Swift
let lowercasedString = "hello, world!"
let titleCased = lowercasedString.capitalized // "Hello, World!"
let uppercasedString = lowercasedString.uppercased() // "HELLO, WORLD!"

// Kết Quả Mẫu:
print(titleCased)  // In ra "Hello, World!"
print(uppercasedString)  // In ra "HELLO, WORLD!"
```

Để kiểm soát nhiều hơn, chúng ta sẽ tiếp cận với `Locale`:

```Swift
let sentence = "the quick brown fox"
let titleCasedWithLocale = sentence.capitalized(with: Locale(identifier: "en_US"))
// "The Quick Brown Fox"

// Kết Quả Mẫu:
print(titleCasedWithLocale)  // In ra "The Quick Brown Fox"
```

## Sâu Hơn
Việc viết hoa trong lập trình đã tồn tại từ khi chúng ta có xử lý văn bản số hóa - nó tất cả là về việc đáp ứng kỳ vọng của người dùng. Trong khi `capitalized` trong Swift chuẩn hóa chuỗi thành Dạng Tiêu Đề, nơi ký tự đầu tiên của mỗi từ là chữ in hoa, có những sắc thái.

Trong quá khứ, các lập trình viên cần phải tự mình xử lý các phương thức tùy chỉnh để viết hoa, đối mặt với các trường hợp ngoại lệ một cách chủ quan. `capitalized` của Swift tính đến địa phương, điều này quan trọng đối với tên riêng hoặc quy tắc viết hoa cụ thể cho từng địa phương.

Nói về các lựa chọn thay thế, những người không hài lòng với `capitalized` thường chuyển sang regex hoặc viết phần mở rộng cho `String` để xử lý các quy tắc phức tạp hơn. Về mặt thực hiện, `capitalized` cơ bản là một phương thức tích hợp sẵn mà lặp qua chuỗi, áp dụng viết hoa cho chữ cái đầu tiên sau một ký tự không phải là chữ.

```Swift
extension String {
    func customCapitalized() -> String {
        return self.lowercased().replacingOccurrences(of: "\\b\\w", with: { 
            guard let firstChar = $0.first else { return $0 }
            return String(firstChar).uppercased() + $0.dropFirst()
        }, options: .regularExpression)
    }
}
```

Phần mở rộng trên sử dụng biểu thức chính quy để viết hoa chữ cái đầu tiên của mỗi từ.

## Xem Thêm
Để hiểu sâu hơn về việc thao tác chuỗi trong Swift, dưới đây là một số nguồn tài liệu hữu ích:
- [Tài liệu Swift về Chuỗi](https://developer.apple.com/documentation/swift/string)
- [Hướng Dẫn về Chuỗi trong Swift của Ray Wenderlich](https://www.raywenderlich.com/5492-working-with-strings-in-swift)
