---
changelog:
- 2024-03-17, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-17 17:48:32.495721-06:00
description: "Dart \u098F \u09AC\u09B0\u09CD\u09A4\u09AE\u09BE\u09A8 \u09A4\u09BE\u09B0\
  \u09BF\u0996 \u09AA\u09BE\u0993\u09AF\u09BC\u09BE\u09B0 \u099C\u09A8\u09CD\u09AF\
  \ \u09B8\u09BF\u09B8\u09CD\u099F\u09C7\u09AE \u09A5\u09C7\u0995\u09C7 \u09AC\u09B0\
  \u09CD\u09A4\u09AE\u09BE\u09A8 \u09A4\u09BE\u09B0\u09BF\u0996 \u0993 \u09B8\u09AE\
  \u09AF\u09BC\u09C7\u09B0 \u09A4\u09A5\u09CD\u09AF \u09A8\u09C7\u0993\u09AF\u09BC\
  \u09BE \u09B9\u09AF\u09BC\u0964 \u098F\u0987 \u0995\u09BE\u09B0\u09CD\u09AF\u0995\
  \u09BE\u09B0\u09BF\u09A4\u09BE \u09B8\u09BE\u09A7\u09BE\u09B0\u09A3\u09A4 \u0985\
  \u09CD\u09AF\u09BE\u09AA\u09CD\u09B2\u09BF\u0995\u09C7\u09B6\u09A8\u0997\u09C1\u09B2\
  \u09BF\u09A4\u09C7 \u0987\u09AD\u09C7\u09A8\u09CD\u099F \u09B8\u09AE\u09AF\u09BC\
  \ \u09A8\u09BF\u09B0\u09CD\u09A6\u09C7\u09B6 \u0995\u09B0\u09BE,\u2026"
lastmod: '2024-03-17T18:47:43.730307-06:00'
model: gpt-4-0125-preview
summary: "Dart \u098F \u09AC\u09B0\u09CD\u09A4\u09AE\u09BE\u09A8 \u09A4\u09BE\u09B0\
  \u09BF\u0996 \u09AA\u09BE\u0993\u09AF\u09BC\u09BE\u09B0 \u099C\u09A8\u09CD\u09AF\
  \ \u09B8\u09BF\u09B8\u09CD\u099F\u09C7\u09AE \u09A5\u09C7\u0995\u09C7 \u09AC\u09B0\
  \u09CD\u09A4\u09AE\u09BE\u09A8 \u09A4\u09BE\u09B0\u09BF\u0996 \u0993 \u09B8\u09AE\
  \u09AF\u09BC\u09C7\u09B0 \u09A4\u09A5\u09CD\u09AF \u09A8\u09C7\u0993\u09AF\u09BC\
  \u09BE \u09B9\u09AF\u09BC\u0964 \u098F\u0987 \u0995\u09BE\u09B0\u09CD\u09AF\u0995\
  \u09BE\u09B0\u09BF\u09A4\u09BE \u09B8\u09BE\u09A7\u09BE\u09B0\u09A3\u09A4 \u0985\
  \u09CD\u09AF\u09BE\u09AA\u09CD\u09B2\u09BF\u0995\u09C7\u09B6\u09A8\u0997\u09C1\u09B2\
  \u09BF\u09A4\u09C7 \u0987\u09AD\u09C7\u09A8\u09CD\u099F \u09B8\u09AE\u09AF\u09BC\
  \ \u09A8\u09BF\u09B0\u09CD\u09A6\u09C7\u09B6 \u0995\u09B0\u09BE,\u2026"
title: "\u09AC\u09B0\u09CD\u09A4\u09AE\u09BE\u09A8 \u09A4\u09BE\u09B0\u09BF\u0996\
  \ \u09AA\u09C7\u09A4\u09C7"
---

{{< edit_this_page >}}

## কি এবং কেন?
Dart এ বর্তমান তারিখ পাওয়ার জন্য সিস্টেম থেকে বর্তমান তারিখ ও সময়ের তথ্য নেওয়া হয়। এই কার্যকারিতা সাধারণত অ্যাপ্লিকেশনগুলিতে ইভেন্ট সময় নির্দেশ করা, ব্যবহারকারীদের কাছে বর্তমান তারিখ দেখানো, অথবা সময়ের মেয়াদ হিসেব করার মতো ফিচারগুলির জন্য ব্যবহৃত হয়। বর্তমান তারিখ কীভাবে দক্ষভাবে অনুসন্ধান এবং পরিচালনা করা যায় তা জানা সিডিউলিং, লগিং, এবং সময়-সংবেদনশীল ফিচারগুলির জন্য মৌলিক।

## কিভাবে:
Dart এর মূল লাইব্রেরি `DateTime` ক্লাসের মাধ্যমে বর্তমান তারিখ ও সময় পেতে সরাসরি প্রবেশ প্রদান করে। বর্তমান তারিখ পাওয়ার মৌলিক উদাহরণ হল:

```dart
void main() {
  DateTime now = DateTime.now();
  print(now); // উদাহরন আউটপুট: 2023-04-12 10:00:00.000
}
```

যদি আপনি শুধুমাত্র তারিখ অংশটুকু (বছর, মাস, দিন) প্রয়োজন হয়, তাহলে `DateTime` অবজেক্টটি ফর্ম্যাট করতে পারেন:

```dart
void main() {
  DateTime now = DateTime.now();
  String formattedDate = "${now.year}-${now.month}-${now.day}";
  print(formattedDate); // উদাহরন আউটপুট: 2023-04-12
}
```

Dart জটিল তারিখ ফর্ম্যাটিংয়ের জন্য কোনো অন্তর্ভুক্ত লাইব্রেরি রাখে না, তবে এই উদ্দেশ্যে আপনি `intl` প্যাকেজ ব্যবহার করতে পারেন। প্রথমে, আপনার `pubspec.yaml` এ প্যাকেজটি যোগ করুন:

```yaml
dependencies:
  intl: ^0.17.0
```

তারপর, আপনি সহজেই তারিখগুলি ফর্ম্যাট করতে পারেন:

```dart
import 'package:intl/intl.dart';

void main() {
  DateTime now = DateTime.now();
  String formattedDate = DateFormat('yyyy-MM-dd').format(now);
  print(formattedDate); // উদাহরন আউটপুট: 2023-04-12
}
```

আরো উন্নত ফর্ম্যাটিং অপশন অন্বেষণ করতে, `intl` প্যাকেজ দ্বারা প্রদত্ত `DateFormat` ক্লাসটি পরীক্ষা করুন, যা বিভিন্ন ধরণের প্যাটার্ন এবং লোকেলগুলি সমর্থন করে।
