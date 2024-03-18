---
changelog:
- 2024-03-17, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-17 17:48:14.938726-06:00
description: "\u09A1\u09BE\u09B0\u09CD\u099F\u09C7 \u098F\u0995\u099F\u09BF \u09B8\
  \u09CD\u099F\u09CD\u09B0\u09BF\u0982-\u098F\u09B0 \u09A6\u09C8\u09B0\u09CD\u0998\
  \u09CD\u09AF \u09A8\u09BF\u09B0\u09CD\u09A3\u09AF\u09BC \u0995\u09B0\u09BE \u09AE\
  \u09BE\u09A8\u09C7 \u098F\u0995\u099F\u09BF \u09A6\u09C7\u0993\u09AF\u09BC\u09BE\
  \ \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982-\u098F \u0995\u09CB\u09A1 \u0987\u0989\
  \u09A8\u09BF\u099F\u09C7\u09B0 (\u09B8\u09B9\u099C\u09AD\u09BE\u09AC\u09C7 \u09AC\
  \u09B2\u09A4\u09C7 \u0997\u09C7\u09B2\u09C7, \u0985\u0995\u09CD\u09B7\u09B0\u09C7\
  \u09B0 \u09B8\u0982\u0996\u09CD\u09AF\u09BE) \u09B8\u0982\u0996\u09CD\u09AF\u09BE\
  \ \u09A8\u09BF\u09B0\u09CD\u09A7\u09BE\u09B0\u09A3 \u0995\u09B0\u09BE\u0964 \u09AA\
  \u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE\u2026"
lastmod: '2024-03-17T18:47:43.707751-06:00'
model: gpt-4-0125-preview
summary: "\u09A1\u09BE\u09B0\u09CD\u099F\u09C7 \u098F\u0995\u099F\u09BF \u09B8\u09CD\
  \u099F\u09CD\u09B0\u09BF\u0982-\u098F\u09B0 \u09A6\u09C8\u09B0\u09CD\u0998\u09CD\
  \u09AF \u09A8\u09BF\u09B0\u09CD\u09A3\u09AF\u09BC \u0995\u09B0\u09BE \u09AE\u09BE\
  \u09A8\u09C7 \u098F\u0995\u099F\u09BF \u09A6\u09C7\u0993\u09AF\u09BC\u09BE \u09B8\
  \u09CD\u099F\u09CD\u09B0\u09BF\u0982-\u098F \u0995\u09CB\u09A1 \u0987\u0989\u09A8\
  \u09BF\u099F\u09C7\u09B0 (\u09B8\u09B9\u099C\u09AD\u09BE\u09AC\u09C7 \u09AC\u09B2\
  \u09A4\u09C7 \u0997\u09C7\u09B2\u09C7, \u0985\u0995\u09CD\u09B7\u09B0\u09C7\u09B0\
  \ \u09B8\u0982\u0996\u09CD\u09AF\u09BE) \u09B8\u0982\u0996\u09CD\u09AF\u09BE \u09A8\
  \u09BF\u09B0\u09CD\u09A7\u09BE\u09B0\u09A3 \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\
  \u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE\u2026"
title: "\u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u098F\u09B0 \u09A6\u09C8\u09B0\
  \u09CD\u0998\u09CD\u09AF \u099A\u09BF\u09B9\u09CD\u09A8\u09BF\u09A4 \u0995\u09B0\
  \u09BE"
---

{{< edit_this_page >}}

## কি এবং কেন?
ডার্টে একটি স্ট্রিং-এর দৈর্ঘ্য নির্ণয় করা মানে একটি দেওয়া স্ট্রিং-এ কোড ইউনিটের (সহজভাবে বলতে গেলে, অক্ষরের সংখ্যা) সংখ্যা নির্ধারণ করা। প্রোগ্রামাররা এটি করে থাকেন স্ট্রিংসমূহকে আরও নির্দিষ্টভাবে ম্যানিপুলেট করার জন্য, যেমন ইনপুট যাচাই করা, ডিসপ্লে টেক্সট ছাঁটাই করা, অথবা ডাটা ফরম্যাট প্রক্রিয়া করা যেখানে দৈর্ঘ্যের গুরুত্ব রয়েছে (উদাঃ দৈর্ঘ্য-পূর্ববর্তী বার্তা সম্বলিত প্রোটোকলগুলি)।

## কিভাবে:
ডার্ট একটি স্ট্রিং-এর দৈর্ঘ্য পাওয়ার জন্য `length` প্রোপার্টি ব্যবহার করে সোজা পথ দেয়। এখানে একটি মৌলিক উদাহরণ দেওয়া হল:

```dart
void main() {
  String myString = "Hello, Dart!";
  print("The length of '\(myString)' is: \(myString.length)");
  // আউটপুট: The length of 'Hello, Dart!' is: 12
}
```
এই প্রোপার্টি স্ট্রিং-এ থাকা UTF-16 কোড ইউনিটের সংখ্যা গণনা করে, যা সাধারণ ব্যবহারের ক্ষেত্রে স্ট্রিং-এর দৈর্ঘ্যের সাথে মেলে।

আরও বিশদ টেক্সট প্রসেসিংয়ের জন্য, বিশেষ করে বেসিক মাল্টিলিংগুয়াল প্লেনের (BMP) বাইরে ইউনিকোড অক্ষরগুলি জড়িত হলে, গ্রাফেম ক্লাস্টার গণনা করার জন্য `characters` প্যাকেজ ব্যবহার করার বিবেচনা করুন, যা ইউজার-অনুভূত অক্ষরগুলিকে আরও সঠিকভাবে প্রতিনিধিত্ব করে।

প্রথমে, `characters` আপনার `pubspec.yaml`-এ যোগ করুন:

```yaml
dependencies:
  characters: ^1.2.0
```

তারপর, এটি এমনভাবে ব্যবহার করুন:

```dart
import 'package:characters/characters.dart';

void main() {
  String myEmojiString = "👨‍👩‍👧‍👦 family";
  print("The length of '\(myEmojiString)' is: \(myEmojiString.characters.length)");
  // আউটপুট: The length of '👨‍👩‍👧‍👦 family' is: 8
}
```

এই উদাহরণে, `myEmojiString.characters.length` আমাদের ইউনিকোড গ্রাফেম ক্লাস্টারের দৈর্ঘ্য বুঝায়, যা ইমোজি বা যৌথ অক্ষর চিহ্নের মতো জটিল অক্ষরযুক্ত স্ট্রিংগুলির জন্য আরও সঠিক প্রতিনিধিত্ব প্রদান করে।
