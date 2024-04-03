---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:10:36.530463-07:00
description: "JSON (JavaScript Object Notation) l\xE0 m\u1ED9t \u0111\u1ECBnh d\u1EA1\
  ng \u0111\u1EC3 c\u1EA5u tr\xFAc d\u1EEF li\u1EC7u, \u0111\u01B0\u1EE3c s\u1EED\
  \ d\u1EE5ng cho vi\u1EC7c l\u01B0u tr\u1EEF v\xE0 truy\u1EC1n d\u1EEF li\u1EC7u.\
  \ L\u1EADp tr\xECnh vi\xEAn s\u1EED d\u1EE5ng n\xF3 v\xEC n\xF3\u2026"
lastmod: '2024-03-13T22:44:36.629468-06:00'
model: gpt-4-0125-preview
summary: "JSON (JavaScript Object Notation) l\xE0 m\u1ED9t \u0111\u1ECBnh d\u1EA1\
  ng \u0111\u1EC3 c\u1EA5u tr\xFAc d\u1EEF li\u1EC7u, \u0111\u01B0\u1EE3c s\u1EED\
  \ d\u1EE5ng cho vi\u1EC7c l\u01B0u tr\u1EEF v\xE0 truy\u1EC1n d\u1EEF li\u1EC7u."
title: "L\xE0m vi\u1EC7c v\u1EDBi JSON"
weight: 38
---

## Làm thế nào:
Để làm việc với JSON trong Kotlin, bạn có thể sử dụng thư viện `kotlinx.serialization`. Dưới đây là một ví dụ đơn giản về việc tuần tự hóa và giải tuần tự hóa một lớp dữ liệu.

```Kotlin
import kotlinx.serialization.Serializable
import kotlinx.serialization.json.Json
import kotlinx.serialization.encodeToString
import kotlinx.serialization.decodeFromString

@Serializable
data class User(val name: String, val age: Int)

fun main() {
    val json = Json { prettyPrint = true }
    val userData = User("John Doe", 30)
    
    // Tuần tự hóa thành JSON
    val jsonString = json.encodeToString(userData)
    println(jsonString)
    
    // Giải tuần tự hóa từ JSON
    val userObj = json.decodeFromString<User>(jsonString)
    println(userObj)
}
```

Đầu ra mẫu:

```
{
    "name": "John Doe",
    "age": 30
}
User(name=John Doe, age=30)
```

## Tìm hiểu sâu hơn
Cú pháp đơn giản của JSON có nguồn gốc từ JavaScript, nhưng bây giờ nó độc lập với ngôn ngữ. Các phương thức khác như XML thì dài dòng hơn. Khi làm việc với JSON trong Kotlin, thư viện `kotlinx.serialization` giải quyết phần nặng nề, tự động chuyển đổi đối tượng Kotlin thành JSON và ngược lại với các chú thích. Nó hỗ trợ các kiểu dữ liệu phức tạp và xử lý các trường hợp ngoại lệ, nhưng việc phân tích cú pháp JSON một cách thủ công cũng là một lựa chọn nếu bạn cần kiểm soát chặt chẽ hơn.

## Xem thêm
- Hướng dẫn Tuần tự hóa Kotlin: [https://kotlinlang.org/docs/serialization.html](https://kotlinlang.org/docs/serialization.html)
- Giới thiệu về JSON: [https://www.json.org/json-en.html](https://www.json.org/json-en.html)
