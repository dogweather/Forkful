---
changelog:
- 2024-03-17, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-17 17:46:28.048773-06:00
description: "\u09A4\u09BE\u09B0\u09BF\u0996\u0997\u09C1\u09B2\u09BF\u0995\u09C7 \u09B8\
  \u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u0986\u0995\u09BE\u09B0\u09C7 \u09B0\u09C2\
  \u09AA\u09BE\u09A8\u09CD\u09A4\u09B0 \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\u09C7\
  \ \u09B9\u09B2 \u098F\u0995\u099F\u09BF \u09A4\u09BE\u09B0\u09BF\u0996 \u0985\u09AC\
  \u099C\u09C7\u0995\u09CD\u099F\u0995\u09C7 \u099F\u09C7\u0995\u09CD\u09B8\u099F\
  \ \u09AB\u09B0\u09CD\u09AE\u09CD\u09AF\u09BE\u099F\u09C7 \u09AA\u09B0\u09BF\u09AC\
  \u09B0\u09CD\u09A4\u09A8 \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\
  \u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u098F\u099F\u09BF \u09AC\u09CD\
  \u09AF\u09AC\u09B9\u09BE\u09B0\u0995\u09BE\u09B0\u09C0-\u09AC\u09BE\u09A8\u09CD\u09A7\
  \u09AC \u0989\u09AA\u09BE\u09DF\u09C7 \u09A4\u09BE\u09B0\u09BF\u0996\u2026"
lastmod: '2024-03-17T18:47:43.586790-06:00'
model: gpt-4-0125-preview
summary: "\u09A4\u09BE\u09B0\u09BF\u0996\u0997\u09C1\u09B2\u09BF\u0995\u09C7 \u09B8\
  \u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u0986\u0995\u09BE\u09B0\u09C7 \u09B0\u09C2\
  \u09AA\u09BE\u09A8\u09CD\u09A4\u09B0 \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\u09C7\
  \ \u09B9\u09B2 \u098F\u0995\u099F\u09BF \u09A4\u09BE\u09B0\u09BF\u0996 \u0985\u09AC\
  \u099C\u09C7\u0995\u09CD\u099F\u0995\u09C7 \u099F\u09C7\u0995\u09CD\u09B8\u099F\
  \ \u09AB\u09B0\u09CD\u09AE\u09CD\u09AF\u09BE\u099F\u09C7 \u09AA\u09B0\u09BF\u09AC\
  \u09B0\u09CD\u09A4\u09A8 \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\
  \u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u098F\u099F\u09BF \u09AC\u09CD\
  \u09AF\u09AC\u09B9\u09BE\u09B0\u0995\u09BE\u09B0\u09C0-\u09AC\u09BE\u09A8\u09CD\u09A7\
  \u09AC \u0989\u09AA\u09BE\u09DF\u09C7 \u09A4\u09BE\u09B0\u09BF\u0996\u2026"
title: "\u09A4\u09BE\u09B0\u09BF\u0996\u0995\u09C7 \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\
  \u0982 \u098F \u09B0\u09C2\u09AA\u09BE\u09A8\u09CD\u09A4\u09B0 \u0995\u09B0\u09BE"
---

{{< edit_this_page >}}

## কি এবং কেন?
তারিখগুলিকে স্ট্রিং আকারে রূপান্তর করা মানে হল একটি তারিখ অবজেক্টকে টেক্সট ফর্ম্যাটে পরিবর্তন করা। প্রোগ্রামাররা এটি ব্যবহারকারী-বান্ধব উপায়ে তারিখ প্রদর্শনের জন্য বা তাদেরকে CSV অথবা JSON এর মত টেক্সট-ভিত্তিক ফরম্যাটে সংরক্ষণের জন্য তৈরি করার জন্য করে থাকেন।

## কিভাবে:
Python তারিখগুলিকে স্ট্রিং-এ রূপান্তর করা সহজ করে তোলে। তারিখ অবজেক্টগুলিতে উপলব্ধ `strftime` পদ্ধতি ব্যবহার করুন। এখানে কিভাবে করা হয়:

```Python
থেকে datetime আমদানি করুন datetime

# বর্তমান তারিখ এবং সময় পান
এখন = datetime.now()

# এটিকে স্ট্রিং আকারে রূপান্তর করুন ফর্ম্যাট: মাস দিন, বছর
date_string = now.strftime("%B %d, %Y")
প্রিন্ট(date_string)  # আউটপুট: মার্চ 29, 2023 (অথবা বর্তমান তারিখ)

# ফর্ম্যাট: YYYY-MM-DD
iso_date_string = now.strftime("%Y-%m-%d")
প্রিন্ট(iso_date_string)  # আউটপুট: 2023-03-29 (অথবা বর্তমান তারিখ)
```

## গভীর ডাইভ
ইতিহাসে, তারিখ-স্ট্রিং রূপান্তর মানব-পাঠ্য ফর্ম্যাটে তারিখ উপস্থাপনের প্রয়োজনে প্রোগ্রামিং-এ একটি মূল উপাদান রেখেছে।

`strftime` এর বিকল্পগুলির মধ্যে `isoformat` পদ্ধতি ব্যবহার করা ISO 8601 ফর্ম্যাটের জন্য, অথবা `arrow` এবং `dateutil` এর মত তৃতীয়-পক্ষের লাইব্রেরিগুলি আরও সহজ পার্সিং এবং ফর্ম্যাটিং বিকল্প প্রস্তাব করে।

বাস্তবায়নের দিক থেকে, `strftime` মানে হল "স্ট্রিং ফর্ম্যাট টাইম" এবং এর উৎপত্তি সি প্রোগ্রামিং-এ। Python-এর `strftime` বছরের জন্য `%Y` এবং মাসের জন্য `%m` এর মত ফর্ম্যাট কোড ব্যাখ্যা করে, যা প্রায় অসীম কাস্টমাইজেশনের সুযোগ দেয়।

## আরও দেখুন
Python-এর তারিখ এবং সময় ফাংশনগুলি সম্পর্কে আরও গভীরে ডুব দিতে:
- Python-এর অফিসিয়াল `datetime` ডকুমেন্টেশন: https://docs.python.org/3/library/datetime.html
- `strftime` ডিরেক্টিভগুলির একটি সম্পূর্ণ তালিকা নিয়ে আগ্রহীদের জন্য: https://strftime.org/
- তৃতীয়-পক্ষের তারিখ/সময় লাইব্রেরিগুলি অন্বেষণ করতে:
  - Arrow: https://arrow.readthedocs.io/en/latest/
  - python-dateutil: https://dateutil.readthedocs.io/en/stable/
