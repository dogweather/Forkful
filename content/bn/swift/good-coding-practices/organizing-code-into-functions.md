---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:04:15.948212-06:00
description: "\u0995\u09CB\u09A1\u0995\u09C7 \u09AB\u09BE\u0982\u09B6\u09A8\u09C7\
  \ \u0997\u09CD\u09B0\u09C1\u09AA\u09BF\u0982 \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\
  \u09C7 \u099F\u09BE\u09B8\u09CD\u0995\u0997\u09C1\u09B2\u09CB\u0995\u09C7 \u09AA\
  \u09C1\u09A8\u0983\u09AC\u09CD\u09AF\u09AC\u09B9\u09BE\u09B0\u09AF\u09CB\u0997\u09CD\
  \u09AF \u0996\u09A3\u09CD\u09A1\u09C7 \u09AD\u09BE\u0997 \u0995\u09B0\u09BE\u0964\
  \ \u098F\u099F\u09BF \u0995\u09CB\u09A1\u0995\u09C7 \u09AA\u09B0\u09BF\u09B7\u09CD\
  \u0995\u09BE\u09B0, \u0995\u09AE \u09A4\u09CD\u09B0\u09C1\u099F\u09BF\u09AA\u09C2\
  \u09B0\u09CD\u09A3 \u098F\u09AC\u0982 \u09A1\u09BF\u09AC\u09BE\u0997 \u09AC\u09BE\
  \ \u09B0\u09BF\u09AB\u09CD\u09AF\u09BE\u0995\u09CD\u099F\u09B0 \u0995\u09B0\u09BE\
  \ \u09B8\u09B9\u099C \u0995\u09B0\u09C7 \u09A4\u09CB\u09B2\u09C7\u0964"
lastmod: '2024-03-17T18:47:44.415207-06:00'
model: gpt-4-0125-preview
summary: "\u0995\u09CB\u09A1\u0995\u09C7 \u09AB\u09BE\u0982\u09B6\u09A8\u09C7 \u0997\
  \u09CD\u09B0\u09C1\u09AA\u09BF\u0982 \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\u09C7\
  \ \u099F\u09BE\u09B8\u09CD\u0995\u0997\u09C1\u09B2\u09CB\u0995\u09C7 \u09AA\u09C1\
  \u09A8\u0983\u09AC\u09CD\u09AF\u09AC\u09B9\u09BE\u09B0\u09AF\u09CB\u0997\u09CD\u09AF\
  \ \u0996\u09A3\u09CD\u09A1\u09C7 \u09AD\u09BE\u0997 \u0995\u09B0\u09BE\u0964 \u098F\
  \u099F\u09BF \u0995\u09CB\u09A1\u0995\u09C7 \u09AA\u09B0\u09BF\u09B7\u09CD\u0995\
  \u09BE\u09B0, \u0995\u09AE \u09A4\u09CD\u09B0\u09C1\u099F\u09BF\u09AA\u09C2\u09B0\
  \u09CD\u09A3 \u098F\u09AC\u0982 \u09A1\u09BF\u09AC\u09BE\u0997 \u09AC\u09BE \u09B0\
  \u09BF\u09AB\u09CD\u09AF\u09BE\u0995\u09CD\u099F\u09B0 \u0995\u09B0\u09BE \u09B8\
  \u09B9\u099C \u0995\u09B0\u09C7 \u09A4\u09CB\u09B2\u09C7\u0964."
title: "\u0995\u09CB\u09A1\u0995\u09C7 \u09AB\u09BE\u0982\u09B6\u09A8\u09C7\u09B0\
  \ \u09AE\u09A7\u09CD\u09AF\u09C7 \u09B8\u0982\u0997\u09A0\u09A8 \u0995\u09B0\u09BE"
weight: 18
---

## কিভাবে:
কল্পনা করুন একটি টাস্ক: একটি অ্যারের গড় গণনা করা। ফাংশন ছাড়া, আপনি সবকিছু main এ স্থাপন করতেন। ফাংশন ব্যবহার করে, আপনি এটি এভাবে করতেন:

```swift
func calculateAverage(of numbers: [Double]) -> Double {
    let sum = numbers.reduce(0, +)
    return numbers.isEmpty ? 0 : sum / Double(numbers.count)
}

// ব্যবহার
let scores = [92.5, 88.75, 99.0, 70.5]
let averageScore = calculateAverage(of: scores)
print("গড় স্কোর হল \(averageScore)")
```

নমুনা আউটপুট হবে: 
```
গড় স্কোর হল 87.6875
```

## গভীরে যাওয়া
একটি সময় যখন প্রোগ্রামিং জটিল হয়ে ওঠে, ফাংশন জটিলতা সামাল দেওয়ার একটি মূল উপাদানে পরিণত হয়। বিকল্প অন্তর্ভুক্ত ইনলাইন কোডিং এবং কোড কপি-পেস্ট করা (স্প্যাগেটি কোড) – যা এখন মূলত খারাপ অনুশীলন বিবেচিত। Swift এ, ফাংশনগুলি প্রথম শ্রেণির নাগরিক; এগুলো ভেরিয়েবলে অ্যাসাইন করা যায়, আর্গুমেন্ট হিসেবে পাস করা যায় এবং অন্য ফাংশন থেকে রিটার্ন করা যায়, যা কোডকে আরও মডিউলার এবং নমনীয় করে তোলে।

বাস্তবায়নের দিক থেকে, আপনার ফাংশনগুলি এমনভাবে ডিজাইন করুন যাতে এটি একটি জিনিসকে ভালভাবে করতে পারে। এমন ফাংশনের লক্ষ্য রাখুন যার একটি স্পষ্ট উদ্দেশ্য এবং একটি নাম রয়েছে যা এটি প্রতিফলিত করে। প্যারামিটারের সংখ্যা দেখুন—অনেকগুলো থাকলে আপনি সম্ভবত অনেক কিছু করছেন। ভুল সম্পর্কে চিন্তা করছেন? এরর হ্যান্ডলিং ফাংশন বিবেচনা করুন এবং সমস্যাগুলোকে সুন্দরভাবে সামাল দিন। মনে রাখবেন: Swift পড়াশোনা এবং রক্ষণাবেক্ষণের সহজতার বিষয়ে সব।

## আরও দেখুন
- [Swift প্রোগ্রামিং ভাষার গাইড - ফাংশন](https://docs.swift.org/swift-book/LanguageGuide/Functions.html)
- [রে ওয়েন্ডারলিচের Swift স্টাইল গাইড](https://github.com/raywenderlich/swift-style-guide)
- [মার্টিন ফাউলারের রিফ্যাক্টরিং: বর্তমান কোডের ডিজাইন উন্নতি করা](https://martinfowler.com/books/refactoring.html)
