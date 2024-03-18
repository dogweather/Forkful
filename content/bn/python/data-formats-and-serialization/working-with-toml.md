---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:31:23.891094-06:00
description: "TOML, \u09AF\u09BE\u09B0 \u09AA\u09C2\u09B0\u09CD\u09A3\u09B0\u09C2\u09AA\
  \ Tom's Obvious, Minimal Language, \u09B9\u09B2 \u098F\u0995\u099F\u09BF \u09A1\u09BE\
  \u099F\u09BE \u09B8\u09BF\u09B0\u09BF\u09AF\u09BC\u09BE\u09B2\u09BE\u0987\u099C\u09C7\
  \u09B6\u09A8 \u09AB\u09B0\u09AE\u09CD\u09AF\u09BE\u099F \u09AF\u09BE JSON \u0985\
  \u09A5\u09AC\u09BE YAML \u098F\u09B0 \u09AE\u09A4 \u0995\u09BF\u09A8\u09CD\u09A4\
  \u09C1 \u098F\u099F\u09BF \u09B8\u09BE\u09A7\u09BE\u09B0\u09A3\u09A4\u09BE \u098F\
  \u09AC\u0982 \u09AA\u09A1\u09BC\u09BE\u09B0 \u09B8\u09B9\u099C\u09A4\u09BE\u09B0\
  \ \u099C\u09A8\u09CD\u09AF\u2026"
lastmod: '2024-03-17T18:47:43.599944-06:00'
model: gpt-4-0125-preview
summary: "TOML, \u09AF\u09BE\u09B0 \u09AA\u09C2\u09B0\u09CD\u09A3\u09B0\u09C2\u09AA\
  \ Tom's Obvious, Minimal Language, \u09B9\u09B2 \u098F\u0995\u099F\u09BF \u09A1\u09BE\
  \u099F\u09BE \u09B8\u09BF\u09B0\u09BF\u09AF\u09BC\u09BE\u09B2\u09BE\u0987\u099C\u09C7\
  \u09B6\u09A8 \u09AB\u09B0\u09AE\u09CD\u09AF\u09BE\u099F \u09AF\u09BE JSON \u0985\
  \u09A5\u09AC\u09BE YAML \u098F\u09B0 \u09AE\u09A4 \u0995\u09BF\u09A8\u09CD\u09A4\
  \u09C1 \u098F\u099F\u09BF \u09B8\u09BE\u09A7\u09BE\u09B0\u09A3\u09A4\u09BE \u098F\
  \u09AC\u0982 \u09AA\u09A1\u09BC\u09BE\u09B0 \u09B8\u09B9\u099C\u09A4\u09BE\u09B0\
  \ \u099C\u09A8\u09CD\u09AF\u2026"
title: "\u099F\u09AE\u09B2 \u09A8\u09BF\u09AF\u09BC\u09C7 \u0995\u09BE\u099C \u0995\
  \u09B0\u09BE"
---

{{< edit_this_page >}}

## কি এবং কেন?
TOML, যার পূর্ণরূপ Tom's Obvious, Minimal Language, হল একটি ডাটা সিরিয়ালাইজেশন ফরম্যাট যা JSON অথবা YAML এর মত কিন্তু এটি সাধারণতা এবং পড়ার সহজতার জন্য উন্নত। প্রোগ্রামাররা কনফিগারেশন ফাইলগুলির জন্য TOML ব্যবহার করে কারণ এটি লেখা এবং বুঝতে সহজ, এবং এটি পাইথনের মত প্রোগ্রামিং ভাষাগুলিতে ডেটা স্ট্রাকচারে সুন্দরভাবে ম্যাপ করে।

## কিভাবে:
শুরু করার আগে, `toml` প্যাকেজ ইনস্টল করুন `pip install toml` দিয়ে। চলুন একটি TOML ফাইল পার্স করি:

```python
import toml

# উদাহরণ TOML কন্টেন্ট একটি স্ট্রিং আকারে
toml_string = """
[owner]
name = "Tom Preston-Werner"
dob = 1979-05-27T07:32:00Z # প্রথম শ্রেণির তারিখ

[database]
server = "192.168.1.1"
ports = [ 8001, 8001, 8002 ]
"""

# TOML স্ট্রিং পার্স করা
parsed_toml = toml.loads(toml_string)

# ডেটা অ্যাক্সেসিং
print(parsed_toml['owner']['name'])  # আউটপুট: Tom Preston-Werner
print(parsed_toml['database']['ports'])  # আউটপুট: [8001, 8001, 8002]
```

## গভীর ডুব
TOML টম প্রেস্টন-ওয়ের্নার দ্বারা সৃষ্টি, যিনি GitHub এর প্রতিষ্ঠাতাদের একজন, এটি একটি ব্যবহারকারী-বান্ধব কনফিগারেশন ফাইল ফরম্যাট হিসেবে ডিজাইন করা হয়েছে। এটি একটি হ্যাশ টেবিলে এক নির্দ্বিধায় ম্যাপ করার জন্য ডিজাইন করা হয়েছে এবং মেশিন দ্বারা সহজেই পার্স করা সম্ভব।

JSON এর তুলনায়, TOML কনফিগারেশন ফাইলগুলির জন্য অধিকাংশ পঠনীয় এবং মন্তব্য সমর্থন করে। YAML, একটি অন্য বিকল্প, আরও সংকুচিত হতে পারে, কিন্তু এর ইনডেনটেশনের উপর নির্ভরতা এবং যেমন ট্যাবগুলি অনুমোদিত নয় এমন সূক্ষ্ম সমস্যা, মানুষকে বিভ্রান্ত করতে পারে। 

কার্যনির্বাহের বিস্তারিত বিবরণের বিষয়ে, TOML মানগুলি টাইপড, যা স্ট্রিং, পূর্ণসংখ্যা, ফ্লোট, বুলিয়ান, ডেটাটাইম, অ্যারে, এবং টেবিল অন্তর্ভুক্ত। সবকিছু কেস সেনসিটিভ। এছাড়াও, TOML মাল্টি-লাইন স্ট্রিংস সমর্থন করে এবং, সর্বশেষ সংস্করণে, এমনকি বিভিন্ন টাইপ করা অ্যারেগুলির জন্যও অনুমোদন করে।

Python `toml` লাইব্রেরিটি ব্যবহার করে, যা JSON এবং YAML লাইব্রেরিগুলির সাথে API এর দিক দিয়ে মিল রাখে। আপনার কাছে `toml.load` এবং `toml.loads` রয়েছে একটি ফাইল বা একটি স্ট্রিং থেকে TOML পড়ার জন্য, যথাক্রমে, এবং `toml.dump` এবং `toml.dumps` রয়েছে এটি লিখতে।

## আরও দেখুন
- স্পেক্সের জন্য অফিসিয়াল TOML GitHub রিপোজিটরি: [github.com/toml-lang/toml](https://github.com/toml-lang/toml)
- `toml` Python লাইব্রেরি ডকুমেন্টেশন: [pypi.org/project/toml/](https://pypi.org/project/toml/)
- TOML এর বাস্তব জগতের উদাহরণ: Rust এর প্যাকেজ ম্যানেজার `cargo` বা Python প্যাকেজিং টূল `poetry` এর কনফিগারেশন ফাইলগুলি।
