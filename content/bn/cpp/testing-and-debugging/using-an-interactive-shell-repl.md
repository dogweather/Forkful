---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:23:15.537987-06:00
description: "\u098F\u0995\u099F\u09BF REPL (Read-Eval-Print-Loop) \u09B9\u09B2 \u098F\
  \u0995\u099F\u09BF \u09B8\u09BE\u09A7\u09BE\u09B0\u09A3, \u0987\u09A8\u09CD\u099F\
  \u09BE\u09B0\u200C\u09CD\u09AF\u09BE\u0995\u09CD\u099F\u09BF\u09AD \u09AA\u09CD\u09B0\
  \u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BF\u0982 \u09AA\u09B0\u09BF\u09AC\u09C7\u09B6\
  \u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE\
  \ \u098F\u099F\u09BF \u09AC\u09CD\u09AF\u09AC\u09B9\u09BE\u09B0 \u0995\u09B0\u09C7\
  \u09A8 \u09AC\u09BE\u09B8\u09CD\u09A4\u09AC \u09B8\u09AE\u09AF\u09BC\u09C7 \u09AD\
  \u09BE\u09B7\u09BE\u0997\u09A4 \u09AA\u09B0\u09C0\u0995\u09CD\u09B7\u09BE-\u09A8\
  \u09BF\u09B0\u09C0\u0995\u09CD\u09B7\u09BE,\u2026"
lastmod: '2024-03-17T18:47:44.366942-06:00'
model: gpt-4-0125-preview
summary: "\u098F\u0995\u099F\u09BF REPL (Read-Eval-Print-Loop) \u09B9\u09B2 \u098F\
  \u0995\u099F\u09BF \u09B8\u09BE\u09A7\u09BE\u09B0\u09A3, \u0987\u09A8\u09CD\u099F\
  \u09BE\u09B0\u200C\u09CD\u09AF\u09BE\u0995\u09CD\u099F\u09BF\u09AD \u09AA\u09CD\u09B0\
  \u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BF\u0982 \u09AA\u09B0\u09BF\u09AC\u09C7\u09B6\
  \u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE\
  \ \u098F\u099F\u09BF \u09AC\u09CD\u09AF\u09AC\u09B9\u09BE\u09B0 \u0995\u09B0\u09C7\
  \u09A8 \u09AC\u09BE\u09B8\u09CD\u09A4\u09AC \u09B8\u09AE\u09AF\u09BC\u09C7 \u09AD\
  \u09BE\u09B7\u09BE\u0997\u09A4 \u09AA\u09B0\u09C0\u0995\u09CD\u09B7\u09BE-\u09A8\
  \u09BF\u09B0\u09C0\u0995\u09CD\u09B7\u09BE, \u09A6\u09CD\u09B0\u09C1\u09A4 \u0995\
  \u09B0\u09CD\u09AE, \u0985\u09A5\u09AC\u09BE \u09AA\u09C2\u09B0\u09CD\u09A3\u09BE\
  \u0999\u09CD\u0997 \u0985\u09CD\u09AF\u09BE\u09AA\u09CD\u09B2\u09BF\u0995\u09C7\u09B6\
  \u09A8 \u09A4\u09C8\u09B0\u09BF\u09B0 \u0985\u09A4\u09BF\u09B0\u09BF\u0995\u09CD\
  \u09A4 \u09AC\u09CB\u099D\u09BE \u099B\u09BE\u09A1\u09BC\u09BE\u0987 \u09A8\u09A4\
  \u09C1\u09A8 \u09A7\u09BE\u09B0\u09A3\u09BE\u0997\u09C1\u09B2\u09BF \u09AC\u09CB\
  \u099D\u09BE\u09B0 \u099C\u09A8\u09CD\u09AF\u0964."
title: "\u0987\u09A8\u09CD\u099F\u09BE\u09B0\u09AF\u09BC\u09BE\u0995\u09CD\u099F\u09BF\
  \u09AD \u09B6\u09C7\u09B2 (REPL) \u09AC\u09CD\u09AF\u09AC\u09B9\u09BE\u09B0 \u0995\
  \u09B0\u09BE"
weight: 34
---

## কিভাবে:
C++ সাথে নির্মিত কোন REPL নেই, তবে ক্লিং এর মতো টুলস সেই ক্ষমতা প্রদান করে। এখানে দুটি সংখ্যার যোগফল হিসাব করার জন্য ক্লিং ব্যবহার করার উপায় দেখানো হল:

```C++
#include <iostream>

int main() {
    int a = 5;
    int b = 7;
    std::cout << "The sum is: " << a + b << std::endl;
    return 0;
}

// আউটপুট:
// The sum is: 12
```

ক্লিং শুরু করুন এবং প্রতিটি কোড লাইন আস্তে আস্তে লিখুন, প্রতিটি কমান্ডের পরে আউটপুট লক্ষ্য করে দেখুন। এটি তাৎক্ষণিক প্রতিক্রিয়া, কম্পাইল ছাড়াই।

## গভীর ডুব
REPLs পাইথন অথবা লিস্পের মতো ভাষাগুলির জন্য সাধারণ, এবং এগুলি ১৯৬০ সাল থেকেই আছে। C++ এর মতো একটি সংকলিত ভাষার জন্য ধারণাটি স্বাভাবিকভাবে মেলে না, যা ক্লিং এর মতো টুলস থাকার কারণ। এর বিকল্পগুলি অনলাইন কম্পাইলার অথবা প্রথাগতভাবে সংকলিত ছোট পরিসরের পরীক্ষামূলক প্রোগ্রাম অন্তর্ভুক্ত। ক্লিং LLVM এবং Clang এর উপর নির্মিত, C++ কে ব্যাখ্যা মোডে ব্যবহারের জন্য একটি সেতু প্রদান করে।

## আরও দেখুন
- [ক্লিং](https://root.cern/cling/): একটি ইন্টার‌্যাক্টিভ C++ ইন্টারপ্রেটার, LLVM এবং Clang লাইব্রেরির উপরে নির্মিত।
- [জুপিটার নোটবুক](https://jupyter.org/): একটি নোটবুক পরিবেশের মধ্যে একটি ইন্টার‌্যাক্টিভ শেল অফার করে, C++ সাপোর্ট করে xeus-cling কার্নেলের মাধ্যমে।
- [LLVM](https://llvm.org/): মডুলার এবং পুনঃব্যবহারযোগ্য কম্পাইলার এবং টুলচেইন প্রযুক্তিগুলির একটি সংগ্রহ, যার উপর ক্লিং নির্মিত।
