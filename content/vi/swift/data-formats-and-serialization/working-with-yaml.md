---
aliases:
- /vi/swift/working-with-yaml/
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:12:43.606792-07:00
description: "YAML, vi\u1EBFt t\u1EAFt c\u1EE7a \"YAML Ain't Markup Language\", l\xE0\
  \ m\u1ED9t chu\u1EA9n m\xE3 h\xF3a d\u1EEF li\u1EC7u d\u1EC5 \u0111\u1ECDc cho con\
  \ ng\u01B0\u1EDDi, ch\xFAng ta c\xF3 th\u1EC3 s\u1EED d\u1EE5ng \u0111\u1EC3 c\u1EA5\
  u h\xECnh t\u1EC7p ho\u1EB7c trao \u0111\u1ED5i\u2026"
lastmod: 2024-02-18 23:08:51.112368
model: gpt-4-0125-preview
summary: "YAML, vi\u1EBFt t\u1EAFt c\u1EE7a \"YAML Ain't Markup Language\", l\xE0\
  \ m\u1ED9t chu\u1EA9n m\xE3 h\xF3a d\u1EEF li\u1EC7u d\u1EC5 \u0111\u1ECDc cho con\
  \ ng\u01B0\u1EDDi, ch\xFAng ta c\xF3 th\u1EC3 s\u1EED d\u1EE5ng \u0111\u1EC3 c\u1EA5\
  u h\xECnh t\u1EC7p ho\u1EB7c trao \u0111\u1ED5i\u2026"
title: "L\xE0m vi\u1EC7c v\u1EDBi YAML"
---

{{< edit_this_page >}}

## Lý do & Tại sao?
YAML, viết tắt của "YAML Ain't Markup Language", là một chuẩn mã hóa dữ liệu dễ đọc cho con người, chúng ta có thể sử dụng để cấu hình tệp hoặc trao đổi dữ liệu. Các lập trình viên yêu thích YAML vì sự đơn giản và dễ đọc của nó, đặc biệt trong các cài đặt cấu hình, kịch bản CI/CD và hệ thống điều phối container.

## Cách thực hiện:
Swift không có khả năng xử lý YAML một cách tự nhiên, vì vậy chúng ta cần sử dụng một thư viện bên thứ ba như Yams. Đầu tiên, thêm Yams vào `Package.swift` của bạn:

```swift
dependencies: [
    .package(url: "https://github.com/jpsim/Yams.git", from: "4.0.0")
]
```

Sau đó, nhập Yams và sử dụng nó để phân tích YAML thành một dictionary Swift:

```swift
import Yams

let yamlString = """
name: John Doe
age: 34
languages:
  - Swift
  - Python
"""

do {
    if let data = try Yams.load(yaml: yamlString) as? [String: Any] {
        print(data)
    }
} catch {
    print("Không thể phân tích chuỗi YAML.")
}

// Đầu ra:
// ["name": "John Doe", "age": 34, "languages": ["Swift", "Python"]]
```

Nếu bạn muốn sinh ra YAML từ đối tượng Swift:

```swift
import Yams

let dictionary: [String: Any] = [
    "name": "Jane Smith",
    "age": 28,
    "languages": ["Java", "Kotlin"]
]

do {
    let yaml = try Yams.dump(object: dictionary)
    print(yaml)
} catch {
    print("Không thể chuyển dictionary thành YAML.")
}

// Đầu ra:
// age: 28
// languages:
//   - Java
//   - Kotlin
// name: Jane Smith
```

## Sâu hơn
YAML xuất phát từ năm 2001 như một lựa chọn thân thiện với con người thay thế cho XML. Nó giống với JSON nhưng sử dụng ít ngoặc và dễ đọc hơn cho con người. Trong khi JSON là lựa chọn hàng đầu cho các API web, YAML được ưa chuộng cho các tệp cấu hình. Các lựa chọn thay thế bao gồm TOML và JSON5, nhưng việc sử dụng khoảng trắng của YAML và khả năng bình luận các dòng khiến nó trở nên đáng mong muốn. Với Yams, Swift tiếp cận việc xử lý YAML với việc ánh xạ lớp, cung cấp sự cân bằng giữa sự đơn giản giống như kịch bản và an toàn kiểu.

## Xem thêm
- Trang chính thức của YAML để biết chi tiết về spec: [https://yaml.org](https://yaml.org)
- Kho lưu trữ GitHub của Yams: [https://github.com/jpsim/Yams](https://github.com/jpsim/Yams)
- Tài liệu về Quản lý Gói Swift: [https://swift.org/package-manager/](https://swift.org/package-manager/)
