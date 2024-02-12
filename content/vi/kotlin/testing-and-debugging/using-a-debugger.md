---
title:                "Sử dụng bộ gỡ lỗi"
aliases:
- vi/kotlin/using-a-debugger.md
date:                  2024-01-28T22:09:13.471868-07:00
model:                 gpt-4-0125-preview
simple_title:         "Sử dụng bộ gỡ lỗi"

tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/kotlin/using-a-debugger.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Cái gì & Tại sao?
Việc lặn sâu vào debugger là để bước qua từng dòng code, quan sát cách thức hoạt động và bắt gặp những lỗi khó chịu đang quậy phá. Lập trình viên sử dụng debugger bởi vì đó là công cụ thám tử giúp chúng ta tìm ra vấn đề ở đâu mà không cần phải tức tóc.

## Cách thực hiện:
Dưới đây là một vài ví dụ về việc debug trong Kotlin với IntelliJ IDEA - Sherlock Holmes của các IDE:

```kotlin
fun main() {
    val mysteryNumber = 42
    var guess = 0

    while (guess != mysteryNumber) {
        println("Đoán số: ")
        guess = readLine()?.toIntOrNull() ?: continue // Bỏ qua nhập liệu xấu

        // Đặt một breakpoint ở đây để theo dõi 'guess' trong quá trình hoạt động
        if (guess < mysteryNumber) {
            println("Quá thấp!")
        } else if (guess > mysteryNumber) {
            println("Quá cao!")
        }
    }

    println("Bạn đã đoán đúng! Số bí ẩn là $mysteryNumber")
}
```

Kết quả từ Debugger:
```
Đoán số: 
10
Quá thấp!
Đoán số: 
50
Quá cao!
Đoán số: 
42
Bạn đã đoán đúng! Số bí ẩn là 42
```

## Sâu hơn nữa
Debugger đã có mặt trong ngành từ những năm '50. Lúc bấy giờ, chúng khá là sơ khai, và việc debug có thể liên quan nhiều đến phần cứng hơn là phần mềm. Ngày nay, một debugger như cái trong IntelliJ IDEA cho phép chúng ta đặt breakpoint, bước qua từng dòng code một cách chi tiết, và kiểm tra trạng thái của các biến một cách thoải mái.

Mặc dù debugger của IntelliJ rất tiện lợi cho Kotlin, nó không phải là cái duy nhất. Có một loạt các phương án khác như Logcat cho phát triển Android, hoặc các công cụ dòng lệnh như jdb cho những người thích giản dị. Phép thuật đằng sau hậu trường ở đây chủ yếu liên quan đến JVM Tool Interface (JVMTI), điều này cho phép debugger tương tác với Máy Ảo Java, giữ cho các nhà phát triển Kotlin được thông suốt.

## Xem thêm
- Tài liệu Debugger của IntelliJ IDEA: [https://jetbrains.com/idea/](https://www.jetbrains.com/idea/features/debugger.html)
