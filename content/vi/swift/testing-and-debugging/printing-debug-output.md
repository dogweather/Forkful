---
title:                "In ra thông tin gỡ lỗi"
aliases:
- vi/swift/printing-debug-output.md
date:                  2024-01-28T22:04:50.703974-07:00
model:                 gpt-4-0125-preview
simple_title:         "In ra thông tin gỡ lỗi"

tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/swift/printing-debug-output.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Cái gì & Tại sao?

Trong Swift, việc in đầu ra để gỡ lỗi nghĩa là hiển thị dữ liệu trong khu vực gỡ lỗi, thường là trong một IDE hoặc bảng điều khiển, để theo dõi những gì đang xảy ra trực tiếp trong mã của bạn. Đó là động thái chính để nhanh chóng chẩn đoán vấn đề hoặc hiểu luồng mã—hãy coi đó như một cái nhìn lén vào bộ não của mã bạn.

## Làm thế nào:

Trong Swift, bạn có một người bạn trong hàm `print()`. Dễ sử dụng, nó cho bạn cái nhìn về những gì đang diễn ra trong mã của bạn.

```Swift
var greeting = "Hello, playground"
print(greeting)
// Đầu ra: Hello, playground

let numbers = [1, 2, 3, 4, 5]
for number in numbers {
    print(number)
}
// Đầu ra:
// 1
// 2
// 3
// 4
// 5
```

Nhưng chờ đã, còn nhiều hơn nữa! Cần thông tin gỡ lỗi chi tiết? `debugPrint()` sẽ giúp bạn:

```Swift
debugPrint(greeting)
// Đầu ra: "Hello, playground"
```

Thấy những dấu ngoặc kép không? `debugPrint()` cung cấp thông tin thêm về các loại dữ liệu và cấu trúc.

## Sâu hơn

Trong những ngày đầu của Objective-C, chúng tôi sử dụng `NSLog` để ghi nhật ký. Swift giữ mọi thứ đơn giản—`print()` là bánh mì và bơ của bạn cho đầu ra tiêu chuẩn, trong khi `debugPrint()` là bơ có hương vị cho các cái nhìn chi tiết.

Thông tin thú vị: Đầu ra tiêu chuẩn trong Swift không chỉ là văn bản—nó có thể là bất kỳ loại nào tuân theo `CustomStringConvertible` hoặc `CustomDebugStringConvertible`. Những giao thức này cho phép bạn tùy chỉnh cách các đối tượng của mình trông như thế nào khi chúng kể câu chuyện qua việc in.

Bên trong, `print()` và `debugPrint()` sử dụng `String(describing:)` và `String(reflecting:)` để biến đối tượng của bạn thành chuỗi. Cơ bản, những hàm này sử dụng một chiếc gương để chụp selfie dữ liệu của bạn.

Có phương án khác không? Bạn có `os_log` và `NSLog`, nhưng những cái này phù hợp hơn cho việc ghi nhật ký ở cấp độ sản xuất, không phải quá trình gỡ lỗi nhanh gọn mà chúng ta đang đề cập ở đây.

## Xem thêm

- Tài liệu tham khảo API của Swift về các hàm in: [Thư viện tiêu chuẩn Swift: print(_:separator:terminator:)](https://developer.apple.com/documentation/swift/1541053-print)
- Cái nhìn sâu hơn về việc ghi nhật ký trong Swift, GDPR và các xem xét về quyền riêng tư: [Unified Logging and Activity Tracing](https://developer.apple.com/documentation/os/logging)
- Sự nội suy chuỗi và khả năng tùy chỉnh cho các mô tả gỡ lỗi của Swift: [CustomStringConvertible](https://developer.apple.com/documentation/swift/customstringconvertible) và [CustomDebugStringConvertible](https://developer.apple.com/documentation/swift/customdebugstringconvertible)
