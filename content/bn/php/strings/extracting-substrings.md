---
changelog:
- 2024-03-17, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-17 17:48:19.888909-06:00
description: "\u09B8\u09BE\u09AC\u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u09AC\u09C7\
  \u09B0 \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\u09C7 \u098F\u0995\u099F\u09BF \u09B8\
  \u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u09A5\u09C7\u0995\u09C7 \u09A8\u09BF\u09B0\
  \u09CD\u09A6\u09BF\u09B7\u09CD\u099F \u0985\u0982\u09B6 \u099F\u09C7\u09A8\u09C7\
  \ \u0986\u09A8\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\
  \u09BE\u09B0\u09B0\u09BE \u098F\u099F\u09BF \u09A1\u09C7\u099F\u09BE \u09AA\u09CD\
  \u09B0\u0995\u09CD\u09B0\u09BF\u09AF\u09BC\u09BE \u0995\u09B0\u09A4\u09C7 \u0985\
  \u09A5\u09AC\u09BE \u09AE\u09CD\u09AF\u09BE\u09A8\u09BF\u09AA\u09C1\u09B2\u09C7\u099F\
  \ \u0995\u09B0\u09A4\u09C7 \u0995\u09B0\u09C7, \u09AF\u09C7\u09AE\u09A8- \u098F\u0995\
  \u099F\u09BF \u0987\u09AE\u09C7\u0987\u09B2\u2026"
lastmod: '2024-03-17T18:47:44.117847-06:00'
model: gpt-4-0125-preview
summary: "\u09B8\u09BE\u09AC\u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u09AC\u09C7\
  \u09B0 \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\u09C7 \u098F\u0995\u099F\u09BF \u09B8\
  \u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u09A5\u09C7\u0995\u09C7 \u09A8\u09BF\u09B0\
  \u09CD\u09A6\u09BF\u09B7\u09CD\u099F \u0985\u0982\u09B6 \u099F\u09C7\u09A8\u09C7\
  \ \u0986\u09A8\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\
  \u09BE\u09B0\u09B0\u09BE \u098F\u099F\u09BF \u09A1\u09C7\u099F\u09BE \u09AA\u09CD\
  \u09B0\u0995\u09CD\u09B0\u09BF\u09AF\u09BC\u09BE \u0995\u09B0\u09A4\u09C7 \u0985\
  \u09A5\u09AC\u09BE \u09AE\u09CD\u09AF\u09BE\u09A8\u09BF\u09AA\u09C1\u09B2\u09C7\u099F\
  \ \u0995\u09B0\u09A4\u09C7 \u0995\u09B0\u09C7, \u09AF\u09C7\u09AE\u09A8- \u098F\u0995\
  \u099F\u09BF \u0987\u09AE\u09C7\u0987\u09B2 \u09A0\u09BF\u0995\u09BE\u09A8\u09BE\
  \ \u09A5\u09C7\u0995\u09C7 \u0987\u0989\u099C\u09BE\u09B0\u09A8\u09BE\u09AE \u09AC\
  \u09BE \u09AB\u09BE\u0987\u09B2\u09C7\u09B0 \u09A8\u09BE\u09AE \u09A5\u09C7\u0995\
  \u09C7 \u09AB\u09BE\u0987\u09B2 \u098F\u0995\u09CD\u09B8\u099F\u09C7\u09A8\u09B6\
  \u09A8 \u09AC\u09C7\u09B0 \u0995\u09B0\u09BE\u0964."
title: "\u09B8\u09BE\u09AC\u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u09AC\u09C7\u09B0\
  \ \u0995\u09B0\u09BE"
weight: 6
---

## কিভাবে:
PHP সাবস্ট্রিং বের করার জন্য বেশ কিছু ফাংশন অফার করে। চলুন `substr`, `mb_substr`, এবং `strstr` চেক করে দেখি।

```PHP
$string = "Hello, World! Programming is fun.";

// 'World' বের করা `substr` ব্যবহার করে।
echo substr($string, 7, 5); // আউটপুট: World

// UTF-8 স্ট্রিং উদাহরণ `mb_substr` ব্যবহার করে মাল্টি-বাইট ক্যারেকটারের জন্য।
$utf8String = "こんにちは世界";
echo mb_substr($utf8String, 5, 2); // আউটপুট: 世

// কমা পরবর্তী সবকিছু `strstr` ব্যবহার করে পাওয়া।
echo strstr($string, ","); // আউটপুট: , World! Programming is fun.
```

## গভীরে ডাইভ
PHP-র প্রাথমিক দিনগুলিতে, একটি স্ট্রিং থেকে এক অংশ ছিনতাই করার মূল উপায় ছিল `substr()`। তবে, `substr()` এর (এখনো আছে) একটি সীমাবদ্ধতা রয়েছে: এটি অ-ইংরেজি ক্যারেকটারের (যেমন- জাপানি অথবা আরবি) সাথে ভালো খাপ খায় না।

এখানে আসে `mb_substr()`, মাল্টিবাইট-নিরাপদ সমতুল্য যা বিভিন্ন এনকোডিংয়ের অক্ষরগুলির প্রতি সম্মান জানায়। এটা নিশ্চিত করে যে যখন আপনি একটি সাবস্ট্রিং টানছেন, আপনি কোন অক্ষরের মধ্যে দিয়ে অর্ধেক বাইট দিয়ে ছিঁড়ে যাচ্ছেন না, যা আন্তর্জাতিক অ্যাপ্লিকেশনগুলির জন্য অপরিহার্য।

অপরদিকে, `strstr()` একটি সাবস্ট্রিং এর প্রথম উদিতি খুঁজে বের করে এবং তারপর তার পরবর্তী সবকিছু দেয়। এটির অপর নাম `strchr()`, যা `strstr()` এর একটি অ্যালিয়াস।

যেখানে `substr()` এবং `mb_substr()` আপনাকে স্পষ্টভাবে স্পেসিফাই করে দেয় কোথা থেকে শুরু করবেন এবং কতটা নেবেন, সেখানে `strstr()` আরও বেশি "খুঁজে বের করে বাকিটুকু দাও" টূলের মতো।

## আরও দেখুন
আরও জানার আগ্রহ থাকলে এখানে কিছু অতিরিক্ত পড়ার জন্য:

- PHP অফিসিয়াল ডকুমেন্টেশন স্ট্রিং ফাংশনের জন্য: https://www.php.net/manual/en/ref.strings.php
- PHP-র মাল্টিবাইট স্ট্রিং ফাংশনস সম্পর্কে গভীরে ডাইভ: https://www.php.net/manual/en/book.mbstring.php
- ক্যারেকটার এনকোডিং এবং এটা কেন গুরুত্বপূর্ণ তা সম্পর্কে আরও জেনে নিন: http://kunststube.net/encoding/
