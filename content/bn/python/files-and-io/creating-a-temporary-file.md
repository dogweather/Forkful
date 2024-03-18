---
changelog:
- 2024-03-17, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-17 17:47:24.285895-06:00
description: "\u098F\u0995\u099F\u09BF \u0985\u09B8\u09CD\u09A5\u09BE\u09AF\u09BC\u09C0\
  \ \u09AB\u09BE\u0987\u09B2 \u09A4\u09C8\u09B0\u09BF \u0995\u09B0\u09BE \u09AE\u09BE\
  \u09A8\u09C7 \u098F\u09AE\u09A8 \u098F\u0995\u099F\u09BF \u09AB\u09BE\u0987\u09B2\
  \ \u09A4\u09C8\u09B0\u09BF \u0995\u09B0\u09BE \u09AF\u09BE \u0986\u09AA\u09A8\u09BE\
  \u09B0 \u09AC\u09CD\u09AF\u09AC\u09B9\u09BE\u09B0 \u09B6\u09C7\u09B7\u09C7 \u09A4\
  \u09BE\u09B0 \u09AA\u09CD\u09B0\u09AF\u09BC\u09CB\u099C\u09A8 \u09A8\u09C7\u0987\
  \u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE\
  \ \u098F\u099F\u09BF \u0995\u09B0\u09C7\u09A8 \u098F\u09AE\u09A8 \u09A1\u09C7\u099F\
  \u09BE\u09B0 \u099C\u09A8\u09CD\u09AF \u09AF\u09C7\u099F\u09BF \u09B6\u09C1\u09A7\
  \u09C1\u09AE\u09BE\u09A4\u09CD\u09B0\u2026"
lastmod: '2024-03-17T18:47:43.595634-06:00'
model: gpt-4-0125-preview
summary: "\u098F\u0995\u099F\u09BF \u0985\u09B8\u09CD\u09A5\u09BE\u09AF\u09BC\u09C0\
  \ \u09AB\u09BE\u0987\u09B2 \u09A4\u09C8\u09B0\u09BF \u0995\u09B0\u09BE \u09AE\u09BE\
  \u09A8\u09C7 \u098F\u09AE\u09A8 \u098F\u0995\u099F\u09BF \u09AB\u09BE\u0987\u09B2\
  \ \u09A4\u09C8\u09B0\u09BF \u0995\u09B0\u09BE \u09AF\u09BE \u0986\u09AA\u09A8\u09BE\
  \u09B0 \u09AC\u09CD\u09AF\u09AC\u09B9\u09BE\u09B0 \u09B6\u09C7\u09B7\u09C7 \u09A4\
  \u09BE\u09B0 \u09AA\u09CD\u09B0\u09AF\u09BC\u09CB\u099C\u09A8 \u09A8\u09C7\u0987\
  \u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE\
  \ \u098F\u099F\u09BF \u0995\u09B0\u09C7\u09A8 \u098F\u09AE\u09A8 \u09A1\u09C7\u099F\
  \u09BE\u09B0 \u099C\u09A8\u09CD\u09AF \u09AF\u09C7\u099F\u09BF \u09B6\u09C1\u09A7\
  \u09C1\u09AE\u09BE\u09A4\u09CD\u09B0\u2026"
title: "\u098F\u0995\u099F\u09BF \u0985\u09B8\u09CD\u09A5\u09BE\u09AF\u09BC\u09C0\
  \ \u09AB\u09BE\u0987\u09B2 \u09A4\u09C8\u09B0\u09BF \u0995\u09B0\u09BE"
---

{{< edit_this_page >}}

## কী এবং কেন?
একটি অস্থায়ী ফাইল তৈরি করা মানে এমন একটি ফাইল তৈরি করা যা আপনার ব্যবহার শেষে তার প্রয়োজন নেই। প্রোগ্রামাররা এটি করেন এমন ডেটার জন্য যেটি শুধুমাত্র প্রোগ্রামের এক্সিকিউশনের সময় প্রয়োজন, যেমন মধ্যবর্তী ফলাফল অথবা মেমোরি অপব্যবহার এড়াতে।

## কিভাবে:
Python-এর `tempfile` মডিউল এর জন্য তৈরি। দেখুন এটি কিভাবে কাজ করে:

```Python
import tempfile

# একটি অস্থায়ী ফাইল তৈরি করুন এবং তাতে কিছু লিখুন
with tempfile.TemporaryFile(mode='w+t') as tf:
    # অস্থায়ী ফাইলে একটি স্ট্রিং লিখুন
    tf.write('Python is fun!')
    # পড়ার আগে ফাইলের শুরুতে ফিরে যান
    tf.seek(0)
    # আমরা যা লিখেছি তা পড়ুন
    print(tf.read())  # আউটপুট: Python is fun!

# এবং ঠিক এইভাবে, ব্লক থেকে বের হওয়ার পরে ফাইলটি চলে যায়
```

এই কোডটি ফাইল পরিচালনার জন্য একটি কন্টেক্সট ম্যানেজার ব্যবহার করে, যা নিজে থেকেই পরিষ্কার করে। কোনো দীর্ঘস্থায়ী ফাইল নেই!

## গভীর ডাইভ:
অস্থায়ী ফাইল নতুন নয়। এই ধরনের ফাইল কম্পিউটিংয়ের সূচনালগ্ন থেকেই অস্থায়ী ডেটা ধারণের জন্য ব্যবহৃত হয়েছে। Python-এর `tempfile` মডিউল অনন্য নাম উত্পন্ন করা এবং ব্যবহার শেষে ফাইলগুলি সরা�নোর মতো কঠিন বিষয়গুলি পরিচালনা করে। আরও বেশি নিয়ন্ত্রণ চাইলে, `NamedTemporaryFile` রয়েছে, যা আপনি এর স্বল্প জীবনকালে একটি নাম দিয়ে রেফারেন্স করতে পারেন। কিন্তু মনে রাখবেন, এর উদ্দেশ্য অস্থায়ী থাকা:

```Python
import tempfile

# একটি নামযুক্ত অস্থায়ী ফাইল তৈরি করুন
with tempfile.NamedTemporaryFile(delete=True) as ntf:
    print(f'Temp file name is: {ntf.name}')  # এটির একটি আসল নাম আছে!

# তবুও, ব্যবহারের পরে এটি অদৃশ্য হয়ে যায়
```

এবং নিয়মিত ফাইল ব্যবহার না করে `tempfile` কেন ব্যবহার করবেন? সিম্পল: `tempfile` ব্যবহার করা আপনাকে জঞ্জাল এবং সম্ভাব্য দ্বন্দ্ব থেকে রক্ষা করে — কল্পনা করুন আপনার স্ক্রিপ্ট পুনরায় চালানো হচ্ছে এবং একই ফাইল নাম পুনর্ব্যবহৃত হচ্ছে। ঝামেলাপূর্ণ, তাই না?

## আরও দেখুন:
- Python-এর tempfile ডকুমেন্টেশন: https://docs.python.org/3/library/tempfile.html
- Python-এ file I/O নিয়ে একটি টিউটোরিয়াল: https://realpython.com/read-write-files-python/
