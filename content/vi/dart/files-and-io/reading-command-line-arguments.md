---
title:                "Đọc các tham số dòng lệnh"
date:                  2024-03-08T21:56:07.969026-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Điều gì & Tại sao?

Việc đọc các đối số dòng lệnh trong Dart cho phép lập trình viên nhập dữ liệu trực tiếp vào console khi thực thi một chương trình Dart, nâng cao tính tương tác và linh hoạt cho nhiều trường hợp sử dụng, bao gồm các kịch bản tự động hóa, công cụ CLI, hoặc xử lý loạt. Tính năng này là trọng tâm để tạo ra các ứng dụng dòng lệnh thân thiện và linh hoạt với người dùng.

## Làm thế nào:

Dart cung cấp một cách tiếp cận đơn giản để truy cập vào các đối số dòng lệnh thông qua `List<String> args` trong phương thức main. Dưới đây là một ví dụ đơn giản minh họa cách đọc và sử dụng các đối số dòng lệnh.

```dart
// main.dart
void main(List<String> args) {
  print('Đối Số Dòng Lệnh:');
  for (var i = 0; i < args.length; i++) {
    print('${i + 1}: ${args[i]}');
  }
}
```

Để chạy chương trình Dart này và truyền các đối số dòng lệnh, sử dụng Dart CLI như sau:

```shell
dart run main.dart Hello World!
```

Kết quả mong đợi:

```
Đối Số Dòng Lệnh:
1: Hello
2: World!
```

### Sử dụng Một Thư Viện Bên Thứ Ba Phổ Biến: `args`

Mặc dù các khả năng tích hợp sẵn của Dart trong việc xử lý các đối số dòng lệnh là đủ mạnh mẽ cho nhiều ứng dụng, gói `args` cung cấp một cách tinh tế hơn để định nghĩa và phân tích các đối số dòng lệnh cho những nhu cầu phức tạp hơn.

Đầu tiên, thêm gói `args` vào `pubspec.yaml` của bạn:

```yaml
dependencies:
  args: ^2.0.0
```

Sau đó, sử dụng nó trong chương trình của bạn như sau:

```dart
// Sử dụng gói 'args'
import 'package:args/args.dart';

void main(List<String> arguments) {
  final parser = ArgParser()..addOption('name', abbr: 'n');
  final argResults = parser.parse(arguments);

  if (argResults.wasParsed('name')) {
    print('Xin chào, ${argResults['name']}!');
  } else {
    print('Không có tên được cung cấp.');
  }
}
```

Chạy chương trình với một đối số được đặt tên:

```shell
dart run main.dart --name=John
```

Kết quả mong đợi:

```
Xin chào, John!
```

Giới thiệu đơn giản này về cách phân tích các đối số dòng lệnh, cả natively và với thư viện `args`, thể hiện cách Dart có thể xử lý đầu vào từ người dùng ngay từ console, mở ra một con đường tạo ra các ứng dụng CLI tương tác và động hơn.
