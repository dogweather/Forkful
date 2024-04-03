---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:14:10.293033-06:00
description: "\u09B8\u0982\u0996\u09CD\u09AF\u09BE \u0997\u09CB\u09B2 \u0995\u09B0\
  \u09BE \u09AE\u09BE\u09A8\u09C7 \u09A6\u09B6\u09AE\u09BF\u0995 \u09B8\u09CD\u09A5\
  \u09BE\u09A8\u0997\u09C1\u09B2\u09BF \u0995\u09C7\u099F\u09C7 \u09AB\u09C7\u09B2\
  \u09BE \u09AF\u09BE\u09A4\u09C7 \u0986\u09AA\u09A8\u09BE\u09B0 \u09A1\u09BE\u099F\
  \u09BE \u09B8\u09B9\u099C \u0995\u09B0\u09BE \u09AF\u09BE\u09DF \u0985\u09A5\u09AC\
  \u09BE \u09A8\u09BF\u09B0\u09CD\u09A6\u09BF\u09B7\u09CD\u099F \u09AB\u09B0\u09AE\
  \u09CD\u09AF\u09BE\u099F\u09C7 \u09AB\u09BF\u099F \u0995\u09B0\u09BE\u09A8\u09CB\
  \ \u09AF\u09BE\u09DF\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\
  \u09BE\u09B0\u09B0\u09BE \u09A4\u09BE \u09AC\u09CD\u09AF\u09AC\u09B9\u09BE\u09B0\
  \u09BF\u0995 \u09AA\u09CD\u09B0\u09A6\u09B0\u09CD\u09B6\u09A8\u09C7\u09B0\u2026"
lastmod: '2024-03-17T18:47:44.490318-06:00'
model: gpt-4-0125-preview
summary: "\u09B8\u0982\u0996\u09CD\u09AF\u09BE \u0997\u09CB\u09B2 \u0995\u09B0\u09BE\
  \ \u09AE\u09BE\u09A8\u09C7 \u09A6\u09B6\u09AE\u09BF\u0995 \u09B8\u09CD\u09A5\u09BE\
  \u09A8\u0997\u09C1\u09B2\u09BF \u0995\u09C7\u099F\u09C7 \u09AB\u09C7\u09B2\u09BE\
  \ \u09AF\u09BE\u09A4\u09C7 \u0986\u09AA\u09A8\u09BE\u09B0 \u09A1\u09BE\u099F\u09BE\
  \ \u09B8\u09B9\u099C \u0995\u09B0\u09BE \u09AF\u09BE\u09DF \u0985\u09A5\u09AC\u09BE\
  \ \u09A8\u09BF\u09B0\u09CD\u09A6\u09BF\u09B7\u09CD\u099F \u09AB\u09B0\u09AE\u09CD\
  \u09AF\u09BE\u099F\u09C7 \u09AB\u09BF\u099F \u0995\u09B0\u09BE\u09A8\u09CB \u09AF\
  \u09BE\u09DF\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\
  \u09B0\u09BE \u09A4\u09BE \u09AC\u09CD\u09AF\u09AC\u09B9\u09BE\u09B0\u09BF\u0995\
  \ \u09AA\u09CD\u09B0\u09A6\u09B0\u09CD\u09B6\u09A8\u09C7\u09B0 \u099C\u09A8\u09CD\
  \u09AF, \u09A6\u0995\u09CD\u09B7 \u09B8\u09CD\u099F\u09CB\u09B0\u09C7\u099C\u09C7\
  \u09B0 \u099C\u09A8\u09CD\u09AF, \u0985\u09A5\u09AC\u09BE \u09AF\u0996\u09A8 \u09A6\
  \u09B6\u09AE\u09BF\u0995 \u09A8\u09BF\u09B0\u09CD\u09AD\u09C1\u09B2\u09A4\u09BE\
  \ \u098F\u0995\u099F\u09BF \u09B8\u09AE\u09B8\u09CD\u09AF\u09BE \u09A8\u09AF\u09BC\
  \ \u09A4\u0996\u09A8 \u09A4\u09BE \u0995\u09B0\u09C7 \u09A5\u09BE\u0995\u09C7\u09A8\
  \u0964."
title: "\u09B8\u0982\u0996\u09CD\u09AF\u09BE \u09A8\u09BF\u09B0\u09CD\u09A3\u09DF"
weight: 13
---

## কিভাবে:
Fish-এ, সংখ্যা গোল করা `math` কমান্ডের উপর নির্ভর করে। নিকটস্থ পূর্ণসংখ্যায় গোল করতে `math -s0` ব্যবহার করুন।

```fish
# উপরে গোল করা
echo (math -s0 "4.7")
# আউটপুট: 5

# নিচে গোল করা
echo (math -s0 "4.3")
# আউটপুট: 4

# দুই দশমিক স্থানে গোল করা
echo (math -s2 "4.5678")
# আউটপুট: 4.57

# ঋণাত্মক সংখ্যা গোল করা
echo (math -s0 "-2.5")
# আউটপুট: -3
```

## গভীর ডুব
ঐতিহাসিকভাবে, সংখ্যা গোল করা আরো ম্যানুয়ালি করা হতো অথবা বাহ্যিক টুলস দিয়ে, কিন্তু মডার্ন শেলগুলিতে যেমন Fish, এটা বিল্ট-ইন ইউটিলিটিগুলির মধ্যে অন্তর্ভুক্ত। Fish এর `math` কমান্ড ব্যবহার করা প্রক্রিয়াটি পুরনো শেলগুলির তুলনায় সহজ করে। অন্যান্য প্রোগ্রামিং পরিবেশের বিকল্পগুলি বিভিন্ন; যেমন পাইথনে `round()` ফাংশন ব্যবহার করা হয়, যেখানে Bash এ আরো জটিল এক্সপ্রেশন অথবা `bc` ইউটিলিটি প্রয়োজন হতে পারে। Fish-এর গোল করার বাস্তবায়ন ম্যাথকে শেল পরিবেশের ভেতরে রেখে স্ক্রিপ্টিং সহজ করে দেয় অন্যান্য টুল বা ভাষা ডেকে না আনিয়ে।

## আরো দেখুন
- Fish ডকুমেন্টেশনে `math` কমান্ডের জন্য: https://fishshell.com/docs/current/cmds/math.html
- ফ্লোটিং-পয়েন্ট অঙ্ক জন্য IEEE স্ট্যান্ডার্ড (IEEE 754): https://ieeexplore.ieee.org/document/4610935
