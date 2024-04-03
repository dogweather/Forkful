---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 17:51:32.330322-06:00
description: "PowerShell \u098F \u09A4\u09CD\u09B0\u09C1\u099F\u09BF \u09B8\u09BE\u09AE\
  \u09B2\u09BE\u09A8\u09CB \u09AE\u09BE\u09A8\u09C7 \u09B9\u09B2\u09CB \u09A6\u09C1\
  \u09B0\u09CD\u0998\u099F\u09A8\u09BE\u0997\u09C1\u09B2\u09BF \u0985\u09A8\u09C1\u09AE\
  \u09BE\u09A8 \u0995\u09B0\u09BE \u098F\u09AC\u0982 \u09A4\u09BE\u09A6\u09C7\u09B0\
  \ \u09AE\u09B8\u09C3\u09A3\u09AD\u09BE\u09AC\u09C7 \u09AA\u09B0\u09BF\u099A\u09BE\
  \u09B2\u09A8\u09BE \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\
  \u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u098F\u099F\u09BF \u09A6\u09C1\u09B0\
  \u09CD\u0998\u099F\u09A8\u09BE\u0997\u09C1\u09B2\u09BF \u098F\u09A1\u09BC\u09BE\u09A4\
  \u09C7 \u098F\u09AC\u0982 \u09AC\u09CD\u09AF\u09AC\u09B9\u09BE\u09B0\u0995\u09BE\
  \u09B0\u09C0\u09A6\u09C7\u09B0\u2026"
lastmod: '2024-03-17T18:47:44.284840-06:00'
model: gpt-4-0125-preview
summary: "PowerShell \u098F \u09A4\u09CD\u09B0\u09C1\u099F\u09BF \u09B8\u09BE\u09AE\
  \u09B2\u09BE\u09A8\u09CB \u09AE\u09BE\u09A8\u09C7 \u09B9\u09B2\u09CB \u09A6\u09C1\
  \u09B0\u09CD\u0998\u099F\u09A8\u09BE\u0997\u09C1\u09B2\u09BF \u0985\u09A8\u09C1\u09AE\
  \u09BE\u09A8 \u0995\u09B0\u09BE \u098F\u09AC\u0982 \u09A4\u09BE\u09A6\u09C7\u09B0\
  \ \u09AE\u09B8\u09C3\u09A3\u09AD\u09BE\u09AC\u09C7 \u09AA\u09B0\u09BF\u099A\u09BE\
  \u09B2\u09A8\u09BE \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\
  \u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u098F\u099F\u09BF \u09A6\u09C1\u09B0\
  \u09CD\u0998\u099F\u09A8\u09BE\u0997\u09C1\u09B2\u09BF \u098F\u09A1\u09BC\u09BE\u09A4\
  \u09C7 \u098F\u09AC\u0982 \u09AC\u09CD\u09AF\u09AC\u09B9\u09BE\u09B0\u0995\u09BE\
  \u09B0\u09C0\u09A6\u09C7\u09B0 \u0989\u09AA\u0995\u09BE\u09B0\u09C0 \u09AA\u09CD\
  \u09B0\u09A4\u09BF\u0995\u09CD\u09B0\u09BF\u09AF\u09BC\u09BE \u09AA\u09CD\u09B0\u09A6\
  \u09BE\u09A8 \u0995\u09B0\u09A4\u09C7 \u0995\u09B0\u09C7\u0964."
title: "\u09A4\u09CD\u09B0\u09C1\u099F\u09BF\u0997\u09C1\u09B2\u09BF \u09AA\u09B0\u09BF\
  \u099A\u09BE\u09B2\u09A8\u09BE \u0995\u09B0\u09BE"
weight: 16
---

## কিভাবে:
```PowerShell
# ব্যাতিক্রমগুলি সামলানোর জন্য মৌলিক ট্রাই-ক্যাচ
try {
    # কোড যা ত্রুটি ট্রিগার করতে পারে
    $result = 1 / 0
} catch {
    # একটি ত্রুটি ঘটলে কি করবেন
    Write-Host "ওহো, একটি ত্রুটি ঘটেছে: $_"
}

# একটি কাস্টম ত্রুটি বার্তা আউটপুট করা
try {
    Get-Item "nonexistentfile.txt" -ErrorAction Stop
} catch {
    Write-Host "ফাইলটি পাওয়া যায়নি।"
}

# শেষ ত্রুটিটি পরীক্ষা করতে $Error ভেরিয়েবল ব্যবহার করা
```

## গভীর ডুব
PowerShell এর আবির্ভাবের পর থেকে এটি Monad হিসেবে অনেক দূরাগত হয়েছে। সময়ের সাথে সাথে ত্রুটি সামলানো আরও দৃঢ় হয়েছে, অন্যান্য প্রোগ্রামিং ভাষার মতো বৈশিষ্ট্য প্রদান করে। `try-catch-finally` ব্যাকরণ হল এরূপ এক ক্রস-পোলিনেশন, C# এর মতো ভাষাগুলি থেকে। এর আগে, স্ক্রিপ্টাররা প্রধানত শর্তাবলী পরীক্ষা করা এবং `$Error` স্বয়ংক্রিয় ভেরিয়েবল ব্যবহারের উপর নির্ভর করেছিলেন।

PowerShell এ দুই প্রধান ধরনের ত্রুটি রয়েছে: সমাপ্ত এবং অ-সমাপ্ত। সমাপ্ত ত্রুটি একটি স্ক্রিপ্টকে বন্ধ করে দেবে, যদ্যনা এটি একটি `try-catch` ব্লকে ধরা পড়ে, যখন অ-সমাপ্ত ত্রুটিগুলি বন্ধ করে দেবে না যদি আপনি `-ErrorAction Stop` উল্লেখ না করেন। এই পার্থক্য ক্রুশিয়াল কেননা এটি ত্রুটি সামলানোর উপর সূক্ষ্ম নিয়ন্ত্রণ প্রদান করে, সিদ্ধান্ত নেওয়ার পেছনে যে একটি ত্রুটি সত্যি সত্যি সম্পূর্ণ স্ক্রিপ্টটি থামানোর যোগ্য কিনা বা কেবলমাত্র লগ করে উপেক্ষা করা যেতে পারে।

PowerShell এর ত্রুটি সামলানো একটি `finally` ব্লকের জন্য অনুমতি দেয়, যা কোন পরিস্থিতিতেই কাজ করে, ত্রুটি ঘটুক বা না ঘটুক। এটি পরিষ্কার কাজের জন্য দুর্দান্ত।

আপনি যখন স্ক্রিপ্টিং গভীর খাঁজে রয়েছেন, আপনি নির্দিষ্ট ব্যাতিক্রম ধরনের সাথে দখল নিতে পারেন, যা আপনাকে আরও সূক্ষ্ম নিয়ন্ত্রণ দেয়।

পরিবর্তে, `-ErrorVariable` পরামিতি রয়েছে ত্রুটিগুলি ক্যাপচার করার জন্য দুর্ঘটনা ছাড়াই। এবং `$?` ভেরিয়েবল আপনাকে জানায় যে শেষ অপারেশন সফল ছিল কিনা। এগুলি হাতের কাছের সরঞ্জাম, যদিও একটি মজবুত `try-catch` এর তুলনায় একটু কম পরিষ্কার।

## আরও দেখুন
- [about_Try_Catch_Finally](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_try_catch_finally?view=powershell-7.2)
