---
changelog:
- 2024-03-17, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-17 17:48:13.704824-06:00
description: "\u098F\u0995\u099F\u09BF \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982\u09DF\
  \u09C7\u09B0 \u09A6\u09C8\u09B0\u09CD\u0998\u09CD\u09AF \u09A8\u09BF\u09B0\u09CD\
  \u09A3\u09AF\u09BC \u09AE\u09BE\u09A8\u09C7 \u09B9\u09B2 \u09A4\u09BE\u09A4\u09C7\
  \ \u0995\u09A4\u0997\u09C1\u09B2\u09BF \u0985\u0995\u09CD\u09B7\u09B0 \u0986\u099B\
  \u09C7 \u09A4\u09BE \u09AC\u09C7\u09B0 \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\
  \u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u0987\u09A8\u09AA\u09C1\
  \u099F \u09AF\u09BE\u099A\u09BE\u0987 \u0995\u09B0\u09BE, \u099F\u09C7\u0995\u09CD\
  \u09B8\u099F \u09AE\u09CD\u09AF\u09BE\u09A8\u09BF\u09AA\u09C1\u09B2\u09C7\u099F\
  \ \u0995\u09B0\u09BE, \u0985\u09A5\u09AC\u09BE \u09A4\u09BE\u09A6\u09C7\u09B0 \u09A1\
  \u09BE\u099F\u09BE\u09B0 \u0986\u0995\u09BE\u09B0\u2026"
lastmod: '2024-03-17T18:47:44.400065-06:00'
model: gpt-4-0125-preview
summary: "\u098F\u0995\u099F\u09BF \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982\u09DF\
  \u09C7\u09B0 \u09A6\u09C8\u09B0\u09CD\u0998\u09CD\u09AF \u09A8\u09BF\u09B0\u09CD\
  \u09A3\u09AF\u09BC \u09AE\u09BE\u09A8\u09C7 \u09B9\u09B2 \u09A4\u09BE\u09A4\u09C7\
  \ \u0995\u09A4\u0997\u09C1\u09B2\u09BF \u0985\u0995\u09CD\u09B7\u09B0 \u0986\u099B\
  \u09C7 \u09A4\u09BE \u09AC\u09C7\u09B0 \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\
  \u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u0987\u09A8\u09AA\u09C1\
  \u099F \u09AF\u09BE\u099A\u09BE\u0987 \u0995\u09B0\u09BE, \u099F\u09C7\u0995\u09CD\
  \u09B8\u099F \u09AE\u09CD\u09AF\u09BE\u09A8\u09BF\u09AA\u09C1\u09B2\u09C7\u099F\
  \ \u0995\u09B0\u09BE, \u0985\u09A5\u09AC\u09BE \u09A4\u09BE\u09A6\u09C7\u09B0 \u09A1\
  \u09BE\u099F\u09BE\u09B0 \u0986\u0995\u09BE\u09B0\u2026"
title: "\u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u098F\u09B0 \u09A6\u09C8\u09B0\
  \u09CD\u0998\u09CD\u09AF \u099A\u09BF\u09B9\u09CD\u09A8\u09BF\u09A4 \u0995\u09B0\
  \u09BE"
---

{{< edit_this_page >}}

## কি এবং কেন?
একটি স্ট্রিংয়ের দৈর্ঘ্য নির্ণয় মানে হল তাতে কতগুলি অক্ষর আছে তা বের করা। প্রোগ্রামাররা ইনপুট যাচাই করা, টেক্সট ম্যানিপুলেট করা, অথবা তাদের ডাটার আকার সম্পর্কে বুঝতে এটা করে থাকেন।

## কিভাবে:
Swift এ, আপনি একটি স্ট্রিংয়ের দৈর্ঘ্য তার `count` প্রোপার্টি এক্সেস করে পেতে পারেন। সরল, চলুন এটা করি:

```Swift
let greeting = "Hello, World!"
print(greeting.count) // আউটপুট: 13
```

মনে রাখবেন যে Swift ইমোজিকে একটি একক অক্ষর হিসেবে বিবেচনা করে, ধন্যবাদ ইউনিকোডকে:

```Swift
let wave = "👋"
print(wave.count)  // আউটপুট: 1
```

## গভীর ডুব
Objective-C এর দিনগুলিতে, স্ট্রিংয়ের দৈর্ঘ্য এত সোজা ছিল না—ছিল `length` এবং `lengthOfBytes(using:)`। Swift এটাকে পরিষ্কার করেছে `count` এর মাধ্যমে।

সংযোজন অক্ষরগুলির বিষয়ে সচেতন থাকুন: যা দৃশ্যত একক অক্ষর কিন্তু মাল্টিপল ইউনিকোড স্কেলারগুলি দিয়ে তৈরি। `count` এইগুলিকে সুন্দরভাবে সামলায়।

বিকল্প? অবশ্যই, আপনি একটি লুপ দিয়ে স্ট্রিং ট্রাভার্স করতে পারেন, কিন্তু সেটা হল চাকা আবার আবিষ্কার করা এবং কম কার্যকরী।

আন্দরে, `count` হল O(n), যেখানে ‘n’ হল অক্ষরগুলির সংখ্যা। এর কারণ হল Swift’s `String` হলনা অক্ষরগুলির একটি সংগ্রহ, বরং একটি গ্রাফিম ক্লাস্টারের ক্রম, যেটি দৈর্ঘ্যে ভিন্ন হতে পারে।

## আরো দেখুন
- সুইফট ডকুমেন্টেশন টেক্সটগুলিতে: [সুইফট স্ট্রিং ডকস](https://developer.apple.com/documentation/swift/string)
- ইউনিকোড বেসিক্স: [ইউনিকোড কনসোর্টিয়াম](https://home.unicode.org)
- সুইফটের স্ট্রিং পারফরম্যান্সে গভীরে ডাইভ: [সুইফট স্ট্রিং পারফ](https://swift.org/blog/utf8-string/)
