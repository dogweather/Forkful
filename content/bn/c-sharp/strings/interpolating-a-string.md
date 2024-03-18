---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 17:51:11.538717-06:00
description: "C# \u098F \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u0987\u09A8\u09CD\
  \u099F\u09BE\u09B0\u09AA\u09CB\u09B2\u09C7\u09B6\u09A8 \u0986\u09AA\u09A8\u09BE\u0995\
  \u09C7 \u098F\u0995\u099F\u09BF \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u09B2\
  \u09BF\u099F\u09BE\u09B0\u09BE\u09B2\u09C7\u09B0 \u09AE\u09A7\u09CD\u09AF\u09C7\
  \ \u098F\u0995\u09CD\u09B8\u09AA\u09CD\u09B0\u09C7\u09B6\u09A8 \u09AF\u09C1\u0995\
  \u09CD\u09A4 \u0995\u09B0\u09C7 \u09A8\u09A4\u09C1\u09A8 \u098F\u0995\u099F\u09BF\
  \ \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u09A4\u09C8\u09B0\u09BF \u0995\u09B0\
  \u09BE\u09B0 \u0985\u09A8\u09C1\u09AE\u09A4\u09BF \u09A6\u09C7\u09DF, \u09AF\u09BE\
  \ \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u09AB\u09B0\u09CD\u09AE\u09C7\u099F\
  \ \u098F\u09AC\u0982 \u09B8\u0982\u09AF\u09C1\u0995\u09CD\u09A4\u09BF\u2026"
lastmod: '2024-03-17T18:47:44.023272-06:00'
model: gpt-4-0125-preview
summary: "C# \u098F \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u0987\u09A8\u09CD\u099F\
  \u09BE\u09B0\u09AA\u09CB\u09B2\u09C7\u09B6\u09A8 \u0986\u09AA\u09A8\u09BE\u0995\u09C7\
  \ \u098F\u0995\u099F\u09BF \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u09B2\u09BF\
  \u099F\u09BE\u09B0\u09BE\u09B2\u09C7\u09B0 \u09AE\u09A7\u09CD\u09AF\u09C7 \u098F\
  \u0995\u09CD\u09B8\u09AA\u09CD\u09B0\u09C7\u09B6\u09A8 \u09AF\u09C1\u0995\u09CD\u09A4\
  \ \u0995\u09B0\u09C7 \u09A8\u09A4\u09C1\u09A8 \u098F\u0995\u099F\u09BF \u09B8\u09CD\
  \u099F\u09CD\u09B0\u09BF\u0982 \u09A4\u09C8\u09B0\u09BF \u0995\u09B0\u09BE\u09B0\
  \ \u0985\u09A8\u09C1\u09AE\u09A4\u09BF \u09A6\u09C7\u09DF, \u09AF\u09BE \u09B8\u09CD\
  \u099F\u09CD\u09B0\u09BF\u0982 \u09AB\u09B0\u09CD\u09AE\u09C7\u099F \u098F\u09AC\
  \u0982 \u09B8\u0982\u09AF\u09C1\u0995\u09CD\u09A4\u09BF\u2026"
title: "\u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u0987\u09A8\u09CD\u099F\u09BE\u09B0\
  \u09AA\u09CB\u09B2\u09C7\u099F \u0995\u09B0\u09BE"
---

{{< edit_this_page >}}

## কি এবং কেন?
C# এ স্ট্রিং ইন্টারপোলেশন আপনাকে একটি স্ট্রিং লিটারালের মধ্যে এক্সপ্রেশন যুক্ত করে নতুন একটি স্ট্রিং তৈরি করার অনুমতি দেয়, যা স্ট্রিং ফর্মেট এবং সংযুক্তি করা সহজ করে। প্রোগ্রামারগণ এই ফিচারটি ব্যবহার করেন কোড পাঠ্যগত এবং রক্ষণাবেক্ষণ উন্নতির জন্য, বিশেষ করে যখন তারা ডাইনামিক স্ট্রিং কনটেন্টের সাথে কাজ করে।

## কিভাবে:
C# এ, স্ট্রিং ইন্টারপোলেশনের প্রকাশ একটি ডলার চিহ্ন (`$`) দ্বারা চিহ্নিত হয় যা একটি স্ট্রিং লিটারালের পরে আসে। ভেরিয়েবল নাম অথবা এক্সপ্রেশনগুলি কার্লি ব্রেসেস (`{}`) এর মধ্যে বন্ধকৃত হয়।

```csharp
string name = "Jane";
int age = 28;
string interpolatedString = $"Hello, {name}! You are {age} years old.";
Console.WriteLine(interpolatedString);
// আউটপুট: Hello, Jane! You are 28 years old.
```

একটি জটিল উদাহরণে, আপনি কার্লি ব্রেসেসের মধ্যে অপারেশন বা মেথড কল করতে পারেন:

```csharp
double price = 19.99;
int quantity = 3;
string orderDetail = $"Total price: {price * quantity:C2}";
Console.WriteLine(orderDetail);
// আউটপুট: Total price: $59.97
```
কার্লি ব্রেসেসের মধ্যে `:C2` ফরম্যাট স্পেসিফায়ারটি সংখ্যাটিকে দুই দশমিক স্থানের সাথে একটি মুদ্রার ফরম্যাটে ফর্মেট করে।

আরও জটিল ফর্মেটিং অথবা লোকালাইজেশনের দৃশ্যপটে, আপনি `string.Format` মেথড অথবা Humanizer এর মতো লাইব্রেরিগুলি বিবেচনা করতে পারেন। Humanizer স্ট্রিং, ডেট, সময়, টাইমস্প্যান, নম্বর, এবং পরিমাণগুলিকে আরও মানববান্ধব ফরম্যাটে পরিচালনা এবং প্রদর্শন করতে পারে। নিচে একটি উদাহরণ দেওয়া হলো Humanizer ব্যবহার করে জটিল স্ট্রিং ম্যানিপুলেশনের। মনে রাখবেন যে Humanizer হল .NET স্ট্যান্ডার্ড লাইব্রেরির অংশ নয় এবং এর জন্য NuGet প্যাকেজ `Humanizer` ইনস্টল করা প্রয়োজন।

প্রথমে, Humanizer ইনস্টল করুন ভায়া NuGet:

```
Install-Package Humanizer
```

তারপর, আপনি এটি এরকম ব্যবহার করতে পারেন:

```csharp
using Humanizer;

int dayDifference = 5;
string humanized = $"The event was {dayDifference} days ago.".Humanize();
Console.WriteLine(humanized);
// কনফিগারেশন এবং কালচার অনুযায়ী, সম্ভাব্য আউটপুট: ইভেন্টটি 5 দিন আগে ছিল।
```

এই উদাহরণটি মৌলিক ব্যবহার প্রদর্শন করে। Humanizer স্ট্রিং, ডেট, নম্বর, এবং আরো বিস্তর কার্যকারিতা প্রদান করে, যা আপনার অ্যাপ্লিকেশনগুলিকে আরও অ্যাকসেসেবল এবং ইন্টুইটিভ করে তোলে।
