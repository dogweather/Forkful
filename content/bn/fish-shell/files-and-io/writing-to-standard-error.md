---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:42:50.625907-06:00
description: "Fish Shell-\u098F \u09B8\u09CD\u099F\u09CD\u09AF\u09BE\u09A8\u09CD\u09A1\
  \u09BE\u09B0\u09CD\u09A1 \u098F\u09B0\u09B0 (stderr) \u09B2\u09BF\u0996\u09BE \u09AE\
  \u09BE\u09A8\u09C7 \u09B9\u099A\u09CD\u099B\u09C7 \u09B8\u09CD\u099F\u09CD\u09AF\
  \u09BE\u09A8\u09CD\u09A1\u09BE\u09B0\u09CD\u09A1 \u0986\u0989\u099F\u09AA\u09C1\u099F\
  \ (stdout) \u09A5\u09C7\u0995\u09C7 \u0986\u09B2\u09BE\u09A6\u09BE \u0995\u09B0\u09C7\
  \ \u09A4\u09CD\u09B0\u09C1\u099F\u09BF \u09AC\u09BE\u09B0\u09CD\u09A4\u09BE \u0985\
  \u09A5\u09AC\u09BE \u09A1\u09BE\u09DF\u09BE\u0997\u09A8\u09B8\u09CD\u099F\u09BF\u0995\
  \u09CD\u09B8 \u09A8\u09BF\u09B0\u09CD\u09A6\u09C7\u09B6 \u0995\u09B0\u09BE\u0964\
  \u2026"
lastmod: '2024-03-17T18:47:44.514863-06:00'
model: gpt-4-0125-preview
summary: "Fish Shell-\u098F \u09B8\u09CD\u099F\u09CD\u09AF\u09BE\u09A8\u09CD\u09A1\
  \u09BE\u09B0\u09CD\u09A1 \u098F\u09B0\u09B0 (stderr) \u09B2\u09BF\u0996\u09BE \u09AE\
  \u09BE\u09A8\u09C7 \u09B9\u099A\u09CD\u099B\u09C7 \u09B8\u09CD\u099F\u09CD\u09AF\
  \u09BE\u09A8\u09CD\u09A1\u09BE\u09B0\u09CD\u09A1 \u0986\u0989\u099F\u09AA\u09C1\u099F\
  \ (stdout) \u09A5\u09C7\u0995\u09C7 \u0986\u09B2\u09BE\u09A6\u09BE \u0995\u09B0\u09C7\
  \ \u09A4\u09CD\u09B0\u09C1\u099F\u09BF \u09AC\u09BE\u09B0\u09CD\u09A4\u09BE \u0985\
  \u09A5\u09AC\u09BE \u09A1\u09BE\u09DF\u09BE\u0997\u09A8\u09B8\u09CD\u099F\u09BF\u0995\
  \u09CD\u09B8 \u09A8\u09BF\u09B0\u09CD\u09A6\u09C7\u09B6 \u0995\u09B0\u09BE\u0964\
  \ \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE\
  \ \u098F\u099F\u09BF \u0995\u09B0\u09C7 \u09A5\u09BE\u0995\u09C7\u09A8 \u09AF\u09BE\
  \u09A4\u09C7 \u09A4\u09CD\u09B0\u09C1\u099F\u09BF \u09A4\u09A5\u09CD\u09AF \u09B8\
  \u09B9\u099C\u09C7 \u099A\u09BF\u09A8\u09A4\u09C7, \u09AA\u09B0\u09BF\u099A\u09BE\
  \u09B2\u09A8\u09BE \u0985\u09A5\u09AC\u09BE \u09AA\u09C1\u09A8\u0983\u09A8\u09BF\
  \u09B0\u09CD\u09A6\u09C7\u09B6 \u0995\u09B0\u09BE \u09AF\u09BE\u09AF\u09BC, \u098F\
  \u09A4\u09C7 \u09B8\u09B9\u099C\u09C7 \u09A1\u09BF\u09AC\u09BE\u0997\u09BF\u0982\
  \ \u098F\u09AC\u0982 \u09B2\u0997\u09BF\u0982 \u09AA\u09CD\u09B0\u0995\u09CD\u09B0\
  \u09BF\u09AF\u09BC\u09BE \u0986\u09B0\u09CB \u09A8\u09BF\u09B0\u09CD\u09AC\u09BF\
  \u0998\u09CD\u09A8 \u09B9\u09AF\u09BC\u0964."
title: "\u09B8\u09CD\u099F\u09CD\u09AF\u09BE\u09A8\u09CD\u09A1\u09BE\u09B0\u09CD\u09A1\
  \ \u098F\u09B0\u09B0\u09C7 \u09B2\u09BF\u0996\u09A8"
weight: 25
---

## কিভাবে:
Fish Shell-এ আপনি `>&2` ব্যবহার করে আপনার আউটপুট রিডিরেক্ট করে stderr-এ লিখতে পারেন। একটি মৌলিক উদাহরণ হল:

```fish
echo "এটি একটি ত্রুটি বার্তা" >&2
```

এই কমান্ডটি কেবল স্ট্যান্ডার্ড আউটপুটের পরিবর্তে ত্রুটি বার্তাটি stderr-এ ইকো করে। যদি আপনি একটি স্ক্রিপ্ট লিখতে চান যেটি নিয়মিত এবং ত্রুটি বার্তা উভয়ই আউটপুট করে, আপনি এইরকম কিছু করতে পারেন:

```fish
echo "প্রক্রিয়া শুরু"
echo "একটি ত্রুটি ঘটেছে" >&2
echo "প্রক্রিয়া সম্পূর্ণ"
```

যদি আপনি স্ক্রিপ্ট চালান এবং stderr একটি ফাইলে রিডিরেক্ট করেন, সেক্ষেত্রে স্যাম্পল আউটপুট হবে:

```
প্রক্রিয়া শুরু
প্রক্রিয়া সম্পূর্ণ
```

ত্রুটি বার্তাটি স্ট্যান্ডার্ড আউটপুটে উপস্থিত হবে না বরং তা stderr রিডিরেক্ট করা ফাইলে পাওয়া যাবে।

অধিক জটিল ত্রুটি সম্পর্কিত হ্যান্ডলিং বা লগিং পরিস্থিতির জন্য, Fish বিশেষায়িত লাইব্রেরি সহ সর্বদা উপলব্ধ নেই। তবে, আপনি বাহ্যিক টুলস অথবা ফাংশন লেখার মাধ্যমে সহায়তা নিতে পারেন। উদাহরণ স্বরূপ, একটি সাধারণ লগিং ফাংশন এরকম দেখাতে পারে:

```fish
function log_error
    echo $argv >&2
end

log_error "এটি একটি উন্নত ত্রুটি বার্তা"
```

`log_error` এই ফাংশনটি আপনার যেকোনো স্ট্রিং নেবে এবং তা stderr-এ লিখবে। এরকম ফাংশন ব্যবহার আপনার ত্রুটি হাতের ভল্যুম পরিষ্কার এবং ধারাবাহিক রাখতে সাহায্য করবে।
