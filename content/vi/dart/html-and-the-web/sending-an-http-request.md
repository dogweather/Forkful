---
title:                "Gửi một yêu cầu HTTP"
date:                  2024-03-08T21:56:24.367492-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Gì & Tại Sao?

Việc gửi một yêu cầu HTTP trong Dart là quy trình khởi tạo giao tiếp với máy chủ web hoặc API từ một ứng dụng Dart. Lập trình viên thực hiện điều này để lấy dữ liệu từ web, gửi biểu mẫu, và tương tác với các dịch vụ RESTful, khiến nó trở thành một thao tác cơ bản cho phát triển ứng dụng web, phía máy chủ, và ứng dụng di động trong Dart.

## Cách thực hiện:

Dart bao gồm gói `http`, một cách mạnh mẽ và thuận tiện để làm việc với các tài nguyên HTTP. Đầu tiên, bao gồm nó trong tệp pubspec.yaml của bạn:

```yaml
dependencies:
  http: ^0.13.3
```

Sau đó, nhập nó vào code Dart của bạn để bắt đầu thực hiện các yêu cầu:

```dart
import 'package:http/http.dart' as http;

void main() async {
  var url = Uri.parse('https://jsonplaceholder.typicode.com/todos/1');
  var phản_hồi = await http.get(url);

  if (phản_hồi.statusCode == 200) {
    print('Nội dung phản hồi: ${phản_hồi.body}');
  } else {
    print('Yêu cầu thất bại với trạng thái: ${phản_hồi.statusCode}.');
  }
}
```

Mẫu đầu ra cho một yêu cầu thành công có thể trông như thế này:

```
Nội dung phản hồi: {
  "userId": 1,
  "id": 1,
  "title": "delectus aut autem",
  "completed": false
}
```

Đối với các yêu cầu phức tạp hơn, như yêu cầu POST với một nội dung JSON, bạn sẽ thực hiện như sau:

```dart
import 'dart:convert';
import 'package:http/http.dart' as http;

void main() async {
  var url = Uri.parse('https://jsonplaceholder.typicode.com/posts');
  var phản_hồi = await http.post(
    url,
    headers: {"Content-Type": "application/json"},
    body: jsonEncode({
      "title": 'foo',
      "body": 'bar',
      "userId": 1,
    }),
  );

  if (phản_hồi.statusCode == 201) {
    print('Trạng thái phản hồi: ${phản_hồi.statusCode}');
    print('Nội dung phản hồi: ${phản_hồi.body}');
  } else {
    print('Thất bại khi tạo một bài đăng mới. Trạng thái: ${phản_hồi.statusCode}');
  }
}
```

Mẫu đầu ra cho yêu cầu post có thể là:

```
Trạng thái phản hồi: 201
Nội dung phản hồi: {
  "title": "foo",
  "body": "bar",
  "userId": 1,
  "id": 101
}
```

Những ví dụ này trình bày các yêu cầu HTTP GET và POST cơ bản sử dụng gói `http` trong Dart. Gói này đáp ứng hầu hết các nhu cầu về gửi yêu cầu HTTP, bao gồm cả những tình huống phức tạp hơn với headers và nội dung body.
