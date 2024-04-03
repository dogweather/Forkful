---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 17:51:18.222921-06:00
description: "\u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u0987\u09A8\u09CD\u099F\u09BE\
  \u09B0\u09AA\u09CB\u09B2\u09C7\u09B6\u09A8 \u0986\u09AA\u09A8\u09BE\u0995\u09C7\
  \ \u098F\u0995\u099F\u09BF \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982\u09DF\u09C7\
  \u09B0 \u09AE\u09A7\u09CD\u09AF\u09C7 \u09B8\u09B0\u09BE\u09B8\u09B0\u09BF \u09AD\
  \u09C7\u09B0\u09BF\u09DF\u09C7\u09AC\u09B2 \u09AF\u09C1\u0995\u09CD\u09A4 \u0995\
  \u09B0\u09A4\u09C7 \u09A6\u09C7\u09AF\u09BC, \u09AF\u09BE\u09A4\u09C7 \u098F\u099F\
  \u09BF \u09B8\u09BE\u09A7\u09BE\u09B0\u09A3 \u099F\u09C7\u0995\u09CD\u09B8\u099F\
  \u09C7\u09B0 \u09AE\u09A4\u09CB \u09AA\u09DC\u09BE \u09AF\u09BE\u09DF\u0964 \u09AA\
  \u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u098F\u099F\
  \u09BF \u0997\u09A0\u09A8\u09AE\u09C2\u09B2\u0995\u2026"
lastmod: '2024-03-17T18:47:43.934237-06:00'
model: gpt-4-0125-preview
summary: "\u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u0987\u09A8\u09CD\u099F\u09BE\
  \u09B0\u09AA\u09CB\u09B2\u09C7\u09B6\u09A8 \u0986\u09AA\u09A8\u09BE\u0995\u09C7\
  \ \u098F\u0995\u099F\u09BF \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982\u09DF\u09C7\
  \u09B0 \u09AE\u09A7\u09CD\u09AF\u09C7 \u09B8\u09B0\u09BE\u09B8\u09B0\u09BF \u09AD\
  \u09C7\u09B0\u09BF\u09DF\u09C7\u09AC\u09B2 \u09AF\u09C1\u0995\u09CD\u09A4 \u0995\
  \u09B0\u09A4\u09C7 \u09A6\u09C7\u09AF\u09BC, \u09AF\u09BE\u09A4\u09C7 \u098F\u099F\
  \u09BF \u09B8\u09BE\u09A7\u09BE\u09B0\u09A3 \u099F\u09C7\u0995\u09CD\u09B8\u099F\
  \u09C7\u09B0 \u09AE\u09A4\u09CB \u09AA\u09DC\u09BE \u09AF\u09BE\u09DF\u0964 \u09AA\
  \u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u098F\u099F\
  \u09BF \u0997\u09A0\u09A8\u09AE\u09C2\u09B2\u0995 \u09B8\u09CD\u099F\u09CD\u09B0\
  \u09BF\u0982\u09B8 \u09A4\u09C8\u09B0\u09BF \u0995\u09B0\u09A4\u09C7, \u099F\u09C7\
  \u0995\u09CD\u09B8\u099F\u09C7\u09B0 \u09AC\u09BF\u09AD\u09BF\u09A8\u09CD\u09A8\
  \ \u0985\u0982\u09B6 \u098F\u09AC\u0982 \u09AD\u09C7\u09B0\u09BF\u09DF\u09C7\u09AC\
  \u09B2\u09C7\u09B0 \u09AE\u09BE\u09A8\u0997\u09C1\u09B2\u09BF \u09B8\u09C1\u09A8\
  \u09CD\u09A6\u09B0\u09AD\u09BE\u09AC\u09C7 \u09AF\u09C1\u0995\u09CD\u09A4 \u0995\
  \u09B0\u09BE\u09B0 \u099C\u09A8\u09CD\u09AF \u09AC\u09CD\u09AF\u09AC\u09B9\u09BE\
  \u09B0 \u0995\u09B0\u09C7 \u09A5\u09BE\u0995\u09C7\u0964."
title: "\u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u0987\u09A8\u09CD\u099F\u09BE\u09B0\
  \u09AA\u09CB\u09B2\u09C7\u099F \u0995\u09B0\u09BE"
weight: 8
---

## কিভাবে:
Elm স্ট্রিংস জোড়া লাগাতে `++` অপারেটরকে ব্যবহার করে, যা আপনি ইন্টারপোলেশনের মতো আচরণের জন্য ব্যবহার করতে পারেন। এটি কোনো বিশেষ সিনট্যাক্স নয়; আপনাকে শুধু তাদের একত্রিত করতে হবে।

```Elm
name = "world"
greeting = "Hello, " ++ name ++ "!"

-- আউটপুট
"Hello, world!"
```

## গভীর ডুব
Elm, সাদাসিধাও এবং রক্ষণাবেক্ষণের উপর জোর দেয়া হয়েছে, অন্যান্য ভাষার মতো বিল্ট-ইন স্ট্রিং ইন্টারপোলেশন নেই। পরিবর্তে, আপনি স্ট্রিং যোগাযোগের জন্য `++` ব্যবহার করবেন। ঐতিহাসিকভাবে, স্ট্রিং ইন্টারপোলেশন প্রাথমিক কম্পিউটিং ভাষায় উত্তরণ করে এবং সময়ের সাথে সাথে আরও উন্নত হয়েছে। 

Elm এ উন্নত স্ট্রিংস তৈরি করতে ফাংশন ব্যবহার করা হতে পারে, অথবা যদি স্ট্রিংয়ের তালিকা নিয়ে কাজ করা হয় তাহলে `String.concat` বা `String.join` ফাংশনগুলি ব্যবহার করা যেতে পারে। ইন্টারপোলেশন সিনট্যাক্স অনুকরণ করতে কাস্টম ফাংশন তৈরি করা যেতে পারে, তবে নেটিভ সমর্থন যুক্ত ভাষাগুলিতে এগুলি ততটা পরিষ্কার হবে না।

অভ্যন্তরে, যখন আপনি স্ট্রিংগুলি যোগাযোগ করতে `++` ব্যবহার করছেন, Elm কার্যকরভাবে সংমিশ্রিত বিষয়বস্তু সহ একটি নতুন স্ট্রিং তৈরি করছে। উল্লেখ্য, বড় বা বহু স্ট্রিং নিয়ে `++` অপারেটরের ব্যবহার অতিমাত্রায় করা অন্যান্য ভাষার ইন্টারপোলেশন পদ্ধতির তুলনায় কম কার্যকর হতে পারে যেহেতু যোগাযোগের সময় স্ট্রিংগুলির পুনরাবৃত্তি কপি করা হতে পারে।

## দেখুন এছাড়াও
- Elm `String` মডিউল ডকুমেন্টেশন: https://package.elm-lang.org/packages/elm/core/latest/String
- Elm সিনট্যাক্স ওভারভিউ: https://elm-lang.org/docs/syntax
- Elm অপ্টিমাইজেশন টিপস: https://elm-lang.org/0.19.1/optimization
- Elm ডিসকোর্সে স্ট্রিং যোগাযোগ আলোচনা: https://discourse.elm-lang.org
