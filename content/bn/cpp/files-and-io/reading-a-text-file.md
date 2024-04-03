---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:08:11.250398-06:00
description: "\u099F\u09C7\u0995\u09CD\u09B8\u099F \u09AB\u09BE\u0987\u09B2 \u09AA\
  \u09A1\u09BC\u09BE \u09AE\u09BE\u09A8\u09C7 \u09A1\u09BF\u09B8\u09CD\u0995\u09C7\
  \u09B0 \u0989\u09AA\u09B0 \u09A5\u09BE\u0995\u09BE \u098F\u0995\u099F\u09BF \u09AB\
  \u09BE\u0987\u09B2 \u09A5\u09C7\u0995\u09C7 \u09A4\u09A5\u09CD\u09AF \u0986\u09AA\
  \u09A8\u09BE\u09B0 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09C7\
  \ \u099F\u09BE\u09A8\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\
  \u09AE\u09BE\u09B0\u09B0\u09BE \u098F\u099F\u09BF \u0995\u09B0\u09C7 \u0987\u09A8\
  \u09AA\u09C1\u099F, \u0995\u09A8\u09AB\u09BF\u0997\u09BE\u09B0\u09C7\u09B6\u09A8\
  , \u09AC\u09BE \u09A1\u09C7\u099F\u09BE \u09B8\u09CD\u099F\u09CB\u09B0\u09C7\u099C\
  \ \u09B8\u09BE\u09AE\u09B2\u09BE\u09A8\u09CB\u09B0 \u099C\u09A8\u09CD\u09AF,\u2026"
lastmod: '2024-03-17T18:47:44.382855-06:00'
model: gpt-4-0125-preview
summary: "\u099F\u09C7\u0995\u09CD\u09B8\u099F \u09AB\u09BE\u0987\u09B2 \u09AA\u09A1\
  \u09BC\u09BE \u09AE\u09BE\u09A8\u09C7 \u09A1\u09BF\u09B8\u09CD\u0995\u09C7\u09B0\
  \ \u0989\u09AA\u09B0 \u09A5\u09BE\u0995\u09BE \u098F\u0995\u099F\u09BF \u09AB\u09BE\
  \u0987\u09B2 \u09A5\u09C7\u0995\u09C7 \u09A4\u09A5\u09CD\u09AF \u0986\u09AA\u09A8\
  \u09BE\u09B0 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09C7 \u099F\
  \u09BE\u09A8\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\
  \u09B0\u09B0\u09BE \u098F\u099F\u09BF \u0995\u09B0\u09C7 \u0987\u09A8\u09AA\u09C1\
  \u099F, \u0995\u09A8\u09AB\u09BF\u0997\u09BE\u09B0\u09C7\u09B6\u09A8, \u09AC\u09BE\
  \ \u09A1\u09C7\u099F\u09BE \u09B8\u09CD\u099F\u09CB\u09B0\u09C7\u099C \u09B8\u09BE\
  \u09AE\u09B2\u09BE\u09A8\u09CB\u09B0 \u099C\u09A8\u09CD\u09AF, \u09AA\u09CD\u09B0\
  \u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09C7 \u0995\u09A0\u09BF\u09A8 \u0995\u09CB\
  \u09A1\u09BF\u0982 \u099B\u09BE\u09A1\u09BC\u09BE\u0987\u0964."
title: "\u099F\u09C7\u0995\u09CD\u09B8\u099F \u09AB\u09BE\u0987\u09B2 \u09AA\u09A1\
  \u09BC\u09BE"
weight: 22
---

## কিভাবে:
```C++
#include <iostream>
#include <fstream>
#include <string>

int main() {
    std::ifstream file("example.txt");
    std::string লাইন;

    if (file.is_open()) {
        while (getline(file, line)) {
            std::cout << line << '\n';
        }
        file.close();
    } else {
        std::cout << "Unable to open file";
    }
    
    return 0;
}
```
যদি `example.txt` ফাইলে থাকে:
```
হ্যালো, পৃথিবী!
এটি একটি টেস্ট ফাইল।
```
আউটপুট হবে:
```
হ্যালো, পৃথিবী!
এটি একটি টেস্ট ফাইল।
```

## গভীরে ডুব দেওয়া
পুরানো দিনে, ডেটা স্টোরেজ এবং পুনরুদ্ধার বেশ কঠিন ছিল। উচ্চতর প্রোগ্রামিং ভাষার আবির্ভাবের সাথে সাথে, টেক্সট ফাইল থেকে পড়ার মতো অপারেশনগুলি সহজ হয়ে উঠেছে। C++ ফাইল থেকে পড়ার জন্য বিভিন্ন উপায় অফার করে, যা স্ট্যান্ডার্ড লাইব্রেরি দ্বারা প্রদত্ত ইনপুট/আউটপুট স্ট্রিমগুলি ব্যবহার করে।

<fstream> এর বিকল্প ফাইল I/O এর জন্য পুরনো C ফাংশন (যেমন fopen, fgets, ইত্যাদি), অপারেটিং সিস্টেম-বিশেষ এপিআই, অথবা অন্যান্য লাইব্রেরি রয়েছে যা নিম্নস্তরের বিস্তারিত হিসেবে কিছু সরলিকরণ করে।

আমরা যখন বাস্তবায়নের বিস্তারিত সম্পর্কে কথা বলি, তখন জানা দরকার যে `std::ifstream` হল একটি ক্লাস যা ইনপুট ফাইল স্ট্রিম পরিচালনা করে। মূল ফাংশনগুলি হল `is_open()` যা পরীক্ষা করে ফাইল স্ট্রিমটি সফলভাবে খোলা হয়েছে কিনা, `getline()` যা ফাইলটি লাইন অনুযায়ী পড়ে, এবং `close()` যা ফাইল স্ট্রিমটি বন্ধ করে। ফাইল সম্পদগুলি সঠিকভাবে পরিচালনা করা জরুরি তথ্য বিকৃতি বা ডেটা ফাঁস এড়ানোর জন্য। সৌভাগ্যক্রমে, আধুনিক C++ (C++11 এবং পরবর্তী) বস্তুর জীবনকালের মাধ্যমে সম্পদ ব্যবস্থাপনাকে আরও নিরাপদে সামাল দেওয়ার মতো বৈশিষ্ট্য অন্তর্ভুক্ত করে।

## আরো দেখুন
- [cppreference.com - ইনপুট/আউটপুট লাইব্রেরি](https://en.cppreference.com/w/cpp/io)
- স্ট্যাক ওভারফ্লো: [C++ এ আমি কিভাবে CSV ফাইল পড়তে এবং পার্স করতে পারি?](https://stackoverflow.com/questions/1120140/how-can-i-read-and-parse-csv-files-in-c)
