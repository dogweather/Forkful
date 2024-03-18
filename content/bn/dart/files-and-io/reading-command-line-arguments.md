---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:09:52.542368-06:00
description: "Dart \u098F \u0995\u09AE\u09BE\u09A8\u09CD\u09A1 \u09B2\u09BE\u0987\u09A8\
  \ \u0986\u09B0\u09CD\u0997\u09C1\u09AE\u09C7\u09A8\u09CD\u099F\u0997\u09C1\u09B2\
  \u09BF \u09AA\u09A1\u09BC\u09BE \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\
  \u09AE\u09BE\u09B0\u09A6\u09C7\u09B0\u0995\u09C7 \u098F\u0995\u099F\u09BF Dart \u09AA\
  \u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE \u098F\u0995\u09CD\u09B8\u09BF\u0995\
  \u09BF\u0989\u099F \u0995\u09B0\u09BE\u09B0 \u09B8\u09AE\u09AF\u09BC \u09B8\u09B0\
  \u09BE\u09B8\u09B0\u09BF \u0995\u09A8\u09B8\u09CB\u09B2\u09C7 \u09A1\u09C7\u099F\
  \u09BE \u0987\u09A8\u09AA\u09C1\u099F \u0995\u09B0\u09BE\u09B0 \u0985\u09A8\u09C1\
  \u09AE\u09A4\u09BF \u09A6\u09C7\u09AF\u09BC, \u09AF\u09BE \u09AC\u09BF\u09AD\u09BF\
  \u09A8\u09CD\u09A8\u2026"
lastmod: '2024-03-17T18:47:43.736242-06:00'
model: gpt-4-0125-preview
summary: "Dart \u098F \u0995\u09AE\u09BE\u09A8\u09CD\u09A1 \u09B2\u09BE\u0987\u09A8\
  \ \u0986\u09B0\u09CD\u0997\u09C1\u09AE\u09C7\u09A8\u09CD\u099F\u0997\u09C1\u09B2\
  \u09BF \u09AA\u09A1\u09BC\u09BE \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\
  \u09AE\u09BE\u09B0\u09A6\u09C7\u09B0\u0995\u09C7 \u098F\u0995\u099F\u09BF Dart \u09AA\
  \u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE \u098F\u0995\u09CD\u09B8\u09BF\u0995\
  \u09BF\u0989\u099F \u0995\u09B0\u09BE\u09B0 \u09B8\u09AE\u09AF\u09BC \u09B8\u09B0\
  \u09BE\u09B8\u09B0\u09BF \u0995\u09A8\u09B8\u09CB\u09B2\u09C7 \u09A1\u09C7\u099F\
  \u09BE \u0987\u09A8\u09AA\u09C1\u099F \u0995\u09B0\u09BE\u09B0 \u0985\u09A8\u09C1\
  \u09AE\u09A4\u09BF \u09A6\u09C7\u09AF\u09BC, \u09AF\u09BE \u09AC\u09BF\u09AD\u09BF\
  \u09A8\u09CD\u09A8\u2026"
title: "\u0995\u09AE\u09BE\u09A8\u09CD\u09A1 \u09B2\u09BE\u0987\u09A8 \u0986\u09B0\
  \u09CD\u0997\u09C1\u09AE\u09C7\u09A8\u09CD\u099F\u0997\u09C1\u09B2\u09BF \u09AA\u09A1\
  \u09BC\u09BE"
---

{{< edit_this_page >}}

## কি এবং কেন?

Dart এ কমান্ড লাইন আর্গুমেন্টগুলি পড়া প্রোগ্রামারদেরকে একটি Dart প্রোগ্রাম এক্সিকিউট করার সময় সরাসরি কনসোলে ডেটা ইনপুট করার অনুমতি দেয়, যা বিভিন্ন ব্যবহারের ক্ষেত্র, যেমন অটোমেশন স্ক্রিপ্ট, CLI টুল, অথবা ব্যাচ প্রসেসিং এর জন্য এর ইন্টার‌্যাক্টিভিটি এবং নমনীয়তা বাড়ায়। এই বৈশিষ্ট্যটি অভিযোজয়ী এবং ইউজার-ফ্রেন্ডলি কমান্ড-লাইন অ্যাপ্লিকেশন তৈরি করার জন্য মৌলিক।

## কিভাবে:

Dart `List<String> args` এর মাধ্যমে কমান্ড লাইন আর্গুমেন্টগুলি অ্যাক্সেস করার একটি সহজ পদ্ধতি প্রস্তাব করে, যা মূল পদ্ধতিতে থাকে। নিচে কমান্ড লাইন আর্গুমেন্টগুলি পড়া এবং ব্যবহার করার একটি সাধারণ উদাহরণ দেওয়া হল।

```dart
// main.dart
void main(List<String> args) {
  print('Command Line Arguments:');
  for (var i = 0; i < args.length; i++) {
    print('${i + 1}: ${args[i]}');
  }
}
```

এই Dart প্রোগ্রামটি চালানো এবং কমান্ড লাইন আর্গুমেন্ট পাস করার জন্য, Dart CLI এর মতো ব্যবহার করুন:

```shell
dart run main.dart Hello World!
```

প্রত্যাশিত আউটপুট:

```
Command Line Arguments:
1: Hello
2: World!
```

### একটি জনপ্রিয় থার্ড-পার্টি লাইব্রেরি ব্যবহার করা: `args`

যদিও Dart-এর নিজস্ব ক্ষমতাগুলি অনেক অ্যাপ্লিকেশনের জন্য প্রবল, `args` প্যাকেজটি আরও জটিল প্রয়োজনীয়তাগুলোর জন্য কমান্ড লাইন আর্গুমেন্ট সংজ্ঞায়িত এবং পার্স করার একটি উন্নত উপায় প্রদান করে।

প্রথমে, `pubspec.yaml`-এ `args` প্যাকেজটি যোগ করুন:

```yaml
dependencies:
  args: ^2.0.0
```

তারপর, আপনার প্রোগ্রামে এটি ব্যবহার করুন এরকমভাবে:

```dart
// 'args' প্যাকেজ ব্যবহার করা হচ্ছে
import 'package:args/args.dart';

void main(List<String> arguments) {
  final parser = ArgParser()..addOption('name', abbr: 'n');
  final argResults = parser.parse(arguments);

  if (argResults.wasParsed('name')) {
    print('Hello, ${argResults['name']}!');
  } else {
    print('No name provided.');
  }
}
```

নামযুক্ত আর্গুমেন্টের সাথে প্রোগ্রামটি চালান:

```shell
dart run main.dart --name=John
```

প্রত্যাশিত আউটপুট:

```
Hello, John!
```

কমান্ড লাইন আর্গুমেন্ট পার্স করার এই সাধারণ পরিচয়, উভয় নেটিভ এবং `args` লাইব্রেরির সাথে, Dart-এর কনসোল থেকে সরাসরি ইউজার ইনপুট হ্যান্ডেল করার ক্ষমতা দেখায়, যা আরও ইন্টার‌্যাক্টিভ এবং ডা্যানামিক CLI অ্যাপ্লিকেশন তৈরির পথ খোলে।
