---
changelog:
- 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-08 21:56:23.836019-07:00
description: "L\xE0m tr\xF2n s\u1ED1 l\xE0 qu\xE1 tr\xECnh \u0111i\u1EC1u ch\u1EC9\
  nh m\u1ED9t s\u1ED1 \u0111\u1EC3 g\u1EA7n nh\u1EA5t v\u1EDBi s\u1ED1 nguy\xEAn ho\u1EB7\
  c \u0111\u1EBFn m\u1ED9t s\u1ED1 l\u01B0\u1EE3ng ch\u1EEF s\u1ED1 th\u1EADp ph\xE2\
  n \u0111\u01B0\u1EE3c ch\u1EC9 \u0111\u1ECBnh. L\u1EADp tr\xECnh vi\xEAn th\u01B0\
  \u1EDDng l\xE0m tr\xF2n\u2026"
lastmod: '2024-03-13T22:44:36.255987-06:00'
model: gpt-4-0125-preview
summary: "L\xE0m tr\xF2n s\u1ED1 l\xE0 qu\xE1 tr\xECnh \u0111i\u1EC1u ch\u1EC9nh m\u1ED9\
  t s\u1ED1 \u0111\u1EC3 g\u1EA7n nh\u1EA5t v\u1EDBi s\u1ED1 nguy\xEAn ho\u1EB7c \u0111\
  \u1EBFn m\u1ED9t s\u1ED1 l\u01B0\u1EE3ng ch\u1EEF s\u1ED1 th\u1EADp ph\xE2n \u0111\
  \u01B0\u1EE3c ch\u1EC9 \u0111\u1ECBnh."
title: "L\xE0m tr\xF2n s\u1ED1"
weight: 13
---

## Cách thực hiện:
Dart cung cấp các phương thức bản địa trong kiểu `num` của nó cho các thao tác làm tròn. Tại đây, chúng ta sẽ khám phá các phương thức như `round()`, `floor()`, `ceil()`, và cách làm tròn đến một số lượng chữ số thập phân nhất định.

### Làm tròn đến số nguyên gần nhất:
```dart
var number = 3.56;
print(number.round()); // Đầu ra: 4
```

### Làm tròn xuống:
```dart
print(number.floor()); // Đầu ra: 3
```

### Làm tròn lên:
```dart
print(number.ceil()); // Đầu ra: 4
```

### Làm tròn đến một số lượng chữ số thập phân nhất định:
Để làm tròn đến một số lượng chữ số thập phân nhất định, chúng ta có thể sử dụng phương thức `toStringAsFixed()`, phương thức này trả về một chuỗi, hoặc sử dụng sự kết hợp của `pow` từ `dart:math` để có kết quả số.

```dart
import 'dart:math';

var number = 3.56789;
String roundedString = number.toStringAsFixed(2); // Dành cho mục đích hiển thị
print(roundedString); // Đầu ra: 3.57

double roundedNumber = double.parse(roundedString);
print(roundedNumber); // Đầu ra: 3.57

// Hoặc, cho một kết quả số:
double roundedToDecimal = (number * pow(10, 2)).round().toDouble() / pow(10, 2);
print(roundedToDecimal); // Đầu ra: 3.57
```

Mặc dù thư viện cốt lõi của Dart đáp ứng hầu hết các nhu cầu làm tròn một cách hiệu quả, đối với những thao tác toán học phức tạp hơn hoặc các yêu cầu làm tròn chính xác, các thư viện như `decimal` có thể hữu ích. Thư viện `decimal` cung cấp một cách dễ dàng để làm việc với số thập phân mà không mất độ chính xác, điều này đặc biệt hữu ích cho các tính toán tài chính, nhưng đối với các phương pháp làm tròn đơn giản như đã cho thấy, chức năng cốt lõi của Dart thường là đủ.
