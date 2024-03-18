---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:29:29.247044-06:00
description: "JSON (JavaScript Object Notation) \u098F\u09B0 \u09B8\u09BE\u09A5\u09C7\
  \ \u0995\u09BE\u099C \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\u09C7 \u09B8\u09CD\u099F\
  \u09CD\u09B0\u09BF\u0982 \u09A5\u09C7\u0995\u09C7 JSON \u09A1\u09C7\u099F\u09BE\
  \ \u09AA\u09BE\u09B0\u09CD\u09B8 \u0995\u09B0\u09C7 Dart \u0985\u09AC\u099C\u09C7\
  \u0995\u09CD\u099F\u09C7 \u09B0\u09C2\u09AA\u09BE\u09A8\u09CD\u09A4\u09B0 \u0995\
  \u09B0\u09BE \u098F\u09AC\u0982 \u0989\u09B2\u09CD\u099F\u09CB\u099F\u09BE\u0993\
  \ \u0995\u09B0\u09BE, \u09AF\u09BE \u09A1\u09C7\u099F\u09BE \u0986\u09A6\u09BE\u09A8\
  -\u09AA\u09CD\u09B0\u09A6\u09BE\u09A8\u09C7\u09B0\u2026"
lastmod: '2024-03-17T18:47:43.742500-06:00'
model: gpt-4-0125-preview
summary: "JSON (JavaScript Object Notation) \u098F\u09B0 \u09B8\u09BE\u09A5\u09C7\
  \ \u0995\u09BE\u099C \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\u09C7 \u09B8\u09CD\u099F\
  \u09CD\u09B0\u09BF\u0982 \u09A5\u09C7\u0995\u09C7 JSON \u09A1\u09C7\u099F\u09BE\
  \ \u09AA\u09BE\u09B0\u09CD\u09B8 \u0995\u09B0\u09C7 Dart \u0985\u09AC\u099C\u09C7\
  \u0995\u09CD\u099F\u09C7 \u09B0\u09C2\u09AA\u09BE\u09A8\u09CD\u09A4\u09B0 \u0995\
  \u09B0\u09BE \u098F\u09AC\u0982 \u0989\u09B2\u09CD\u099F\u09CB\u099F\u09BE\u0993\
  \ \u0995\u09B0\u09BE, \u09AF\u09BE \u09A1\u09C7\u099F\u09BE \u0986\u09A6\u09BE\u09A8\
  -\u09AA\u09CD\u09B0\u09A6\u09BE\u09A8\u09C7\u09B0\u2026"
title: "JSON \u098F\u09B0 \u09B8\u09BE\u09A5\u09C7 \u0995\u09BE\u099C \u0995\u09B0\
  \u09BE"
---

{{< edit_this_page >}}

## কি এবং কেন?

JSON (JavaScript Object Notation) এর সাথে কাজ করা মানে স্ট্রিং থেকে JSON ডেটা পার্স করে Dart অবজেক্টে রূপান্তর করা এবং উল্টোটাও করা, যা ডেটা আদান-প্রদানের জন্য ওয়েব এবং অ্যাপ ডেভেলপমেন্টের একটি সাধারণ কাজ। প্রোগ্রামাররা এই কাজ করে থাকেন API, কনফিগারেশন, অথবা তাদের অ্যাপের মধ্যেকার কম্পোনেন্টের মধ্যে যোগাযোগের ডেটা কার্যকরভাবে হ্যান্ডেল করার জন্য।

## কিভাবে:

Dart `dart:convert` লাইব্রেরির সাথে JSON এর জন্য বিল্ট-ইন সাপোর্ট প্রদান করে, যা JSON এনকোড এবং ডিকোড করা সহজ করে তোলে। নিচের উদাহরণগুলি মৌলিক অপারেশন প্রদর্শন করছে:

**JSON স্ট্রিং থেকে Dart অবজেক্টে পার্সিং:**
```dart
import 'dart:convert';

void main() {
  // উদাহরণ JSON স্ট্রিং
  String jsonString = '{"name": "John", "age": 30, "email": "john@example.com"}';
  
  // JSON থেকে Dart Map এ ডিকোডিং
  Map<String, dynamic> user = jsonDecode(jsonString);
  
  print('হ্যালো, ${user['name']}! আপনি ${user['age']} বছরের।');
  // আউটপুট: হ্যালো, John! আপনি 30 বছরের।
}
```

**Dart অবজেক্ট থেকে JSON স্ট্রিংএ এনকোডিং:**
```dart
import 'dart:convert';

void main() {
  // উদাহরণ Dart অবজেক্ট
  Map<String, dynamic> user = {
    'name': 'Jane',
    'age': 25,
    'email': 'jane@example.com'
  };
  
  // Dart Map থেকে JSON এ এনকোডিং
  String jsonString = jsonEncode(user);
  
  print(jsonString);
  // আউটপুট: {"name":"Jane","age":25,"email":"jane@example.com"}
}
```

**জটিল মডেলের জন্য `json_serializable` ব্যবহার:**
জটিল ডেটা মডেলের জন্য, ম্যানুয়াল সিরিয়ালাইজেশন বিরক্তিকর হতে পারে। `json_serializable` প্যাকেজ এই প্রক্রিয়াটি অটোমেট করে। এটি অতিরিক্ত সেটআপ প্রয়োজন, যার মধ্যে আপনার `pubspec.yaml` এ ডিপেনডেন্সি যোগ করা এবং বিল্ড ফাইল তৈরি করা অন্তর্ভুক্ত। সেটাপের পর, আপনি নিম্নলিখিতভাবে এটা ব্যবহার করতে পারেন:

১. অ্যানোটেশন সহ একটি মডেল নির্ধারণ:
```dart
import 'package:json_annotation/json_annotation.dart';

part 'user.g.dart';

@JsonSerializable()
class User {
  String name;
  int age;
  String email;
  
  User({required this.name, required this.age, required this.email});
  
  factory User.fromJson(Map<String, dynamic> json) => _$UserFromJson(json);
  Map<String, dynamic> toJson() => _$UserToJson(this);
}
```

২. সিরিয়ালাইজেশন বয়লারপ্লেট উত্পন্ন করুন:
`user.g.dart` ফাইল জেনারেট করতে বিল্ড রানার কমান্ড ব্যবহার করুন:
```shell
flutter pub run build_runner build
```

৩. আপনার মডেল ব্যবহার করুন:
```dart
void main() {
  // JSON থেকে User এ পার্সিং
  Map userMap = jsonDecode('{"name": "John", "age": 30, "email": "john@example.com"}');
  User user = User.fromJson(userMap);
  
  print('ব্যবহারকারী: ${user.name}, বয়স: ${user.age}');
  // আউটপুট: ব্যবহারকারী: John, বয়স: 30

  // User কে ফিরে JSON এ রূপান্তর
  String jsonString = jsonEncode(user.toJson());
  print(jsonString);
  // আউটপুট: {"name":"John","age":30,"email":"john@example.com"}
}
```

এই উদাহরণগুলি Dart এ JSON এর সাথে মৌলিক এবং উন্নত মিথস্ক্রিয়া প্রদর্শন করে, ডেভেলপারদের তাদের অ্যাপ্লিকেশনে ডেটা সিরিয়ালাইজেশন কাজগুলি নির্বিঘ্নে হ্যান্ডেল করতে সক্ষম করে।
