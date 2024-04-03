---
changelog:
- 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-08 21:56:56.515646-07:00
description: "M\u1ED9t shell t\u01B0\u01A1ng t\xE1c (REPL - V\xF2ng l\u1EB7p \u0110\
  \u1ECDc-\u0110\xE1nh gi\xE1-In) cho Dart cho ph\xE9p l\u1EADp tr\xECnh vi\xEAn \u0111\
  \xE1nh m\xE1y v\xE0 th\u1EF1c thi m\xE3 Dart t\u1EEBng d\xF2ng m\u1ED9t m\xE0 kh\xF4\
  ng c\u1EA7n ph\u1EA3i bi\xEAn\u2026"
lastmod: '2024-03-13T22:44:36.265097-06:00'
model: gpt-4-0125-preview
summary: "M\u1ED9t shell t\u01B0\u01A1ng t\xE1c (REPL - V\xF2ng l\u1EB7p \u0110\u1ECD\
  c-\u0110\xE1nh gi\xE1-In) cho Dart cho ph\xE9p l\u1EADp tr\xECnh vi\xEAn \u0111\xE1\
  nh m\xE1y v\xE0 th\u1EF1c thi m\xE3 Dart t\u1EEBng d\xF2ng m\u1ED9t m\xE0 kh\xF4\
  ng c\u1EA7n ph\u1EA3i bi\xEAn d\u1ECBch to\xE0n b\u1ED9 k\u1ECBch b\u1EA3n."
title: "S\u1EED d\u1EE5ng giao di\u1EC7n d\xF2ng l\u1EC7nh t\u01B0\u01A1ng t\xE1c\
  \ (REPL)"
weight: 34
---

## Làm thế nào:
Dart không đi kèm với REPL được tích hợp sẵn. Tuy nhiên, bạn có thể đạt được chức năng tương tự REPL bằng cách sử dụng DartPad (trực tuyến) hoặc bằng cách sử dụng các công cụ bên thứ ba như `dart_repl`.

**Sử dụng DartPad:**

DartPad (https://dartpad.dev) là một trình biên soạn Dart trực tuyến cho phép bạn viết và chạy mã Dart trong trình duyệt web của mình. Mặc dù không phải là một REPL dòng lệnh truyền thống, nhưng nó cung cấp một trải nghiệm tương tự cho việc thử nghiệm nhanh chóng.

Chỉ cần truy cập vào trang web, nhập mã Dart của bạn vào khung bên trái và nhấn "Run" để xem kết quả hiển thị bên phải.

Ví dụ:
```dart
void main() {
  print('Xin chào, Dart!');
}
```
Kết quả:
```
Xin chào, Dart!
```

**Sử dụng `dart_repl` (công cụ bên thứ ba):**

Đầu tiên, cài đặt `dart_repl` thông qua pub một cách toàn cầu:

```shell
dart pub global activate dart_repl
```

Sau đó, chạy `dart_repl` từ terminal của bạn:

```shell
dart_repl
```

Bây giờ, bạn có thể bắt đầu nhập các câu lệnh Dart trực tiếp vào shell. Ví dụ:

```dart
>>> print('Xin chào, REPL!');
Xin chào, REPL!
>>> int add(int x, int y) => x + y;
>>> print(add(5, 7));
12
```

Những phương pháp này cung cấp một con đường nhanh chóng để thử nghiệm mã Dart ngay lập tức, giúp giảm đáng kể độ dốc của quá trình học và tăng cường năng suất.
