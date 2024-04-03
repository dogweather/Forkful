---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:07:14.917012-06:00
description: "\u09A1\u09BF\u09AC\u09BE\u0997 \u0986\u0989\u099F\u09AA\u09C1\u099F\
  \ \u09AA\u09CD\u09B0\u09BF\u09A8\u09CD\u099F \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\
  \u09C7 \u0986\u09AA\u09A8\u09BE\u09B0 \u0995\u09CB\u09A1\u09C7\u09B0 \u09B8\u09BE\
  \u09A5\u09C7 \u098F\u0995\u099F\u09BF \u0995\u09A5\u09CB\u09AA\u0995\u09A5\u09A8\
  \u09C7\u09B0 \u09AE\u09A4\u09CB; \u0986\u09AA\u09A8\u09BF \u098F\u09B0 \u09B8\u09CD\
  \u09AC\u09BE\u09B8\u09CD\u09A5\u09CD\u09AF \u098F\u09AC\u0982 \u09A4\u09BE \u0995\
  \u09C0 \u09AD\u09BE\u09AC\u099B\u09C7 \u09A4\u09BE \u09A6\u09C7\u0996\u09BE\u09B0\
  \ \u099C\u09A8\u09CD\u09AF \u09AA\u09CD\u09B0\u09BF\u09A8\u09CD\u099F \u09B8\u09CD\
  \u099F\u09C7\u099F\u09AE\u09C7\u09A8\u09CD\u099F \u09AF\u09CB\u0997 \u0995\u09B0\
  \u09C7\u09A8\u0964\u2026"
lastmod: '2024-03-17T18:47:44.367896-06:00'
model: gpt-4-0125-preview
summary: "\u09A1\u09BF\u09AC\u09BE\u0997 \u0986\u0989\u099F\u09AA\u09C1\u099F \u09AA\
  \u09CD\u09B0\u09BF\u09A8\u09CD\u099F \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\u09C7\
  \ \u0986\u09AA\u09A8\u09BE\u09B0 \u0995\u09CB\u09A1\u09C7\u09B0 \u09B8\u09BE\u09A5\
  \u09C7 \u098F\u0995\u099F\u09BF \u0995\u09A5\u09CB\u09AA\u0995\u09A5\u09A8\u09C7\
  \u09B0 \u09AE\u09A4\u09CB; \u0986\u09AA\u09A8\u09BF \u098F\u09B0 \u09B8\u09CD\u09AC\
  \u09BE\u09B8\u09CD\u09A5\u09CD\u09AF \u098F\u09AC\u0982 \u09A4\u09BE \u0995\u09C0\
  \ \u09AD\u09BE\u09AC\u099B\u09C7 \u09A4\u09BE \u09A6\u09C7\u0996\u09BE\u09B0 \u099C\
  \u09A8\u09CD\u09AF \u09AA\u09CD\u09B0\u09BF\u09A8\u09CD\u099F \u09B8\u09CD\u099F\
  \u09C7\u099F\u09AE\u09C7\u09A8\u09CD\u099F \u09AF\u09CB\u0997 \u0995\u09B0\u09C7\
  \u09A8\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\
  \u09BE \u09AC\u09BE\u0997 \u0996\u09C1\u0981\u099C\u09C7 \u09AC\u09C7\u09B0 \u0995\
  \u09B0\u09A4\u09C7 \u0985\u09A5\u09AC\u09BE \u09B8\u09AC \u0995\u09BF\u099B\u09C1\
  \ \u09A0\u09BF\u0995\u09A0\u09BE\u0995 \u099A\u09B2\u099B\u09C7 \u0995\u09BF\u09A8\
  \u09BE \u09A4\u09BE \u09A8\u09BF\u09B6\u09CD\u099A\u09BF\u09A4 \u0995\u09B0\u09A4\
  \u09C7 \u098F\u099F\u09BF \u0995\u09B0\u09C7 \u09A5\u09BE\u0995\u09C7\u09A8\u2014\
  \u09AF\u09C7\u09A8 \u0986\u09AA\u09A8\u09BE\u09B0 \u0995\u09CB\u09A1\u0995\u09C7\
  \ \u098F\u0995\u099F\u09BF \u09A6\u09CD\u09B0\u09C1\u09A4 \u09AA\u09B0\u09C0\u0995\
  \u09CD\u09B7\u09BE \u0995\u09B0\u09BE\u0964."
title: "\u09A1\u09BF\u09AC\u09BE\u0997 \u0986\u0989\u099F\u09AA\u09C1\u099F \u09AA\
  \u09CD\u09B0\u09BF\u09A8\u09CD\u099F \u0995\u09B0\u09BE"
weight: 33
---

## কিভাবে:
এখানে একটি স্নিপেট দেখানো হল, যা কনসোলে একটি সাধারণ ডিবাগ বার্তা প্রিন্ট করে।

```C++
#include <iostream>

int main() {
    int lifeTheUniverseAndEverything = 42;

    // ডিবাগ বার্তা
    std::cout << "Debug: The value of lifeTheUniverseAndEverything is " 
              << lifeTheUniverseAndEverything << std::endl;

    // বাকি কোড এখানে যায়...

    return 0;
}
```

নমুনা আউটপুট:
```
Debug: The value of lifeTheUniverseAndEverything is 42
```

## গভীর ডাইভ
অনেক আগে, ডিবাগ আউটপুট শারীরিক মিডিয়াতে খোদাই করা হত। মজা নেই। এখন, আমরা কেবল `std::cout` এবং এরকম অন্যান্য টুল ব্যবহার করি। `std::cerr` ত্রুটিগুলির জন্য ব্যবহৃত হয়, প্রায়শই `std::cout`-এর সাথে ব্যবহৃত হয়। দুটি ভিন্ন স্ট্রীম কেন? এটি যেন কাজ এবং বন্ধুদের জন্য ভিন্ন চ্যাট থাকা; এটি জিনিসগুলি সাজানো রাখতে সাহায্য করে। ফ্যান্সি IDE-গুলি সমন্বিত ডিবাগার প্রদান করে, কিন্তু কখনো কখনো একটি সাধারণ প্রিন্ট বিবৃতি সামান্য ঝামেলা ছাড়াই কাজ করে। সতর্ক থাকুন, অনাবশ্যক প্রিন্টগুলি বিষয়টি ধীর করে দেয়; কল্পনা করুন কেউ তাদের নেওয়া প্রতিটি পদক্ষেপ বর্ণনা করছে। আপনি শেষ হয়ে গেলে পরিষ্কার করুন।

## দেখুন আরও
- [cppreference.com](https://en.cppreference.com/w/cpp/io/cout) - `std::cout` এবং বন্ধুদের সম্পর্কে গভীর জ্ঞান অর্জনের জন্য।
- [GNU প্রজেক্ট ডিবাগার (GDB)](https://www.gnu.org/software/gdb/) - প্রিন্টগুলি ছাড়াই একটি পূর্ণ-বিকশিত ডিবাগারে যেতে প্রস্তুত হলে।
- [Stack Overflow](https://stackoverflow.com/questions/tagged/c%2b%2b) – অন্যান্য ব্যবহারকারীরা কি সমস্যা মোকাবেলা করেছে এবং প্রিন্ট ডিবাগিং কিভাবে সাহায্য করতে পারে তা দেখতে।
