---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:39:33.057313-06:00
description: "\u099C\u099F\u09BF\u09B2 \u09B8\u0982\u0996\u09CD\u09AF\u09BE\u0997\u09C1\
  \u09B2\u09CB\u09B0 \u0986\u09B8\u09B2 \u0985\u0982\u09B6 \u098F\u09AC\u0982 \u0995\
  \u09BE\u09B2\u09CD\u09AA\u09A8\u09BF\u0995 \u0985\u0982\u09B6 \u09A5\u09BE\u0995\
  \u09C7 \u098F\u09AC\u0982 \u098F\u0987 \u09B8\u0982\u0996\u09CD\u09AF\u09BE\u0997\
  \u09C1\u09B2\u09CB \u09AA\u09CD\u09B0\u0995\u09CC\u09B6\u09B2, \u09AA\u09A6\u09BE\
  \u09B0\u09CD\u09A5\u09AC\u09BF\u09A6\u09CD\u09AF\u09BE \u098F\u09AC\u0982 \u0995\
  \u09AE\u09CD\u09AA\u09BF\u0989\u099F\u09BE\u09B0 \u0997\u09CD\u09B0\u09BE\u09AB\u09BF\
  \u0995\u09CD\u09B8\u09C7\u09B0 \u09AE\u09A4 \u09AC\u09BF\u09AD\u09BF\u09A8\u09CD\
  \u09A8 \u0995\u09CD\u09B7\u09C7\u09A4\u09CD\u09B0\u09C7 \u0996\u09C1\u09AC\u0987\
  \ \u099C\u09B0\u09C1\u09B0\u09C0\u0964\u2026"
lastmod: '2024-03-17T18:47:43.802856-06:00'
model: gpt-4-0125-preview
summary: "\u099C\u099F\u09BF\u09B2 \u09B8\u0982\u0996\u09CD\u09AF\u09BE\u0997\u09C1\
  \u09B2\u09CB\u09B0 \u0986\u09B8\u09B2 \u0985\u0982\u09B6 \u098F\u09AC\u0982 \u0995\
  \u09BE\u09B2\u09CD\u09AA\u09A8\u09BF\u0995 \u0985\u0982\u09B6 \u09A5\u09BE\u0995\
  \u09C7 \u098F\u09AC\u0982 \u098F\u0987 \u09B8\u0982\u0996\u09CD\u09AF\u09BE\u0997\
  \u09C1\u09B2\u09CB \u09AA\u09CD\u09B0\u0995\u09CC\u09B6\u09B2, \u09AA\u09A6\u09BE\
  \u09B0\u09CD\u09A5\u09AC\u09BF\u09A6\u09CD\u09AF\u09BE \u098F\u09AC\u0982 \u0995\
  \u09AE\u09CD\u09AA\u09BF\u0989\u099F\u09BE\u09B0 \u0997\u09CD\u09B0\u09BE\u09AB\u09BF\
  \u0995\u09CD\u09B8\u09C7\u09B0 \u09AE\u09A4 \u09AC\u09BF\u09AD\u09BF\u09A8\u09CD\
  \u09A8 \u0995\u09CD\u09B7\u09C7\u09A4\u09CD\u09B0\u09C7 \u0996\u09C1\u09AC\u0987\
  \ \u099C\u09B0\u09C1\u09B0\u09C0\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\
  \u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u098F\u0987 \u09B8\u0982\u0996\u09CD\u09AF\
  \u09BE\u0997\u09C1\u09B2\u09CB \u09AC\u09CD\u09AF\u09AC\u09B9\u09BE\u09B0 \u0995\
  \u09B0\u09C7\u09A8 \u098F\u09AE\u09A8 \u09B8\u09AE\u09C0\u0995\u09B0\u09A3 \u09B8\
  \u09AE\u09BE\u09A7\u09BE\u09A8\u09C7\u09B0 \u099C\u09A8\u09CD\u09AF \u09AF\u09C7\
  \u0997\u09C1\u09B2\u09CB \u09B8\u09BE\u09A7\u09BE\u09B0\u09A3 \u09AC\u09BE\u09B8\
  \u09CD\u09A4\u09AC \u09B8\u0982\u0996\u09CD\u09AF\u09BE \u09A6\u09CD\u09AC\u09BE\
  \u09B0\u09BE \u09B8\u09AE\u09BE\u09A7\u09BE\u09A8 \u0995\u09B0\u09BE \u09AF\u09BE\
  \u09AF\u09BC \u09A8\u09BE\u0964."
title: "\u099C\u099F\u09BF\u09B2 \u09B8\u0982\u0996\u09CD\u09AF\u09BE\u09B0 \u09B8\
  \u09BE\u09A5\u09C7 \u0995\u09BE\u099C \u0995\u09B0\u09BE"
weight: 14
---

## কিভাবে:
রাস্টে জটিল সংখ্যার জন্য অন্তর্নির্মিত সমর্থন নেই, তবে `num-complex` মতো ক্রেটগুলো আপনার পাশে আছে। এখানে এটি ব্যবহার করার উপায় দেওয়া হলঃ

```rust
use num_complex::Complex;

fn main() {
    let a = Complex::new(2.0, 3.0); // 2 + 3i
    let b = Complex::new(1.0, -4.0); // 1 - 4i

    let sum = a + b;
    let product = a * b;

    println!("Sum: {}", sum); // যোগফল: 3 - 1i
    println!("Product: {}", product); // গুণফল: 14 - 5i
}
```
এই জাদু ঘটাতে আপনাকে আপনার `Cargo.toml` এ `num_complex` যোগ করতে হবে।

## গভীর ডুব
জটিল সংখ্যাগুলো 16শ শতাব্দীতে ভাবনায় এসেছিল কিন্তু 18শ শতাব্দীতে ইউলারের মতো গণিতজ্ঞদের খেলার সময় এটি প্রকৃতপক্ষে জনপ্রিয় হয়। 

নেটিভ জটিল সংখ্যা অপারেশনগুলো ছাড়াই, রাস্ট এর মতো ভাষা তৃতীয় পক্ষের লাইব্রেরিগুলোর উপর নির্ভর করে। `num-complex` এমনই একটি ক্রেট এবং রাস্টের জন্য সংখ্যাতত্ত্বিক টাইপ এবং ট্রেইটস প্রদানের লক্ষ্যে `num` ক্রেট সংগ্রহের একটি অংশ।

এটি উল্লেখ্য যে, কিছু ভাষা (যেমন পাইথন) জটিল সংখ্যার জন্য অন্তর্নির্মিত সমর্থন রাখে, অন্য দিকে কিছু (যেমন সি++, `<complex>` হেডার দ্বারা) স্ট্যান্ডার্ড লাইব্রেরিতে এগুলো প্রদান করে। রাস্টে, স্ট্যান্ডার্ড লাইব্রেরিকে ছোট রাখার সিদ্ধান্তের মানে হল আপনি প্রায়শই অতিরিক্ত কার্যকারিতার জন্য সম্প্রদায় তৈরি ক্রেটগুলির দিকে ঝুঁকবেন।

## আরো দেখুন
- [রাস্ট বই](https://doc.rust-lang.org/book/): রাস্ট সম্পর্কে আরো জানতে এবং বাহ্যিক ক্রেটগুলি সাথে কাজ করার উপায় আবিষ্কার করতে।
- [জটিল সংখ্যা উইকিপিডিয়া](https://en.wikipedia.org/wiki/Complex_number): জটিল সংখ্যা সম্পর্কে গভীর ধারণা পেতে।
