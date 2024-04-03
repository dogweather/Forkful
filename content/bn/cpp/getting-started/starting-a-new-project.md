---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:20:10.630903-06:00
description: "\u098F\u0995\u099F\u09BF \u09A8\u09A4\u09C1\u09A8 \u09AA\u09CD\u09B0\
  \u099C\u09C7\u0995\u09CD\u099F \u09B6\u09C1\u09B0\u09C1 \u0995\u09B0\u09BE \u09AE\
  \u09BE\u09A8\u09C7 \u0986\u09AA\u09A8\u09BE\u09B0 \u0995\u09CB\u09A1\u09AC\u09C7\
  \u09B8\u09C7\u09B0 \u099C\u09A8\u09CD\u09AF \u09AD\u09BF\u09A4\u09CD\u09A4\u09BF\
  \ \u09A4\u09C8\u09B0\u09BF \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\
  \u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u098F\u099F\u09BF \u0995\u09B0\
  \u09C7 \u0989\u09A8\u09CD\u09A8\u09DF\u09A8 \u09AA\u09CD\u09B0\u0995\u09CD\u09B0\
  \u09BF\u09DF\u09BE\u0995\u09C7 \u09A4\u09CD\u09AC\u09B0\u09BE\u09A8\u09CD\u09AC\u09BF\
  \u09A4 \u0995\u09B0\u09A4\u09C7, \u09AA\u09CD\u09B0\u099C\u09C7\u0995\u09CD\u099F\
  \u09C7\u09B0 \u0997\u09A0\u09A8\u0995\u09C7 \u09A8\u09BF\u09B0\u09CD\u09A6\u09C7\
  \u09B6\u2026"
lastmod: '2024-03-17T18:47:44.365999-06:00'
model: gpt-4-0125-preview
summary: "\u098F\u0995\u099F\u09BF \u09A8\u09A4\u09C1\u09A8 \u09AA\u09CD\u09B0\u099C\
  \u09C7\u0995\u09CD\u099F \u09B6\u09C1\u09B0\u09C1 \u0995\u09B0\u09BE \u09AE\u09BE\
  \u09A8\u09C7 \u0986\u09AA\u09A8\u09BE\u09B0 \u0995\u09CB\u09A1\u09AC\u09C7\u09B8\
  \u09C7\u09B0 \u099C\u09A8\u09CD\u09AF \u09AD\u09BF\u09A4\u09CD\u09A4\u09BF \u09A4\
  \u09C8\u09B0\u09BF \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\
  \u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u098F\u099F\u09BF \u0995\u09B0\u09C7\
  \ \u0989\u09A8\u09CD\u09A8\u09DF\u09A8 \u09AA\u09CD\u09B0\u0995\u09CD\u09B0\u09BF\
  \u09DF\u09BE\u0995\u09C7 \u09A4\u09CD\u09AC\u09B0\u09BE\u09A8\u09CD\u09AC\u09BF\u09A4\
  \ \u0995\u09B0\u09A4\u09C7, \u09AA\u09CD\u09B0\u099C\u09C7\u0995\u09CD\u099F\u09C7\
  \u09B0 \u0997\u09A0\u09A8\u0995\u09C7 \u09A8\u09BF\u09B0\u09CD\u09A6\u09C7\u09B6\
  \ \u0995\u09B0\u09A4\u09C7, \u098F\u09AC\u0982 \u09AD\u09AC\u09BF\u09B7\u09CD\u09AF\
  \u09A4\u09C7\u09B0 \u0995\u09CB\u09A1\u09C7\u09B0 \u099C\u09A8\u09CD\u09AF \u09AE\
  \u09C2\u09B2 \u09AD\u09C2\u09AE\u09BF\u0995\u09BE \u09B0\u09BE\u0996\u09A4\u09C7\
  \u0964."
title: "\u09A8\u09A4\u09C1\u09A8 \u09AA\u09CD\u09B0\u0995\u09B2\u09CD\u09AA \u09B6\
  \u09C1\u09B0\u09C1 \u0995\u09B0\u09BE"
weight: 1
---

## কীভাবে:
শুরু করার সময়, আপনার বিল্ড সিস্টেম অথবা IDE চয়ন করুন। সহজতার জন্য, আমরা একটি বেসিক টেক্সট এডিটর এবং g++ ব্যবহার করবো। দুটি ফাইল তৈরি করুন: `main.cpp` এবং একটি `Makefile`।

`main.cpp`:
```C++
#include <iostream>

int main() {
    std::cout << "Hello, new project!" << std::endl;
    return 0;
}
```

`Makefile`:
```make
all:
    g++ main.cpp -o my_project

clean:
    rm my_project
```

কম্পাইল করতে, টার্মিনালে `make` চালান। পরিষ্কার করতে, `make clean` চালান।

`./my_project` চালানোর পরে নমুনা আউটপুট:
```
Hello, new project!
```

## গভীর ডুব
ঐতিহাসিকভাবে, একটি নতুন C++ প্রজেক্ট সেট আপ করা একটি বেশি ম্যানুয়াল প্রক্রিয়া ছিল। আজকাল, IDEগুলি টেমপ্লেট জেনারেট করতে পারে। CMake অথবা Meson মতো বিকল্পগুলি বিল্ডগুলি পরিচালনা করতে সাহায্য করে। এই সরঞ্জামগুলোর আগে, ডেভলপাররা হাতে হাতে Makefile লিখতেন, প্রত্যেকটি `.cpp` ফাইলকে অবজেক্ট ফাইলে কম্পাইল করে এবং তাদেরকে লিঙ্ক করতেন।

বিকল্পগুলি বিবেচনা করে: নতুন বিল্ড সিস্টেমগুলি প্রক্রিয়াটিকে সহজিকরণ করে। উদাহরণস্বরূপ, CMake আপনার Makefileগুলো স্বয়ংক্রিয়ভাবে জেনারেট করে, যা এটিকে প্ল্যাটফর্ম-স্বাধীন করে তোলে।

বাস্তবায়নের দিক থেকে, সেটআপটি প্রজেক্টের আকার এবং নির্ভরতার মতো ফ্যাক্টরগুলির উপর নির্ভর করে। বড় প্রজেক্টগুলির জন্য আরো জটিল কাঠামো দাবি করে, যেখানে সোর্স ফাইল, হেডারগুলি, এবং টেস্টগুলির জন্য পৃথক ফোল্ডার থাকে।

## আরও দেখুন
- [CMake ডকুমেন্টেশন](https://cmake.org/documentation/)
- [C++ কোর গাইডলাইনস](https://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines)
- [GCC, দ্য জিএনইউ কম্পাইলার কালেকশন](https://gcc.gnu.org/)
