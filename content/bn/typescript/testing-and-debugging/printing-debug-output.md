---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:08:08.453916-06:00
description: "\u09A1\u09BF\u09AC\u09BE\u0997 \u0986\u0989\u099F\u09AA\u09C1\u099F\
  \ \u09B9\u099A\u09CD\u099B\u09C7 \u0985\u09A8\u09CD\u09A7\u0995\u09BE\u09B0 \u0995\
  \u09CB\u09A1\u09C7\u09B0 \u0997\u09B2\u09BF \u09AE\u09BE\u099D\u09C7 \u0986\u09AA\
  \u09A8\u09BE\u09B0 \u09AC\u09BE\u09A4\u09BF; \u098F\u099F\u09BF \u09B0\u09BE\u09A8\
  \u099F\u09BE\u0987\u09AE\u09C7 \u0986\u09AA\u09A8\u09BE\u09B0 \u0995\u09CB\u09A1\
  \ \u0995\u09BF \u0995\u09B0\u099B\u09C7 \u09A4\u09BE \u09A6\u09C7\u0996\u09C7 \u09A4\
  \u09CD\u09B0\u09C1\u099F\u09BF \u0996\u09C1\u0981\u099C\u09C7 \u09AC\u09C7\u09B0\
  \ \u0995\u09B0\u09BE\u09DF \u0986\u09AA\u09A8\u09BE\u0995\u09C7 \u09B8\u09B9\u09BE\
  \u09AF\u09BC\u09A4\u09BE \u0995\u09B0\u09C7\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\
  \u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u098F\u099F\u09BE\u2026"
lastmod: '2024-03-17T18:47:43.767719-06:00'
model: gpt-4-0125-preview
summary: "\u09A1\u09BF\u09AC\u09BE\u0997 \u0986\u0989\u099F\u09AA\u09C1\u099F \u09B9\
  \u099A\u09CD\u099B\u09C7 \u0985\u09A8\u09CD\u09A7\u0995\u09BE\u09B0 \u0995\u09CB\
  \u09A1\u09C7\u09B0 \u0997\u09B2\u09BF \u09AE\u09BE\u099D\u09C7 \u0986\u09AA\u09A8\
  \u09BE\u09B0 \u09AC\u09BE\u09A4\u09BF; \u098F\u099F\u09BF \u09B0\u09BE\u09A8\u099F\
  \u09BE\u0987\u09AE\u09C7 \u0986\u09AA\u09A8\u09BE\u09B0 \u0995\u09CB\u09A1 \u0995\
  \u09BF \u0995\u09B0\u099B\u09C7 \u09A4\u09BE \u09A6\u09C7\u0996\u09C7 \u09A4\u09CD\
  \u09B0\u09C1\u099F\u09BF \u0996\u09C1\u0981\u099C\u09C7 \u09AC\u09C7\u09B0 \u0995\
  \u09B0\u09BE\u09DF \u0986\u09AA\u09A8\u09BE\u0995\u09C7 \u09B8\u09B9\u09BE\u09AF\
  \u09BC\u09A4\u09BE \u0995\u09B0\u09C7\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\
  \u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u098F\u099F\u09BE \u0995\u09B0\u09C7\
  \ \u0995\u09BE\u09B0\u09A3, \u09AD\u09BE\u09B2, \u0986\u09AE\u09B0\u09BE \u09AE\u09BE\
  \u09A8\u09C1\u09B7 \u098F\u09AC\u0982 \u0986\u09AE\u09BE\u09A6\u09C7\u09B0 \u0995\
  \u09CB\u09A1 \u09AA\u09CD\u09B0\u09A5\u09AE \u09AA\u09CD\u09B0\u09AF\u09BC\u09BE\
  \u09B8\u09C7 \u09B8\u09AC\u09B8\u09AE\u09AF\u09BC \u09A8\u09BF\u09B0\u09CD\u09AD\
  \u09C1\u09B2 \u09B9\u09AF\u09BC \u09A8\u09BE\u0964."
title: "\u09A1\u09BF\u09AC\u09BE\u0997 \u0986\u0989\u099F\u09AA\u09C1\u099F \u09AA\
  \u09CD\u09B0\u09BF\u09A8\u09CD\u099F \u0995\u09B0\u09BE"
weight: 33
---

## কিভাবে:
TypeScript-এ ডিবাগ আউটপুট প্রিন্ট করতে চান? কনসোল মেথডগুলি আপনার পছন্দের হতে পারে। `console.log`, `console.error`, এবং বন্ধুদের কাজে লাগান:

```TypeScript
// বেসিক লগ
console.log('লুক মা, আমি ডিবাগ করছি!');

// গ্রুপড লগ
console.group('ব্যবহারকারীর বিবরণ');
console.log('নাম: জন ডো');
console.log('বয়স: ৩৪');
console.groupEnd();

// টেবিল
console.table([{ a: 1, b: 'Y' }, { a: 'Z', b: 2 }]);

// এরর আউটপুট
console.error('ওপস! কিছু ভুল হয়ে গেছে।');

// ওয়ার্নিং আউটপুট
console.warn('এটি একটি সতর্কতা।');

// একটি ডিবাগ আউটপুট
console.debug('এটি একটি ডিবাগ বার্তা।');
```

নমুনা আউটপুটগুলি:
```
লুক মা, আমি ডিবাগ করছি!
ব্যবহারকারীর বিবরণ
    নাম: জন ডো
    বয়স: ৩৪
(index) এ  বি
0       1  "Y"
1       "Z" 2
ওপস! কিছু ভুল হয়ে গেছে।
এটি একটি সতর্কতা।
এটি একটি ডিবাগ বার্তা।
```

## গভীরে ডুব দেয়া
অতীতে, আমরা `alert()` পেতাম – এটি আপনার মুখে এবং না সামলানো পর্যন্ত কাজ আটকে দিত। এখন, `console` মেথডস রাজত্ব করে। এগুলি কম বিরক্তিকর এবং বার্তা শ্রেণীবদ্ধ করা, টেবিল প্রিন্ট করা, বা আউটপুটগুলি স্টাইল করার মত সুপারপাওয়ার নিয়ে আসে।

বিকল্প? অবশ্যই। আপনি একটি ফাইলে লিখতে পারেন বা দূরবর্তী লগিং এর জন্য নেটওয়ার্ক জুড়ে বার্তা পাঠাতে পারেন। ব্রাউজারের জন্য, ক্রোমের ডেভটুলসের মত টুলস আপনাকে আপনার লগ স্তর এবং ফর্ম্যাটের উপর আরও নিয়ন্ত্রণ দেয়।

বাস্তবায়ন-ভিত্তিক, `console` TypeScript-এ রানটাইমে JavaScript এ হয়ে যায়, এবং সব আসল কাজ সেখানেই হয়। এখানে ফ্যান্সি TypeScript টাইপগুলি খেলাটি পরিবর্তন করে না—এটি ব্রাউজার বা Node-এর নিচে প্রাথমিক বৃত্তাকার `console`।

## আরও দেখুন
- [MDN ওয়েব ডক্স অন কনসোল](https://developer.mozilla.org/en-US/docs/Web/API/Console)
- [Node.js কনসোল ডকুমেন্টেশন](https://nodejs.org/api/console.html)
- [TypeScript হ্যান্ডবুক](https://www.typescriptlang.org/docs/handbook/intro.html)
