---
changelog:
- 2024-03-17, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-17 17:45:34.368410-06:00
description: "\u09A6\u09C1\u099F\u09BF \u09A4\u09BE\u09B0\u09BF\u0996\u09C7\u09B0\
  \ \u09A4\u09C1\u09B2\u09A8\u09BE \u0995\u09B0\u09C7 \u0986\u09AA\u09A8\u09BF \u09AC\
  \u09C1\u099D\u09A4\u09C7 \u09AA\u09BE\u09B0\u09AC\u09C7\u09A8 \u0995\u09CB\u09A8\
  \u099F\u09BF \u0986\u0997\u09C7\u09B0, \u09AA\u09B0\u09C7\u09B0, \u09A8\u09BE\u0995\
  \u09BF \u09A4\u09BE\u09B0\u09BE \u098F\u0995\u0987 \u09B8\u09AE\u09AF\u09BC\u09C7\
  \u09B0 \u09AE\u09C1\u09B9\u09C2\u09B0\u09CD\u09A4\u09C7 \u0986\u099B\u09C7\u0964\
  \ \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE\
  \ \u098F\u099F\u09BF \u0995\u09B0\u09C7 \u09A5\u09BE\u0995\u09C7\u09A8 \u0998\u099F\
  \u09A8\u09BE\u09AC\u09B2\u09C0 \u09B8\u09BE\u099C\u09BE\u09A8\u09CB, \u09A8\u09BF\
  \u09B0\u09CD\u09A6\u09BF\u09B7\u09CD\u099F \u09B8\u09AE\u09AF\u09BC\u09C7\u2026"
lastmod: '2024-03-17T18:47:44.240223-06:00'
model: gpt-4-0125-preview
summary: "\u09A6\u09C1\u099F\u09BF \u09A4\u09BE\u09B0\u09BF\u0996\u09C7\u09B0 \u09A4\
  \u09C1\u09B2\u09A8\u09BE \u0995\u09B0\u09C7 \u0986\u09AA\u09A8\u09BF \u09AC\u09C1\
  \u099D\u09A4\u09C7 \u09AA\u09BE\u09B0\u09AC\u09C7\u09A8 \u0995\u09CB\u09A8\u099F\
  \u09BF \u0986\u0997\u09C7\u09B0, \u09AA\u09B0\u09C7\u09B0, \u09A8\u09BE\u0995\u09BF\
  \ \u09A4\u09BE\u09B0\u09BE \u098F\u0995\u0987 \u09B8\u09AE\u09AF\u09BC\u09C7\u09B0\
  \ \u09AE\u09C1\u09B9\u09C2\u09B0\u09CD\u09A4\u09C7 \u0986\u099B\u09C7\u0964 \u09AA\
  \u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u098F\u099F\
  \u09BF \u0995\u09B0\u09C7 \u09A5\u09BE\u0995\u09C7\u09A8 \u0998\u099F\u09A8\u09BE\
  \u09AC\u09B2\u09C0 \u09B8\u09BE\u099C\u09BE\u09A8\u09CB, \u09A8\u09BF\u09B0\u09CD\
  \u09A6\u09BF\u09B7\u09CD\u099F \u09B8\u09AE\u09AF\u09BC\u09C7 \u0995\u09CD\u09B0\
  \u09BF\u09AF\u09BC\u09BE\u0995\u09B2\u09BE\u09AA \u099F\u09CD\u09B0\u09BF\u0997\u09BE\
  \u09B0 \u0995\u09B0\u09BE, \u0985\u09A5\u09AC\u09BE \u0995\u09C7\u09AC\u09B2 \u0985\
  \u09A4\u09BF\u09AC\u09BE\u09B9\u09BF\u09A4 \u09B8\u09AE\u09AF\u09BC \u099F\u09CD\
  \u09B0\u09CD\u09AF\u09BE\u0995 \u0995\u09B0\u09BE\u09B0 \u099C\u09A8\u09CD\u09AF\
  \u0964."
title: "\u09A6\u09C1\u099F\u09BF \u09A4\u09BE\u09B0\u09BF\u0996 \u09A4\u09C1\u09B2\
  \u09A8\u09BE \u0995\u09B0\u09BE"
weight: 27
---

## কিভাবে:
এখানে একটি সহজ উপায় দেওয়া হলো Bash এ দুটি তারিখের তুলনা করার:

```Bash
date1="2023-04-01"
date2="2023-04-15"

# তারিখগুলিকে এপকের পর থেকে সেকেন্ডে রূপান্তর করুন
sec1=$(date -d "$date1" +%s)
sec2=$(date -d "$date2" +%s)

# তারিখগুলিকে তুলনা করুন
if [ $sec1 -eq $sec2 ]; then
    echo "তারিখগুলো একই।"
elif [ $sec1 -lt $sec2 ]; then
    echo "তারিখ $date1 হলো $date2 এর থেকে আগের।"
else
    echo "তারিখ $date1 হলো $date2 এর থেকে পরের।"
fi
```

যদি `$date2` পরের হয় তবে নমুনা আউটপুট:

```
তারিখ 2023-04-01 হলো 2023-04-15 এর থেকে আগের।
```

## গভীর ডুব
ঐতিহাসিকভাবে, শেল স্ক্রিপ্টে তারিখের তুলনা করা সরাসরি সহজ ছিল না বিভিন্ন তারিখের ফরম্যাট এবং অন্তর্নির্মিত ফাংশনের অভাবের কারণে। `date` কমান্ড, `%s` দ্বারা তারিখগুলিকে Unix এপক (1970 সালের 1 জানুয়ারি 00:00:00 UTC) থেকে সেকেন্ডে রূপান্তর করা, এক আশীর্বাদ।

বিকল্প পদ্ধতির মধ্যে রয়েছে `awk` মতো বাহ্যিক টুল ব্যবহার করা অথবা স্ট্রিং তুলনা করা – ফরম্যাট বিভিন্ন হলে এটি ঝুঁকির। বাস্তবায়নের দিক থেকে, একটি আচ্ছন্ন হচ্ছে সময় জোন নিয়ে মোকাবিলা করা: `date` কমান্ডের আগে `TZ=UTC` যোগ করা ইউটিসি তুলনা নিশ্চিত করে।

তারিখের অঙ্ক, যেমন তারিখের মধ্যে পার্থক্য খুঁজে বের করা, জটিল হতে পারে। দিন যোগ বা বিয়োগ করা আরও `date` কৌশল দাবি করে। লিপ সেকেন্ড বা দিনের আলো সঞ্চয়ের পরিবর্তনের মতো কোণঠাসা ক্ষেত্রগুলি ত্রুটি আনতে পারে।

## আরও দেখুন
- [`date` ম্যানুয়াল পৃষ্ঠা](https://man7.org/linux/man-pages/man1/date.1.html) ফরম্যাট অপশনের জন্য।
- [Stack Overflow](https://stackoverflow.com/questions/tagged/bash) কমিউনিটির জ্ঞান এবং সমস্যা সমাধানের জন্য।
