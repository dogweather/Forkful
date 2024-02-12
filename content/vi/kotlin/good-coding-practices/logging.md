---
title:                "Ghi log"
aliases:
- /vi/kotlin/logging/
date:                  2024-01-28T22:04:10.689371-07:00
model:                 gpt-4-0125-preview
simple_title:         "Ghi log"

tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/vi/kotlin/logging.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Cái Gì & Tại Sao?

Logging, về bản chất, là việc ghi lại các sự kiện và dữ liệu từ một ứng dụng phần mềm vào một đầu ra ngoại vi, như một tệp hoặc console. Các lập trình viên thực hiện logging để truy vết qua mã, khắc phục sự cố, và theo dõi hành vi của ứng dụng ngoài môi trường thực, cung cấp những hiểu biết quan trọng không thể thu được một cách hiệu quả bằng bất kỳ cách nào khác.

## Làm Thế Nào:

Trong Kotlin, việc logging có thể được thực hiện bằng cách sử dụng hàm `println()` được tích hợp sẵn cho các trường hợp đơn giản, hoặc với các thư viện phức tạp hơn như SLF4J kèm theo Logback hoặc Log4j cho những nhu cầu nâng cao.

Dưới đây là một ví dụ cơ bản sử dụng `println()`:

```Kotlin
fun main() {
    println("Thông điệp log đơn giản: Ứng dụng đã được khởi động.")
    // ... một số logic ứng dụng ở đây ...
    try {
        // Mô phỏng một lỗi
        throw Exception("Lỗi được mô phỏng")
    } catch (e: Exception) {
        println("Thông điệp log lỗi: " + e.message)
    }
}
```

Kết quả:
```
Thông điệp log đơn giản: Ứng dụng đã được khởi động.
Thông điệp log lỗi: Lỗi được mô phỏng
```

Và đây là một đoạn mã mẫu sử dụng SLF4J với Logback được cấu hình:

```Kotlin
import org.slf4j.LoggerFactory

private val logger = LoggerFactory.getLogger("MyAppLogger")

fun main() {
    logger.info("Thông điệp log có cấu trúc: Ứng dụng được khởi chạy.")
    // ... một số logic ứng dụng ở đây ...
    try {
        // Mô phỏng một lỗi
        throw Exception("Lỗi được mô phỏng")
    } catch (e: Exception) {
        logger.error("Log lỗi có cấu trúc: ", e)
    }
}
```

Giả sử việc cấu hình Logback phù hợp, kết quả sẽ được định dạng và có thể trông giống như sau khi được ghi vào tệp log:
```
[INFO] - 2023-03-29 14:15:42 - MyAppLogger - Thông điệp log có cấu trúc: Ứng dụng được khởi chạy.
[ERROR] - 2023-03-29 14:15:43 - MyAppLogger - Log lỗi có cấu trúc: 
java.lang.Exception: Lỗi được mô phỏng
   at com.myapp.Main.main(Main.kt:10)
```

## Sâu Hơn

Lịch sử, việc logging trong phần mềm phát triển cùng với sự phức tạp ngày càng tăng của các ứng dụng và hệ thống. Các câu lệnh in đơn giản đã đủ cho những ngày đầu, khi các chương trình thường được chạy và gỡ lỗi bởi chính những nhà phát triển. Nhưng khi các hệ thống được kết nối mạng và chạy trong các môi trường khác nhau trên các người dùng khác nhau, một hệ thống logging vững chắc và lâu dài trở nên quan trọng.

Trước khi Kotlin trở nên phổ biến, các nhà phát triển Java đã rộng rãi áp dụng các thư viện như Log4j và sau đó là SLF4J. Những thư viện này đã truyền cảm hứng cho những phương pháp tương tự trong Kotlin, tận dụng khả năng tương thích của Kotlin với các thư viện Java. SLF4J hoạt động như một lớp trừu tượng, cho phép việc triển khai logging thực tế có thể được thay thế—thường Logback hoặc Log4j2 là những lựa chọn được ưu tiên.

Kotlin cũng cho phép giải pháp logging đa nền tảng hoạt động trên JVM, JavaScript, và Native, ví dụ, thông qua cơ chế `expect`/`actual`, che giấu đi những triển khai cụ thể theo nền tảng.

So với các thư viện logging chuyên dụng, println vẫn là hình thức logging đơn giản nhất bởi vì nó không yêu cầu cài đặt bổ sung hoặc phụ thuộc; tuy nhiên, nó thường không phù hợp cho các ứng dụng sản xuất do thiếu các tính năng như mức độ log, quay vòng log, và định dạng có cấu trúc.

Các tính năng phổ biến khác của các khung logging nâng cao bao gồm:

- Các mức log (DEBUG, INFO, WARN, ERROR, v.v.) để phân loại mức độ cấp bách của thông điệp log.
- Xuất ra các nguồn khác nhau, như console, tệp, cơ sở dữ liệu, hoặc dịch vụ mạng.
- Tự động quay vòng và chính sách giữ log.
- Hỗ trợ tracing phân tán cho kiến trúc microservices.
- Logging có cấu trúc sử dụng các định dạng như JSON, tích hợp tốt với các hệ thống phân tích log.

Công cụ và các tính năng này rất quan trọng cho việc duy trì một hệ thống đáng tin cậy, có thể quan sát đặc biệt trong môi trường phức tạp, phân tán, hoặc có quy mô lớn.

## Xem Thêm

Để tìm hiểu thêm và có cái nhìn sâu sắc hơn về logging trong Kotlin, hãy kiểm tra:

- SLF4J (Simple Logging Facade for Java) [http://www.slf4j.org/](http://www.slf4j.org/)
- Logback, người kế nhiệm của Log4j [http://logback.qos.ch/](http://logback.qos.ch/)
- Log4j 2 [https://logging.apache.org/log4j/2.x/](https://logging.apache.org/log4j/2.x/)
- Tài liệu đa nền tảng Kotlin về các khai báo 'expect' và 'actual': [https://kotlinlang.org/docs/multiplatform.html](https://kotlinlang.org/docs/multiplatform.html)
- Hướng dẫn về logging có cấu trúc trong Kotlin: [https://ktor.io/docs/logging.html](https://ktor.io/docs/logging.html)
