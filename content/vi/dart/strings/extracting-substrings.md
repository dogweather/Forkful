---
title:                "Trích xuất chuỗi con"
date:                  2024-03-08T21:54:56.066135-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Cái gì & Tại sao?
Rút trích các chuỗi con là việc truy xuất các phần cụ thể của một chuỗi dựa trên vị trí hoặc các mẫu. Lập trình viên thực hiện điều này cho các nhiệm vụ như phân tích đầu vào của người dùng, thao tác dữ liệu, hoặc rút trích thông tin liên quan từ các nguồn văn bản lớn hơn.

## Làm thế nào:
Trong Dart, bạn có thể sử dụng nhiều phương pháp khác nhau để rút trích các chuỗi con, như `substring()`, `split()`, và biểu thức chính quy. Mỗi phương pháp phục vụ các mục đích khác nhau và cung cấp sự linh hoạt trong việc xử lý chuỗi.

### Sử dụng `substring()`:
Phương pháp `substring()` là đơn giản. Bạn chỉ định chỉ mục bắt đầu (và tùy chọn, chỉ mục kết thúc) để cắt chuỗi.

```dart
void main() {
  String example = "Hello, World!";
  String result = example.substring(7, 12);
  print(result); // Đầu ra: World
}
```

### Sử dụng `split()`:
Chia một chuỗi thành một danh sách các chuỗi con dựa trên một mẫu (như một khoảng trắng hoặc dấu phẩy), và sau đó truy cập chuỗi con bằng chỉ mục.

```dart
void main() {
  String example = "Dart is fun";
  List<String> parts = example.split(' ');
  String result = parts[1]; // Truy cập bằng chỉ mục
  print(result); // Đầu ra: is
}
```

### Sử dụng Biểu thức Chính Quy:
Cho các mẫu phức tạp, lớp `RegExp` trong Dart rất mạnh mẽ. Sử dụng nó để khớp các mẫu và rút trích các chuỗi con.

```dart
void main() {
  String example = "Email: example@mail.com";
  RegExp regExp = RegExp(r"\b\w+@\w+\.\w+\b");
  String email = regExp.stringMatch(example)!;
  print(email); // Đầu ra: example@mail.com
}
```

### Thư Viện Bên Thứ Ba:
Mặc dù thư viện chuẩn của Dart khá đủ sức mạnh, nhưng bạn có thể gặp phải các tình huống mà một thư viện bên thứ ba có thể đơn giản hóa công việc của bạn. Một lựa chọn phổ biến cho việc thao tác chuỗi và khớp mẫu không được cụ thể khuyến nghị ở đây vì khả năng tự có của Dart thường đã đủ. Tuy nhiên, luôn kiểm tra [pub.dev](https://pub.dev) để tìm bất kỳ thư viện nào có thể phù hợp hơn với nhu cầu cụ thể của bạn.
