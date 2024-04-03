---
changelog:
- 2024-03-17, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-17 17:48:08.458596-06:00
description: "\u098F\u0995\u099F\u09BF \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982\u09AF\
  \u09BC\u09C7\u09B0 \u09A6\u09C8\u09B0\u09CD\u0998\u09CD\u09AF \u09AE\u09BE\u09A8\
  \u09C7 \u09A4\u09BE\u09B0 \u0985\u0995\u09CD\u09B7\u09B0\u0997\u09C1\u09B2\u09BF\
  \ \u0997\u09A3\u09A8\u09BE \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\
  \u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u0987\u09A8\u09AA\u09C1\u099F\
  \ \u09AF\u09BE\u099A\u09BE\u0987, \u0985\u0995\u09CD\u09B7\u09B0\u0997\u09C1\u09B2\
  \u09BF\u09B0 \u09AE\u09BE\u09A7\u09CD\u09AF\u09AE\u09C7 \u09B2\u09C1\u09AA \u099A\
  \u09BE\u09B2\u09BE\u09A8\u09CB \u09AC\u09BE \u0995\u09C7\u09AC\u09B2 \u0986\u0989\
  \u099F\u09AA\u09C1\u099F \u09B8\u09BE\u09B0\u09BF\u09AC\u09A6\u09CD\u09A7 \u0995\
  \u09B0\u09BE\u09B0 \u099C\u09A8\u09CD\u09AF \u098F\u099F\u09BF \u0995\u09B0\u09C7\
  \u2026"
lastmod: '2024-03-17T18:47:44.214565-06:00'
model: gpt-4-0125-preview
summary: "\u098F\u0995\u099F\u09BF \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982\u09AF\
  \u09BC\u09C7\u09B0 \u09A6\u09C8\u09B0\u09CD\u0998\u09CD\u09AF \u09AE\u09BE\u09A8\
  \u09C7 \u09A4\u09BE\u09B0 \u0985\u0995\u09CD\u09B7\u09B0\u0997\u09C1\u09B2\u09BF\
  \ \u0997\u09A3\u09A8\u09BE \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\
  \u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u0987\u09A8\u09AA\u09C1\u099F\
  \ \u09AF\u09BE\u099A\u09BE\u0987, \u0985\u0995\u09CD\u09B7\u09B0\u0997\u09C1\u09B2\
  \u09BF\u09B0 \u09AE\u09BE\u09A7\u09CD\u09AF\u09AE\u09C7 \u09B2\u09C1\u09AA \u099A\
  \u09BE\u09B2\u09BE\u09A8\u09CB \u09AC\u09BE \u0995\u09C7\u09AC\u09B2 \u0986\u0989\
  \u099F\u09AA\u09C1\u099F \u09B8\u09BE\u09B0\u09BF\u09AC\u09A6\u09CD\u09A7 \u0995\
  \u09B0\u09BE\u09B0 \u099C\u09A8\u09CD\u09AF \u098F\u099F\u09BF \u0995\u09B0\u09C7\
  \ \u09A5\u09BE\u0995\u09C7\u09A8\u0964."
title: "\u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u098F\u09B0 \u09A6\u09C8\u09B0\
  \u09CD\u0998\u09CD\u09AF \u099A\u09BF\u09B9\u09CD\u09A8\u09BF\u09A4 \u0995\u09B0\
  \u09BE"
weight: 7
---

## কিভাবে:
ব্যাশে কাজটি সম্পন্ন করতে `#` প্রতীকটি ব্যবহার করা হয়। প্যারামিটার প্রসারণের সাথে এটি ব্যবহার করুন। এখানে কিভাবে:

```bash
my_string="Hello, World!"
string_length=${#my_string}
echo $string_length
```

নমুনা আউটপুট:

```
13
```

## গভীর ডাইভ
পুরানো দিনে, লোকেরা `expr` বা বাইরের টুল যেমন `wc -m` ব্যবহার করত, কিন্তু ব্যাশ নির্মিত বৈশিষ্ট্যগুলি খেলার চিত্র পরিবর্তন করেছে। `${#var}` সিনট্যাক্সটি ব্যাশে প্যারামিটার প্রসারণে প্রবর্তিত একটি অংশ। এটি দ্রুত ও দক্ষ কারণ এটি একটি সাবশেল শুরু করেনা অথবা বাইরের একটি প্রোগ্রাম কল করেনা।

বিকল্প? অবশ্যই, তোমার আছে:

- `expr length "$my_string"` আপনাকে একই ফলাফল দেয়, কিন্তু এটা একটু পুরানো স্কুলের।
- `echo -n $my_string | wc -m` `wc` ব্যবহার করে গণনা করে, কিন্তু সাধারণ কাজের জন্য এটি অতিরিক্ত।

বিস্তারিত, বিস্তারিত... যখন আপনি `${#my_string}` ব্যবহার করেন, এটি ডিফল্ট হিসাবে আপনাকে বাইটে দৈর্ঘ্য দেয়। যদি আপনার টেক্সট ইউনিকোডের দিকে হাঁটে, আপনাকে মাল্টি-বাইট অক্ষরগুলির বিবেচনা করতে হবে। সেই সময় বিষয়গুলো আরও জটিল হয়ে ওঠে।

## আরও দেখুন
`man bash` এর সাথে ম্যান পেজগুলিতে ডাইভ নিয়ে প্যারামিটার প্রসারণের সূক্ষ্ম বৃত্তান্তে প্রবেশ করুন। যারা বেসিক ASCII এর বাইরে স্ট্রিং সম্পর্কে দেখছেন, উন্নত Bash-Scripting গাইড কিছু উপদেশ দেয়: https://www.tldp.org/LDP/abs/html/. এবং শিক্ষার জন্য ভালোবাসা রাখুন, https://www.gnu.org/software/bash/manual/ এ নজর রাখুন ব্যাশ সম্পর্কে সর্বশেষ তথ্যের জন্য।
