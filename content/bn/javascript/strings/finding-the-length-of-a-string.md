---
changelog:
- 2024-03-17, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-17 17:48:18.194006-06:00
description: "\u098F\u0995\u099F\u09BF \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982\u09DF\
  \u09C7\u09B0 \u09A6\u09C8\u09B0\u09CD\u0998\u09CD\u09AF \u0985\u09B0\u09CD\u09A5\
  \u09BE\u09CE \u098F\u09B0 \u0985\u0995\u09CD\u09B7\u09B0\u0997\u09C1\u09B2\u09BF\
  \ \u0997\u09A3\u09A8\u09BE \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\
  \u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u09A4\u09BE\u09A6\u09C7\u09B0\
  \ \u0987\u09A8\u09AA\u09C1\u099F \u09AF\u09BE\u099A\u09BE\u0987 \u0995\u09B0\u09A4\
  \u09C7, \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u098F\u09B0 \u09AE\u09A7\u09CD\
  \u09AF \u09A6\u09BF\u09DF\u09C7 \u09B2\u09C1\u09AA \u0995\u09B0\u09A4\u09C7 \u098F\
  \u09AC\u0982 \u099F\u09C7\u0995\u09CD\u09B8\u099F \u09A1\u09BE\u099F\u09BE \u09A6\
  \u0995\u09CD\u09B7\u09A4\u09BE\u09B0 \u09B8\u09BE\u09A5\u09C7\u2026"
lastmod: '2024-03-17T18:47:44.443686-06:00'
model: gpt-4-0125-preview
summary: "\u098F\u0995\u099F\u09BF \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982\u09DF\
  \u09C7\u09B0 \u09A6\u09C8\u09B0\u09CD\u0998\u09CD\u09AF \u0985\u09B0\u09CD\u09A5\
  \u09BE\u09CE \u098F\u09B0 \u0985\u0995\u09CD\u09B7\u09B0\u0997\u09C1\u09B2\u09BF\
  \ \u0997\u09A3\u09A8\u09BE \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\
  \u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u09A4\u09BE\u09A6\u09C7\u09B0\
  \ \u0987\u09A8\u09AA\u09C1\u099F \u09AF\u09BE\u099A\u09BE\u0987 \u0995\u09B0\u09A4\
  \u09C7, \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u098F\u09B0 \u09AE\u09A7\u09CD\
  \u09AF \u09A6\u09BF\u09DF\u09C7 \u09B2\u09C1\u09AA \u0995\u09B0\u09A4\u09C7 \u098F\
  \u09AC\u0982 \u099F\u09C7\u0995\u09CD\u09B8\u099F \u09A1\u09BE\u099F\u09BE \u09A6\
  \u0995\u09CD\u09B7\u09A4\u09BE\u09B0 \u09B8\u09BE\u09A5\u09C7 \u09AA\u09B0\u09BF\
  \u099A\u09BE\u09B2\u09A8\u09BE \u0995\u09B0\u09A4\u09C7 \u098F\u099F\u09BF \u0995\
  \u09B0\u09C7 \u09A5\u09BE\u0995\u09C7\u09A8\u0964."
title: "\u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u098F\u09B0 \u09A6\u09C8\u09B0\
  \u09CD\u0998\u09CD\u09AF \u099A\u09BF\u09B9\u09CD\u09A8\u09BF\u09A4 \u0995\u09B0\
  \u09BE"
weight: 7
---

## কিভাবে:
জাভাস্ক্রিপ্ট এ সাধারণ ভাবে `.length` প্রপার্টির মাধ্যমে এটি সম্পাদন করা যায়।

```javascript
let greeting = 'Hello, World!';
console.log(greeting.length); // আউটপুট: 13
```

একটি খালি স্ট্রিং এর মান হল শূন্য:

```javascript
let empty = '';
console.log(empty.length); // আউটপুট: 0
```

এমনকি স্পেসগুলিও গণনা করা হয়:

```javascript
let spaces = '   ';
console.log(spaces.length); // আউটপুট: 3
```

## গভীর ডাইভ
`.length` প্রপার্টি জাভাস্ক্রিপ্টের প্রারম্ভিক দিন থেকে আছে। এটি দ্রুত, কারণ এটি আসলে একটি ফাংশন নয়, বরং একটি ইন্সটেন্স প্রপার্টি যা স্ট্রিং অবজেক্টের সাথে সংরক্ষিত থাকে।

প্রতিটি অক্ষর ম্যানুয়ালি লুপ করে গণনা করার মতো বিকল্প পদ্ধতি আছে, কিন্তু তা লিফটের পরিবর্তে সিঁড়ি ব্যবহার করার মতো - শুধুমাত্র যখন প্রয়োজন তখনই ব্যবহার করুন।

জাভাস্ক্রিপ্টে স্ট্রিংগুলিকে অপরিবর্তনীয় হিসেবে বিবেচনা করা হয়, অর্থাৎ `.length` পরিবর্তন হয় না যদি না আপনি ভেরিয়েবলে একটি নতুন স্ট্রিং অ্যাসাইন না করেন। দৈর্ঘ্য স্ট্রিং তৈরির সময়ে গণনা করা হয়।

বাস্তবায়নের দিক থেকে, ইউনিকোডের কথা মনে রাখবেন। জাভাস্ক্রিপ্টের UTF-16 এনকোডিংয়ে কিছু অক্ষর (যেমন ইমোজি বা কিছু ভাষার বর্ণমালা) দুই বা ততোধিক কোড ইউনিট দ্বারা প্রতিনিধিত্ব করা হতে পারে:

```javascript
let smiley = '😊';
console.log(smiley.length); // আউটপুট: 2
```

এমনকি একটি অক্ষরের মতো দেখালেও, কিছুটা দৈর্ঘ্যের হিসাবে দুই হিসেবে গণনা করা হতে পারে কারণ এগুলি কিভাবে এনকোড করা হয়েছে। বিভিন্ন অক্ষর সেট নিয়ে কাজ করলে এটি মনে রাখা জরুরি!

## আরও দেখুন
- [MDN ওয়েব ডক্স - String.length](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length)
- [Unicode এবং জাভাস্ক্রিপ্ট স্ট্রিংস](https://mathiasbynens.be/notes/javascript-unicode)
- [জাভাস্ক্রিপ্ট স্ট্রিং এবং অক্ষর এনকোডিংস](https://flaviocopes.com/javascript-unicode/)
