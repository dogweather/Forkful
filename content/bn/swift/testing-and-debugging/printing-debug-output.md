---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:08:22.714109-06:00
description: "Swift-\u098F \u09A1\u09BF\u09AC\u09BE\u0997 \u0986\u0989\u099F\u09AA\
  \u09C1\u099F \u09AA\u09CD\u09B0\u09BF\u09A8\u09CD\u099F \u0995\u09B0\u09BE \u09AE\
  \u09BE\u09A8\u09C7 \u0986\u0987\u09A1\u09BF\u0987 \u09AC\u09BE \u0995\u09A8\u09B8\
  \u09CB\u09B2 \u098F\u09B0 \u09AE\u09A7\u09CD\u09AF\u09C7 \u098F\u0995\u099F\u09BE\
  \ \u09A1\u09BF\u09AC\u09BE\u0997 \u098F\u09B0\u09BF\u09DF\u09BE\u09DF \u09A1\u09BE\
  \u099F\u09BE \u09A6\u09C7\u0996\u09BE\u09A8\u09CB, \u09AF\u09BE \u0986\u09AA\u09A8\
  \u09BE\u09B0 \u0995\u09CB\u09A1\u09C7 \u0995\u09BF \u0998\u099F\u099B\u09C7 \u09A4\
  \u09BE \u09B2\u09BE\u0987\u09AD \u09AE\u09A8\u09BF\u099F\u09B0\u09BF\u0982 \u0995\
  \u09B0\u09BE\u09B0 \u099C\u09A8\u09CD\u09AF \u09AC\u09CD\u09AF\u09AC\u09B9\u09C3\
  \u09A4 \u09B9\u09DF\u0964\u2026"
lastmod: '2024-03-17T18:47:44.412281-06:00'
model: gpt-4-0125-preview
summary: "Swift-\u098F \u09A1\u09BF\u09AC\u09BE\u0997 \u0986\u0989\u099F\u09AA\u09C1\
  \u099F \u09AA\u09CD\u09B0\u09BF\u09A8\u09CD\u099F \u0995\u09B0\u09BE \u09AE\u09BE\
  \u09A8\u09C7 \u0986\u0987\u09A1\u09BF\u0987 \u09AC\u09BE \u0995\u09A8\u09B8\u09CB\
  \u09B2 \u098F\u09B0 \u09AE\u09A7\u09CD\u09AF\u09C7 \u098F\u0995\u099F\u09BE \u09A1\
  \u09BF\u09AC\u09BE\u0997 \u098F\u09B0\u09BF\u09DF\u09BE\u09DF \u09A1\u09BE\u099F\
  \u09BE \u09A6\u09C7\u0996\u09BE\u09A8\u09CB, \u09AF\u09BE \u0986\u09AA\u09A8\u09BE\
  \u09B0 \u0995\u09CB\u09A1\u09C7 \u0995\u09BF \u0998\u099F\u099B\u09C7 \u09A4\u09BE\
  \ \u09B2\u09BE\u0987\u09AD \u09AE\u09A8\u09BF\u099F\u09B0\u09BF\u0982 \u0995\u09B0\
  \u09BE\u09B0 \u099C\u09A8\u09CD\u09AF \u09AC\u09CD\u09AF\u09AC\u09B9\u09C3\u09A4\
  \ \u09B9\u09DF\u0964\u2026"
title: "\u09A1\u09BF\u09AC\u09BE\u0997 \u0986\u0989\u099F\u09AA\u09C1\u099F \u09AA\
  \u09CD\u09B0\u09BF\u09A8\u09CD\u099F \u0995\u09B0\u09BE"
---

{{< edit_this_page >}}

## কি এবং কেন?

Swift-এ ডিবাগ আউটপুট প্রিন্ট করা মানে আইডিই বা কনসোল এর মধ্যে একটা ডিবাগ এরিয়ায় ডাটা দেখানো, যা আপনার কোডে কি ঘটছে তা লাইভ মনিটরিং করার জন্য ব্যবহৃত হয়। এটা দ্রুত সমস্যা নির্ণয় করা অথবা কোডের প্রবাহ বুঝতে প্রাথমিক পদক্ষেপ—আপনার কোডের মস্তিষ্কের একটি ঝলক ভাবুন।

## কিভাবে:

Swift-এ, আপনার এক বন্ধু আছে `print()` ফাংশনের মধ্যে। ব্যবহার করা সহজ, এটি আপনাকে আপনার কোডে কি ঘটছে তা দেখার সুযোগ দেয়।

```Swift
var greeting = "Hello, playground"
print(greeting)
// আউটপুট: Hello, playground

let numbers = [1, 2, 3, 4, 5]
for number in numbers {
    print(number)
}
// আউটপুট:
// 1
// 2
// 3
// 4
// 5
```

কিন্তু অপেক্ষা করুন, আরও আছে! বিস্তারিত ডিবাগ তথ্য দরকার? `debugPrint()` আপনার জন্য উপস্থিত:

```Swift
debugPrint(greeting)
// আউটপুট: "Hello, playground"
```

ওই উদ্ধৃত চিহ্নগুলো লক্ষ্য করেছেন? `debugPrint()` ডেটা টাইপ এবং গঠন সম্পর্কে অতিরিক্ত তথ্য দিয়ে বিস্তারিত জানায়।

## গভীরে ডুব দেওয়া

Objective-C এর পুরানো দিনগুলোতে, আমরা জিনিসপত্র লগ করতে `NSLog` ব্যবহার করতাম। Swift ব্যাপারটি সহজ রাখল—`print()` হল স্ট্যান্ডার্ড আউটপুটের জন্য আপনার মূল সাধন, যেখানে `debugPrint()` হল বিস্তারিত দৃশ্যের জন্য স্বাদু মাখন।

একটি আন্তরিক তথ্য: Swift-এ স্ট্যান্ডার্ড আউটপুট শুধুমাত্র টেক্সট নয়—এটি যে কোন ধরণের টাইপ হতে পারে যা `CustomStringConvertible` অথবা `CustomDebugStringConvertible` এ মানানসই। এই প্রোটোকলগুলি আপনার অবজেক্টগুলি কিভাবে মুদ্রণের মাধ্যমে তাদের গল্প বলে তা কাস্টমাইজ করতে দেয়।

অন্তরালে, `print()` এবং `debugPrint()` `String(describing:)` এবং `String(reflecting:)` ব্যবহার করে আপনার অবজেক্টগুলিকে স্ট্রিং-এ পরিণত করে। মূলত, এই ফাংশনগুলি আপনার ডেটার একটি আয়না ব্যবহার করে সেলফি তোলে।

বিকল্প? আপনার কাছে `os_log` এবং `NSLog` আছে, কিন্তু এগুলি উচ্চমাত্রার লগিংয়ের জন্য আরো উপযুক্ত, না যে দ্রুত-এবং-নোংরা ডিবাগিংযে আমরা এখানে মাতব্বরি করছি।

## আরো দেখুন

- Apple-এর Swift API রেফারেন্স প্রিন্ট ফাংশনের জন্য: [Swift Standard Library: print(_:separator:terminator:)](https://developer.apple.com/documentation/swift/1541053-print)
- Swift-এ লগিং এর গভীরে দেখা, GDPR এবং গোপনীয়তা বিবেচনা: [Unified Logging and Activity Tracing](https://developer.apple.com/documentation/os/logging)
- Swift-এর স্ট্রিং ইন্টারপোলেশন এবং ডিবাগ বর্ণনার জন্য কাস্টমাইজেবিলিটি: [CustomStringConvertible](https://developer.apple.com/documentation/swift/customstringconvertible) এবং [CustomDebugStringConvertible](https://developer.apple.com/documentation/swift/customdebugstringconvertible)
