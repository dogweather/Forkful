---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:38:40.872574-06:00
description: "\u099C\u099F\u09BF\u09B2 \u09B8\u0982\u0996\u09CD\u09AF\u09BE, \u09AF\
  \u09BE \u09AC\u09BE\u09B8\u09CD\u09A4\u09AC \u098F\u09AC\u0982 \u0995\u09BE\u09B2\
  \u09CD\u09AA\u09A8\u09BF\u0995 \u098F\u0995\u0995\u09C7\u09B0 \u09B8\u09AE\u09A8\
  \u09CD\u09AC\u09AF\u09BC\u09C7 \u09AA\u09CD\u09B0\u0995\u09BE\u09B6\u09BF\u09A4\
  \ (\u09AF\u09C7\u09AE\u09A8, 3 + 4i), \u0987\u099E\u09CD\u099C\u09BF\u09A8\u09BF\
  \u09AF\u09BC\u09BE\u09B0\u09BF\u0982, \u09AA\u09A6\u09BE\u09B0\u09CD\u09A5\u09AC\
  \u09BF\u099C\u09CD\u099E\u09BE\u09A8, \u098F\u09AC\u0982 \u09AA\u09CD\u09B0\u09AF\
  \u09BC\u09CB\u0997\u09AE\u09C2\u09B2\u0995 \u0997\u09A3\u09BF\u09A4\u09C7 \u09A8\
  \u09BE\u09A8\u09BE \u0997\u09A3\u09A8\u09BE \u09B8\u09AE\u09B8\u09CD\u09AF\u09BE\
  \u09A4\u09C7 \u09AE\u09CC\u09B2\u09BF\u0995\u0964\u2026"
lastmod: '2024-03-17T18:47:43.517344-06:00'
model: gpt-4-0125-preview
summary: "\u099C\u099F\u09BF\u09B2 \u09B8\u0982\u0996\u09CD\u09AF\u09BE, \u09AF\u09BE\
  \ \u09AC\u09BE\u09B8\u09CD\u09A4\u09AC \u098F\u09AC\u0982 \u0995\u09BE\u09B2\u09CD\
  \u09AA\u09A8\u09BF\u0995 \u098F\u0995\u0995\u09C7\u09B0 \u09B8\u09AE\u09A8\u09CD\
  \u09AC\u09AF\u09BC\u09C7 \u09AA\u09CD\u09B0\u0995\u09BE\u09B6\u09BF\u09A4 (\u09AF\
  \u09C7\u09AE\u09A8, 3 + 4i), \u0987\u099E\u09CD\u099C\u09BF\u09A8\u09BF\u09AF\u09BC\
  \u09BE\u09B0\u09BF\u0982, \u09AA\u09A6\u09BE\u09B0\u09CD\u09A5\u09AC\u09BF\u099C\
  \u09CD\u099E\u09BE\u09A8, \u098F\u09AC\u0982 \u09AA\u09CD\u09B0\u09AF\u09BC\u09CB\
  \u0997\u09AE\u09C2\u09B2\u0995 \u0997\u09A3\u09BF\u09A4\u09C7 \u09A8\u09BE\u09A8\
  \u09BE \u0997\u09A3\u09A8\u09BE \u09B8\u09AE\u09B8\u09CD\u09AF\u09BE\u09A4\u09C7\
  \ \u09AE\u09CC\u09B2\u09BF\u0995\u0964\u2026"
title: "\u099C\u099F\u09BF\u09B2 \u09B8\u0982\u0996\u09CD\u09AF\u09BE\u09B0 \u09B8\
  \u09BE\u09A5\u09C7 \u0995\u09BE\u099C \u0995\u09B0\u09BE"
---

{{< edit_this_page >}}

## কি এবং কেন?
জটিল সংখ্যা, যা বাস্তব এবং কাল্পনিক এককের সমন্বয়ে প্রকাশিত (যেমন, 3 + 4i), ইঞ্জিনিয়ারিং, পদার্থবিজ্ঞান, এবং প্রয়োগমূলক গণিতে নানা গণনা সমস্যাতে মৌলিক। Google Apps Script-এ এই সংখ্যাগুলি নিয়ে কাজ করা শিখলে প্রোগ্রামাররা তাদের ক্ষমতা বিজ্ঞানভিত্তিক গণনা, সিগন্যাল প্রসেসিং, এবং তার বাইরে প্রসারিত করতে পারেন।

## কিভাবে:
Google Apps Script জটিল সংখ্যা সমর্থন করে না, যার ফলে কাস্টম ফাংশনালিটি বাস্তবায়ন প্রয়োজন। নিচে জটিল সংখ্যা সম্পর্কে যোগ, বিয়োগ, এবং গুণ সম্পাদনের জন্য একটি মৌলিক কাঠামো দেওয়া হলো।

```javascript
// জটিল সংখ্যার জন্য একটি কন্সট্রাক্টর সংজ্ঞায়িত করুন
function Complex(real, imag) {
  this.real = real;
  this.imag = imag;
}

// দুটি জটিল সংখ্যা যোগ করার মেথড
Complex.prototype.add = function(other) {
  return new Complex(this.real + other.real, this.imag + other.imag);
};

// দুটি জটিল সংখ্যা বিয়োগ করার মেথড
Complex.prototype.subtract = function(other) {
  return new Complex(this.real - other.real, this.imag - other.imag);
};

// দুটি জটিল সংখ্যা গুণ করার মেথড
Complex.prototype.multiply = function(other) {
  return new Complex(
    this.real * other.real - this.imag * other.imag,
    this.real * other.imag + this.imag * other.real
  );
};

// উদাহরণ ব্যবহার
var num1 = new Complex(3, 4);
var num2 = new Complex(1, 2);

// দুটি জটিল সংখ্যা যোগ
var sum = num1.add(num2);
console.log(`Sum: ${sum.real} + ${sum.imag}i`); // Sum: 4 + 6i

// দুটি জটিল সংখ্যা বিয়োগ
var difference = num1.subtract(num2);
console.log(`Difference: ${difference.real} + ${difference.imag}i`); // Difference: 2 + 2i

// দুটি জটিল সংখ্যা গুণ
var product = num1.multiply(num2);
console.log(`Product: ${product.real} + ${product.imag}i`); // Product: -5 + 10i
```

## গভীর ডুব:
জটিল সংখ্যার ধারণা ১৬তম শতাব্দীতে ফিরে গেলেও, এটি ইউলার এবং গাউসের মত গণিতবিদদের কাজ যা তাদের গণিতে একটি স্থায়ী স্থান দিয়েছে। তাদের উপযোগিতা সত্ত্বেও, জাভাস্ক্রিপ্ট বা Google Apps Script-এ সরাসরি জটিল সংখ্যা সমর্থন করা হয় না। সরাসরি সমর্থনের অভাব মানে জটিল সংখ্যার উপর অপারেশনগুলি ম্যানুয়ালি বাস্তবায়ন করতে হবে, যেমন দেখানো হয়েছে। যদিও এটি একটি ভাল শিক্ষা সুযোগ এবং মৌলিক প্রয়োজনের জন্য যথেষ্ট ফাংশনালিটি প্রদান করে, জটিল সংখ্যাগুলির উপর ভারী গণনা কাজের জন্য, কেউ গণিতিক গণনার জন্য আরও উপযুক্ত প্রোগ্রামিং পরিবেশের দিকে ঝুঁকতে পারে, যেমন Python সহ NumPy, যা জটিল সংখ্যা সমালোচনার জন্য অন্তর্নির্মিত, অত্যন্ত অপ্টিমাইজড অপারেশন অফার করে। তবে, Google Apps Script-এ মৌলিক অপারেশন বুঝতে এবং বাস্তবায়ন করা একটি বিস্তৃত প্রেক্ষাপটে তাদের প্রোগ্রামিং দক্ষতা বাড়ানো এবং প্রয়োগ করার জন্য একটি উপযোগী অনুশীলন।
