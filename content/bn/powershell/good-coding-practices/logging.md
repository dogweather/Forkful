---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 17:51:11.178365-06:00
description: "\u09B2\u0997\u09BF\u0982 \u09AE\u09C2\u09B2\u09A4 \u0986\u09AA\u09A8\
  \u09BE\u09B0 \u0995\u09CB\u09A1\u09C7\u09B0 \u09AE\u09A7\u09CD\u09AF \u09A6\u09BF\
  \u09AF\u09BC\u09C7 \u098F\u0995\u099F\u09BF \u09AC\u09CD\u09B0\u09C7\u09A1\u0995\
  \u09CD\u09B0\u09BE\u09AE\u09CD\u09AC \u099F\u09CD\u09B0\u09C7\u0987\u09B2 \u099B\
  \u09C7\u09A1\u09BC\u09C7 \u09A6\u09C7\u0993\u09AF\u09BC\u09BE - \u098F\u099F\u09BF\
  \ \u09B9\u09B2 \u09AF\u0996\u09A8 \u0986\u09AA\u09A8\u09BE\u09B0 \u09B8\u09CD\u0995\
  \u09CD\u09B0\u09BF\u09AA\u09CD\u099F \u09AC\u09BE\u0987\u09B0\u09C7 \u099A\u09B2\
  \u099B\u09C7 \u09A4\u0996\u09A8 \u0995\u09BF \u0998\u099F\u099B\u09C7 \u09A4\u09BE\
  \ \u09A8\u099C\u09B0\u09C7 \u09B0\u09BE\u0996\u09BE\u09B0 \u0989\u09AA\u09BE\u09AF\
  \u09BC\u0964\u2026"
lastmod: '2024-03-17T18:47:44.283840-06:00'
model: gpt-4-0125-preview
summary: "\u09B2\u0997\u09BF\u0982 \u09AE\u09C2\u09B2\u09A4 \u0986\u09AA\u09A8\u09BE\
  \u09B0 \u0995\u09CB\u09A1\u09C7\u09B0 \u09AE\u09A7\u09CD\u09AF \u09A6\u09BF\u09AF\
  \u09BC\u09C7 \u098F\u0995\u099F\u09BF \u09AC\u09CD\u09B0\u09C7\u09A1\u0995\u09CD\
  \u09B0\u09BE\u09AE\u09CD\u09AC \u099F\u09CD\u09B0\u09C7\u0987\u09B2 \u099B\u09C7\
  \u09A1\u09BC\u09C7 \u09A6\u09C7\u0993\u09AF\u09BC\u09BE - \u098F\u099F\u09BF \u09B9\
  \u09B2 \u09AF\u0996\u09A8 \u0986\u09AA\u09A8\u09BE\u09B0 \u09B8\u09CD\u0995\u09CD\
  \u09B0\u09BF\u09AA\u09CD\u099F \u09AC\u09BE\u0987\u09B0\u09C7 \u099A\u09B2\u099B\
  \u09C7 \u09A4\u0996\u09A8 \u0995\u09BF \u0998\u099F\u099B\u09C7 \u09A4\u09BE \u09A8\
  \u099C\u09B0\u09C7 \u09B0\u09BE\u0996\u09BE\u09B0 \u0989\u09AA\u09BE\u09AF\u09BC\
  \u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE\
  \ \u09A1\u09BF\u09AC\u09BE\u0997\u09BF\u0982, \u0985\u09CD\u09AF\u09BE\u09AA\u09C7\
  \u09B0 \u0986\u099A\u09B0\u09A3 \u099F\u09CD\u09B0\u09CD\u09AF\u09BE\u0995 \u0995\
  \u09B0\u09BE, \u09AA\u09BE\u09B0\u09AB\u09B0\u09CD\u09AE\u09CD\u09AF\u09BE\u09A8\
  \u09CD\u09B8 \u09AE\u09A8\u09BF\u099F\u09B0 \u0995\u09B0\u09BE \u098F\u09AC\u0982\
  \ \u09AF\u09C7 \u0995\u09CB\u09A8 \u0985\u09B8\u09A6\u09BE\u099A\u09B0\u09A3\u09C7\
  \u09B0 \u099C\u09A8\u09CD\u09AF \u09A8\u099C\u09B0 \u09B0\u09BE\u0996\u09BE\u09B0\
  \ \u0989\u09A6\u09CD\u09A6\u09C7\u09B6\u09C7 \u09B2\u0997 \u0995\u09B0\u09C7\u0964\
  ."
title: "\u09B2\u0997\u09BF\u0982"
weight: 17
---

## কিভাবে:
এখানে আপনার স্ক্রিপ্টে কিছু মৌলিক লগিং অন্তর্ভুক্ত করার উপায়ের বিবরণ দেওয়া হয়েছে:

```PowerShell
# একটি সাধারণ লগ বার্তা তৈরি
Write-Host "Info: স্ক্রিপ্ট প্রক্রিয়া শুরু হচ্ছে।"

# ফাইলে লিখন
"Info: এটি একটি লগ করা বার্তা।" | Out-File -Append myLog.log

# আরও বিস্তারিত লগিং এর জন্য বিল্ট-ইন cmdlet ব্যবহার
Start-Transcript -Path "./detailedLog.log"
Write-Output "Warning: কিছু একটা ঠিক নেই।"
# ... আপনার স্ক্রিপ্ট কিছু কাজ করে
Stop-Transcript

# detailedLog.log এর আউটপুট
******************************
Windows PowerShell ট্রান্সক্রিপ্ট শুরু
শুরুর সময়: 20230324112347
ইউজারনেম  : PShellGuru@example.com
RunAs ইউজার: PShellGuru@example.com
কনফিগারেশনের নাম: 
মেশিন  : PS-DEVBOX (Microsoft Windows NT 10.0.17763.0)
হোস্ট অ্যাপ্লিকেশন: C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe
প্রসেস আইডি: 2024
PS ভার্সন: 7.1.2
```

এখন, আপনার লগে, আপনার কোডের সাথে কি ঘটেছিল তার একটি প্লে-বাই-প্লে রয়েছে।

## গভীর ডুব:
ঐতিহাসিকভাবে, লগিং প্রায় প্রোগ্রামিং এর সাথে সমান বয়সী। এটি সফটওয়্যারের জন্য একটি ক্যাপ্টেনের লগের মত। পুরানো দিনগুলিতে, এটি প্রিন্টআউট বা টেলিটাইপ মেশিন হতে পারে; এখন এটি সম্পর্কে ফাইল এবং ফ্যান্সি লগ ম্যানেজমেন্ট সিস্টেম।

যখন আপনি PowerShell খাঁজে নেমে যান, `Write-Host` দ্রুত এবং নোংরা, কিন্তু এটি কনসোলে শুধুমাত্র টেক্সট বের করে, রেকর্ড রাখার জন্য খুব ভালো নয়। `Out-File` আপনাকে ফাইলে টেক্সট ফেলার একটি সহজ উপায় দেয়, কিন্তু আসল জুসের জন্য, আপনি `Start-Transcript` এবং `Stop-Transcript` চাইবেন যা সবকিছু লগ করে - ইনপুট, আউটপুট, সব কিছু।

বিকল্প? অবশ্যই, যদি আপনি এন্টারপ্রাইজ পর্যায়ে থাকেন, আপনি Windows Event Log বা Logstash এর মতো সফটওয়্যার ব্যবহার করার দিকে নজর দিতে পারেন, কিন্তু আপনার দৈনন্দিন স্ক্রিপ্টের জন্য, PowerShell এর টুলগুলির সাথে থাকুন। বাস্তবায়নের ক্ষেত্রে, মনে রাখবেন স্মার্টভাবে লগ করুন - খুব কম হলে তা ব্যর্থ, খুব বেশি হলে তা শুভ্র ঝালায় পরিণত হয়।

## আরও দেখুন:
PowerShell-এ লগিং সম্পর্কে সবকিছু ধরে রাখার জন্য এগুলি দেখুন:
