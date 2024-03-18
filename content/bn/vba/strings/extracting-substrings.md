---
changelog:
- 2024-03-17, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-17 17:48:29.181246-06:00
description: "Visual Basic for Applications (VBA) \u098F \u09B8\u09BE\u09AC\u09B8\u09CD\
  \u099F\u09CD\u09B0\u09BF\u0982 \u09AC\u09C7\u09B0 \u0995\u09B0\u09BE \u09AE\u09BE\
  \u09A8\u09C7 \u09A8\u09BF\u09B0\u09CD\u09A6\u09BF\u09B7\u09CD\u099F \u09B6\u09B0\
  \u09CD\u09A4 \u0985\u09A8\u09C1\u09AF\u09BE\u09AF\u09BC\u09C0 \u098F\u0995\u099F\
  \u09BF \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u09A5\u09C7\u0995\u09C7 \u09A8\
  \u09BF\u09B0\u09CD\u09A6\u09BF\u09B7\u09CD\u099F \u0985\u0982\u09B6 \u09AA\u09C3\
  \u09A5\u0995 \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\
  \u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u09A1\u09C7\u099F\u09BE\u2026"
lastmod: '2024-03-17T18:47:43.843099-06:00'
model: gpt-4-0125-preview
summary: "Visual Basic for Applications (VBA) \u098F \u09B8\u09BE\u09AC\u09B8\u09CD\
  \u099F\u09CD\u09B0\u09BF\u0982 \u09AC\u09C7\u09B0 \u0995\u09B0\u09BE \u09AE\u09BE\
  \u09A8\u09C7 \u09A8\u09BF\u09B0\u09CD\u09A6\u09BF\u09B7\u09CD\u099F \u09B6\u09B0\
  \u09CD\u09A4 \u0985\u09A8\u09C1\u09AF\u09BE\u09AF\u09BC\u09C0 \u098F\u0995\u099F\
  \u09BF \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u09A5\u09C7\u0995\u09C7 \u09A8\
  \u09BF\u09B0\u09CD\u09A6\u09BF\u09B7\u09CD\u099F \u0985\u0982\u09B6 \u09AA\u09C3\
  \u09A5\u0995 \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\
  \u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u09A1\u09C7\u099F\u09BE\u2026"
title: "\u09B8\u09BE\u09AC\u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u09AC\u09C7\u09B0\
  \ \u0995\u09B0\u09BE"
---

{{< edit_this_page >}}

## কি এবং কেন?

Visual Basic for Applications (VBA) এ সাবস্ট্রিং বের করা মানে নির্দিষ্ট শর্ত অনুযায়ী একটি স্ট্রিং থেকে নির্দিষ্ট অংশ পৃথক করা। প্রোগ্রামাররা ডেটা পার্সিং, ভ্যালিডেশন, এবং ফর্ম্যাটিং এর মত কাজের জন্য এটি করে থাকেন, যেখানে মৌখিক ডেটা থেকে তথ্য ম্যানিপুলেট এবং সংগ্রহ করা অপরিহার্য।

## কিভাবে:

VBA এ, আপনি সাধারণত `Mid`, `Left`, এবং `Right` ফাংশনগুলি ব্যবহার করে সাবস্ট্রিং বের করেন। নিম্নে, আমরা উদাহরণের সাথে এই ফাংশনগুলি সম্পর্কে আলোচনা করি:

1. **Mid**: নির্দিষ্ট একটি অবস্থান থেকে শুরু করে একটি স্ট্রিং থেকে সাবস্ট্রিং বের করে।
   ```basic
   Dim exampleString As String
   exampleString = "Hello World"
   Dim result As String
   result = Mid(exampleString, 7, 5)
   Debug.Print result  ' আউটপুট: World
   ```

2. **Left**: একটি স্ট্রিং এর বাম পাশ থেকে, নির্দিষ্ট সংখ্যক অক্ষর পর্যন্ত একটি সাবস্ট্রিং বের করে।
   ```basic
   Dim exampleString As String
   exampleString = "Hello World"
   Dim result As String
   result = Left(exampleString, 5)
   Debug.Print result  ' আউটপুট: Hello
   ```

3. **Right**: একটি স্ট্রিং এর ডান পাশ থেকে, নির্দিষ্ট সংখ্যক অক্ষর পর্যন্ত একটি সাবস্ট্রিং বের করে।
   ```basic
   Dim exampleString As String
   exampleString = "Hello World"
   Dim result As String
   result = Right(exampleString, 5)
   Debug.Print result  ' আউটপুট: World
   ```

এই মৌলিক ফাংশনগুলি VBA তে সাবস্ট্রিং বের করার ভিত্তি তৈরি করে, স্ট্রিং ম্যানিপুলেশনের প্রতি শক্তিশালী ও সহজ প্রক্রিয়া সরবরাহ করে।

## গভীর ডুব:

প্রোগ্রামিংয়ে স্ট্রিং ম্যানিপুলেট করার ক্ষমতা ঐতিহাসিকভাবে অপরিহার্য ছিল, বিশেষ করে BASIC (VBA এর পূর্বসূরি) ছিল ব্যক্তিগত কম্পিউটিং এর প্রথম দিনগুলিতে এই ক্ষমতা প্রদান করার মধ্যে একটি। VBA তে `Mid`, `Left`, এবং `Right` ফাংশনগুলি এই উত্তরাধিকারকে ধারণ করে, আধুনিক প্রোগ্রামারদের জন্য সরল ইন্টারফেস সরবরাহ করে।

যদিও এই ফাংশনগুলি অনেক কাজের জন্য খুবই কার্যকর, নতুন ভাষাগুলিতে নিয়মিত এক্সপ্রেশনের উদ্ভব টেক্সটের সাথে আরও শক্তিশালী এবং নমনীয় উপায় প্রদান করেছে। সত্ত্বেও, পারম্পরিক VBA সাবস্ট্রিং ফাংশনগুলির তাত্ক্ষণিক সরলতা এবং প্রাপ্যতা তাদের দ্রুত কাজের জন্য এবং প্রোগ্রামিংয়ে নতুনদের জন্য একদম উপযুক্ত করে তোলে। 

স্ট্রিংয়ের মধ্যে আরও জটিল পার্সিং এবং অনুসন্ধান অপারেশনের জন্য, VBA এছাড়াও `Like` অপারেটরের মাধ্যমে প্যাটার্ন ম্যাচিং এবং `VBScript.RegExp` অবজেক্টের মাধ্যমে নিয়মিত এক্সপ্রেশন সমর্থন করে, যদিও এগুলি কার্যকরভাবে ব্যবহার করার জন্য একটু বেশি সেটআপ এবং বোঝার প্রয়োজন। যদিও এই সরঞ্জামগুলি আরও বেশি শক্তি প্রদান করে, `Mid`, `Left`, এবং `Right` এর সরল প্রকৃতি তাদের অনেক VBA প্রোগ্রামে অব্যাহত গুরুত্ব এবং উপযোগিতা নিশ্চিত করে।
