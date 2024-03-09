---
title:                "Chuyển đổi chuỗi thành chữ thường"
date:                  2024-03-08T21:54:21.040452-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Gì và Tại sao?

Chuyển đổi một chuỗi về dạng chữ thường là một thao tác cơ bản bao gồm việc biến đổi tất cả các kí tự trong một chuỗi đã cho thành các tương đương chữ thường của chúng. Các lập trình viên thường thực hiện thao tác này để đạt được so sánh không phân biệt chữ hoa chữ thường hoặc để chuẩn hóa đầu vào văn bản cho xử lý tiếp theo, làm cho ứng dụng thêm thân thiện với người dùng và dữ liệu trở nên nhất quán hơn.

## Làm thế nào:

Trong Dart, bạn có thể chuyển đổi một chuỗi sang dạng chữ thường bằng cách sử dụng phương thức `toLowerCase()` được cung cấp bởi lớp `String`. Phương thức này trả về một chuỗi mới với tất cả các kí tự in hoa được chuyển đổi thành chữ thường. Hãy xem cách thức này hoạt động như thế nào qua một ví dụ đơn giản:

```dart
void main() {
  String chuoiGoc = "Hello, World!";
  String chuoiChuThuong = chuoiGoc.toLowerCase();

  print(chuoiChuThuong);  // Đầu ra: hello, world!
}
```

Dart không yêu cầu thư viện bên ngoài cho các nhiệm vụ xử lý chuỗi cơ bản, bao gồm cả chuyển đổi sang chữ thường, vì lớp `String` của thư viện tiêu chuẩn khá toàn diện. Tuy nhiên, đối với các thao tác phức tạp hơn liên quan đến các quy tắc cụ thể của địa phương, bạn có thể xem xét gói `intl`, cung cấp các tiện ích quốc tế hóa và địa phương hóa, bao gồm chuyển đổi chữ hoa chữ thường dựa trên địa điểm:

Để sử dụng `intl`, thêm nó vào file `pubspec.yaml` của bạn:

```yaml
dependencies:
  intl: ^0.17.0
```

Sau đó, bạn có thể sử dụng phương thức `toLocaleLowerCase()` để chuyển đổi một chuỗi sang dạng chữ thường dựa trên các địa điểm cụ thể:

```dart
import 'package:intl/intl.dart';

void main() {
  String chuoiGoc = "İstanbul";
  
  // Địa điểm tiếng Thổ Nhĩ Kỳ
  print(Intl.withLocale('tr', () => chuoiGoc.toLowerCase())); // Đầu ra: istanbul
  
  // Địa điểm mặc định (en)
  print(chuoiGoc.toLowerCase()); // Đầu ra: i̇stanbul
}
```

Trong ví dụ này, chú ý cách địa điểm tiếng Thổ Nhĩ Kỳ xử lý đúng cách chữ 'i' không dấu, cho thấy tầm quan trọng của các biến đổi nhận thức về địa phương trong các ứng dụng quốc tế hóa.
