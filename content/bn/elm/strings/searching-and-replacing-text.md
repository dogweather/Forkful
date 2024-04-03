---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:16:05.375765-06:00
description: "\u099F\u09C7\u0995\u09CD\u09B8\u099F \u0996\u09C1\u0981\u099C\u09C7\
  \ \u09AA\u09BE\u0993\u09AF\u09BC\u09BE \u098F\u09AC\u0982 \u09AA\u09CD\u09B0\u09A4\
  \u09BF\u09B8\u09CD\u09A5\u09BE\u09AA\u09A8 \u0986\u09AA\u09A8\u09BE\u0995\u09C7\
  \ \u09A8\u09BF\u09B0\u09CD\u09A6\u09BF\u09B7\u09CD\u099F \u09B8\u09CD\u099F\u09CD\
  \u09B0\u09BF\u0982\u0997\u09C1\u09B2\u09BF \u0996\u09C1\u0981\u099C\u09C7 \u09AC\
  \u09C7\u09B0 \u0995\u09B0\u09C7 \u09A4\u09BE \u0985\u09A8\u09CD\u09AF \u0995\u09BF\
  \u099B\u09C1\u09B0 \u09B8\u09BE\u09A5\u09C7 \u09AC\u09A6\u09B2\u09C7 \u09A6\u09C7\
  \u0993\u09AF\u09BC\u09BE\u09B0 \u0985\u09A8\u09C1\u09AE\u09A4\u09BF \u09A6\u09C7\
  \u09AF\u09BC\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\
  \u09B0\u09BE \u099F\u09BE\u0987\u09AA\u09CB \u09B8\u0982\u09B6\u09CB\u09A7\u09A8\
  \ \u0995\u09B0\u09BE\u2026"
lastmod: '2024-03-17T18:47:43.933279-06:00'
model: gpt-4-0125-preview
summary: "\u099F\u09C7\u0995\u09CD\u09B8\u099F \u0996\u09C1\u0981\u099C\u09C7 \u09AA\
  \u09BE\u0993\u09AF\u09BC\u09BE \u098F\u09AC\u0982 \u09AA\u09CD\u09B0\u09A4\u09BF\
  \u09B8\u09CD\u09A5\u09BE\u09AA\u09A8 \u0986\u09AA\u09A8\u09BE\u0995\u09C7 \u09A8\
  \u09BF\u09B0\u09CD\u09A6\u09BF\u09B7\u09CD\u099F \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\
  \u0982\u0997\u09C1\u09B2\u09BF \u0996\u09C1\u0981\u099C\u09C7 \u09AC\u09C7\u09B0\
  \ \u0995\u09B0\u09C7 \u09A4\u09BE \u0985\u09A8\u09CD\u09AF \u0995\u09BF\u099B\u09C1\
  \u09B0 \u09B8\u09BE\u09A5\u09C7 \u09AC\u09A6\u09B2\u09C7 \u09A6\u09C7\u0993\u09AF\
  \u09BC\u09BE\u09B0 \u0985\u09A8\u09C1\u09AE\u09A4\u09BF \u09A6\u09C7\u09AF\u09BC\
  \u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE\
  \ \u099F\u09BE\u0987\u09AA\u09CB \u09B8\u0982\u09B6\u09CB\u09A7\u09A8 \u0995\u09B0\
  \u09BE \u09A5\u09C7\u0995\u09C7 \u0995\u09CB\u09A1 \u09A6\u0995\u09CD\u09B7\u09A4\
  \u09BE\u09B0 \u09B8\u09BE\u09A5\u09C7 \u09B0\u09BF\u09AB\u09CD\u09AF\u09BE\u0995\
  \u09CD\u099F\u09B0\u09BF\u0982 \u0995\u09B0\u09BE \u09AA\u09B0\u09CD\u09AF\u09A8\
  \u09CD\u09A4 \u09B8\u09AC \u0995\u09BE\u099C\u09C7 \u098F\u099F\u09BF \u09AC\u09CD\
  \u09AF\u09AC\u09B9\u09BE\u09B0 \u0995\u09B0\u09C7\u0964."
title: "\u099F\u09C7\u0995\u09CD\u09B8\u099F \u0985\u09A8\u09C1\u09B8\u09A8\u09CD\u09A7\
  \u09BE\u09A8 \u098F\u09AC\u0982 \u09AA\u09CD\u09B0\u09A4\u09BF\u09B8\u09CD\u09A5\
  \u09BE\u09AA\u09A8"
weight: 10
---

## কিভাবে:
Elm-এ, আপনি একটি স্ট্রিং-এর অংশগুলি প্রতিস্থাপন করার জন্য `String` মডিউল ব্যবহার করতে পারেন। আসুন দেখি এটি কিভাবে কাজ করে:

```Elm
import String

replaceExample : String
replaceExample =
    String.replace "cat" "dog" "The cat sat on the mat"

-- আউটপুট হবে: "The dog sat on the mat"
```

## গভীর ডুব
Elm-এ টেক্সট খোঁজা এবং প্রতিস্থাপন করার পদ্ধতি অত্যন্ত সোজা এবং অন্যান্য ফাংশনাল ভাষার সাথে অনুরূপ। এটি ডিফল্টভাবে কোর ভাষায় এই কাজের জন্য নিয়মিত এক্সপ্রেশনগুলি ব্যবহার করে না, JavaScript এর মতো ভাষাগুলির বিপরীতে। এই সরলতা নকশা দ্বারা নির্ধারিত, যাতে Elm-এর নির্ভরযোগ্যতা এবং রক্ষণাবেক্ষণের লক্ষ্যগুলি বজায় থাকে।

ইতিহাসে দেখা যায়, Elm সাধারণ কাজগুলি পরিচালনা করার জন্য একটি শক্তিশালী অন্তর্নির্মিত ফাংশনের সেট প্রদানের লক্ষ্যে রয়েছে, এবং অনুসন্ধান-প্রতিস্থাপন কোনো ব্যতিক্রম নয়। Elm-এর `String` মডিউল ভাষাটির প্রথম দিনগুলিতে থেকে আছে, যদিও ভাষাটির বিকাশের মধ্যে এটির পরিবর্তন হয়েছে।

`String.replace` ফাংশনটি ব্যবহার করার বিকল্পের মধ্যে নিজের একটি অনুসন্ধান এবং প্রতিস্থাপন যুক্তিগুলি লেখা অথবা Elm-এর স্ট্রিং ম্যানিপুলেশন ক্ষমতাগুলি বাড়ানোর জন্য অতিরিক্ত প্যাকেজ যুক্ত করা অন্তর্ভুক্ত থাকতে পারে, যেমন regex-ভিত্তিক অনুসন্ধান।

বাস্তবায়নের দিক থেকে দেখলে, Elm-এর `String.replace` ফাংশনটি শুদ্ধ। অর্থাৎ এটি সবসময় নির্দিষ্ট ইনপুটের জন্য একই আউটপুট উৎপাদন করে এবং এর কোনো পার্শ্ব প্রভাব নেই - এটি Elm-এর নকশার একটি কোর নীতি। এটি অভ্যন্তরে একটি কার্যকর অ্যালগরিদম ব্যবহার করে, কিন্তু ভাষা জটিলতাকে সুন্দরভাবে অপসারিত করে যাতে আপনি ছোটখাটো বিষয়গুলো নিয়ে ঘাম না ঝরিয়ে কোডিংয়ে মনোযোগ দিতে পারেন।

## দেখুন এছাড়াও
- Elm `String` মডিউলের ডকুমেন্টেশন: https://package.elm-lang.org/packages/elm/core/latest/String
- elm/regex প্যাকেজ ব্যবহার করে Elm-এ regex-এর প্রবর্তন: https://package.elm-lang.org/packages/elm/regex/latest
- ফাংশনাল প্রোগ্রামিং-এ স্ট্রিং প্রসেসিং: https://en.wikipedia.org/wiki/Functional_programming
