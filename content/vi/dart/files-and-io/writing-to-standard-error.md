---
title:                "Ghi vào lỗi chuẩn"
date:                  2024-03-08T21:58:27.720708-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Gì và Tại sao?

Viết vào lỗi chuẩn (stderr) trong Dart là về việc gửi thông điệp lỗi và chẩn đoán đến một luồng riêng biệt, khác biệt so với đầu ra chuẩn (stdout). Các lập trình viên làm điều này để phân biệt giữa đầu ra chương trình bình thường và các lỗi hoặc cảnh báo thông điệp, cho phép dễ dàng gỡ lỗi và ghi nhật ký hơn.

## Làm thế nào:

Trong Dart, viết vào stderr rất đơn giản sử dụng đối tượng `stderr` có sẵn trong `dart:io`. Dưới đây là một ví dụ cơ bản:

```dart
import 'dart:io';

void main() {
  stderr.writeln('Đây là một thông điệp lỗi.');
}
```

Đầu ra khi chạy:
```
Đây là một thông điệp lỗi.
```
Thông điệp này được gửi đến luồng stderr, thường được hiển thị trong console hoặc terminal.

Để chứng minh sự phức tạp hơn, như việc ghi nhật ký một ngoại lệ, bộ tính năng phong phú của Dart cho phép xử lý lỗi một cách ngắn gọn và hiệu quả:

```dart
import 'dart:io';

void riskyOperation() {
  try {
    // Giả lập một hoạt động có thể gây ra lỗi
    throw Exception('Có điều gì đó không ổn!');
  } catch (e) {
    stderr.writeln('Lỗi: $e');
  }
}

void main() {
  riskyOperation();
}
```

Đầu ra khi chạy:
```
Lỗi: Exception: Có điều gì đó không ổn!
```

Mẫu này đặc biệt hữu ích cho các ứng dụng cần phân biệt nhật ký bình thường khỏi nhật ký lỗi, làm cho việc giám sát và gỡ lỗi ứng dụng dễ dàng hơn.

Mặc dù thư viện chuẩn của Dart khá toàn diện, nhiều chương trình không yêu cầu thư viện bên thứ ba cho việc viết vào stderr. Tuy nhiên, nếu ứng dụng của bạn cần khả năng ghi nhật ký tinh vi hơn (ví dụ, vào tệp, qua mạng, định dạng), gói `logging` là một lựa chọn phổ biến. Dưới đây là cái nhìn nhanh vào việc sử dụng `logging` cho lỗi:

```dart
import 'dart:io';
import 'package:logging/logging.dart';

final logger = Logger('MyAppLogger');

void setupLogging() {
  logger.onRecord.listen((record) {
    if (record.level >= Level.SEVERE) {
      stderr.writeln('${record.level.name}: ${record.time}: ${record.message}');
    }
  });
}

void main() {
  setupLogging();
  logger.severe('Lỗi Nghiêm Trọng: Đã xảy ra điều cực kỳ tồi tệ.');
}
```

Đầu ra khi chạy:
```
SEVERE: 2023-04-01 00:00:00.000: Lỗi Nghiêm Trọng: Đã xảy ra điều cực kỳ tồi tệ.
```

Phương pháp này cung cấp một mức độ tùy chỉnh và kiểm soát cao hơn về những gì được ghi như một lỗi và cách nó được định dạng, có thể rất hữu ích trong các ứng dụng lớn, phức tạp hơn.
