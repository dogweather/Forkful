---
changelog:
- 2024-03-17, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-17 17:45:29.806085-06:00
description: "\u09A6\u09C1\u099F\u09BF \u09A4\u09BE\u09B0\u09BF\u0996\u09C7\u09B0\
  \ \u09A4\u09C1\u09B2\u09A8\u09BE \u09AE\u09BE\u09A8\u09C7 \u09A4\u09BE\u09B0\u09BE\
  \ \u09B8\u09AE\u09BE\u09A8 \u0995\u09BF \u09A8\u09BE \u09A4\u09BE \u09AF\u09BE\u099A\
  \u09BE\u0987 \u0995\u09B0\u09BE \u0985\u09A5\u09AC\u09BE \u0995\u09CB\u09A8\u099F\
  \u09BF \u09AA\u09CD\u09B0\u09A5\u09AE \u0985\u09A5\u09AC\u09BE \u09B6\u09C7\u09B7\
  \u09C7 \u0986\u09B8\u09C7 \u09A4\u09BE \u09A8\u09BF\u09B0\u09CD\u09A7\u09BE\u09B0\
  \u09A3 \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\
  \u09AE\u09BE\u09B0\u09B0\u09BE \u098F\u0987 \u0995\u09BE\u099C \u0998\u099F\u09A8\
  \u09BE\u09AC\u09B2\u09C0 \u09AA\u09B0\u09BF\u099A\u09BE\u09B2\u09A8\u09BE, \u0995\
  \u09BE\u099C\u09C7\u09B0 \u09B8\u09AE\u09DF\u09B8\u09C2\u099A\u09BF\u2026"
lastmod: '2024-03-17T18:47:43.683890-06:00'
model: gpt-4-0125-preview
summary: "\u09A6\u09C1\u099F\u09BF \u09A4\u09BE\u09B0\u09BF\u0996\u09C7\u09B0 \u09A4\
  \u09C1\u09B2\u09A8\u09BE \u09AE\u09BE\u09A8\u09C7 \u09A4\u09BE\u09B0\u09BE \u09B8\
  \u09AE\u09BE\u09A8 \u0995\u09BF \u09A8\u09BE \u09A4\u09BE \u09AF\u09BE\u099A\u09BE\
  \u0987 \u0995\u09B0\u09BE \u0985\u09A5\u09AC\u09BE \u0995\u09CB\u09A8\u099F\u09BF\
  \ \u09AA\u09CD\u09B0\u09A5\u09AE \u0985\u09A5\u09AC\u09BE \u09B6\u09C7\u09B7\u09C7\
  \ \u0986\u09B8\u09C7 \u09A4\u09BE \u09A8\u09BF\u09B0\u09CD\u09A7\u09BE\u09B0\u09A3\
  \ \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\
  \u09BE\u09B0\u09B0\u09BE \u098F\u0987 \u0995\u09BE\u099C \u0998\u099F\u09A8\u09BE\
  \u09AC\u09B2\u09C0 \u09AA\u09B0\u09BF\u099A\u09BE\u09B2\u09A8\u09BE, \u0995\u09BE\
  \u099C\u09C7\u09B0 \u09B8\u09AE\u09DF\u09B8\u09C2\u099A\u09BF \u09B0\u09BE\u0996\
  \u09BE, \u0987\u09A8\u09AA\u09C1\u099F \u09AF\u09BE\u099A\u09BE\u0987 \u0985\u09A5\
  \u09AC\u09BE \u09B8\u09AE\u09DF\u0995\u09BE\u09B2 \u099F\u09CD\u09B0\u09CD\u09AF\
  \u09BE\u0995 \u0995\u09B0\u09BE\u09B0 \u099C\u09A8\u09CD\u09AF \u0995\u09B0\u09C7\
  \ \u09A5\u09BE\u0995\u09C7\u09A8\u0964."
title: "\u09A6\u09C1\u099F\u09BF \u09A4\u09BE\u09B0\u09BF\u0996 \u09A4\u09C1\u09B2\
  \u09A8\u09BE \u0995\u09B0\u09BE"
weight: 27
---

## কিভাবে:
Elixir তারিখ তুলনা খুবই সহজ করে দেয়। এখানে আজ এবং আগামীকাল তুলনার একটি উদাহরণ দেওয়া হল:

```elixir
{:ok, today} = Date.new(2023, 4, 1)
{:ok, tomorrow} = Date.new(2023, 4, 2)

# সমান কিনা তুলনা করা
Date.compare(today, today) # => :eq
# আউটপুট: :eq (সমান)

# কোনটি আগে?
Date.compare(today, tomorrow) # => :lt
# আউটপুট: :lt (কম)

# কোনটি পরে?
Date.compare(tomorrow, today) # => :gt
# আউটপুট: :gt (বেশি)
```

## গভীরে ডুব দিয়ে
ঐতিহাসিকভাবে, তারিখ তুলনা সবসময় প্রোগ্রামিং ভাষাগুলোতে অন্তর্ভুক্ত বৈশিষ্ট্য ছিল না, এবং প্রোগ্রামাররা ম্যানুয়ালি সেকেন্ড অথবা দিনে পার্থক্য গণনা করত। যাহোক, এলিক্সিরের স্ট্যান্ডার্ড লাইব্রেরি, `Date` মডিউল একটি `compare/2` ফাংশন নিয়ে আসে যা এই কাজটি সহজ করে দেয়।

Elixir মধ্যে সময় ব্যবস্থাপনার জন্য গভীরতর বিকল্প বিদ্যমান, যেমন `DateTime` মডিউল ব্যাবহার করা যায় সেকেন্ড অথবা মাইক্রোসেকেন্ড পর্যন্ত আরো নির্ভুল সময় তুলনার জন্য।

তারিখ তুলনা করার সময়, Elixir ক্যালেন্ডার সিস্টেমের জটিলতাগুলিকে সামলায়। এটি অধিবর্ষ, বিভিন্ন মাসের দৈর্ঘ্য এবং ভিন্ন ক্যালেন্ডার প্রকারগুলি সামলে নেওয়ার জন্য ভিত্তি হিসেবে Erlang `:calendar` মডিউলের উপর নির্ভর করে।

## দেখুনও
- Elixir Date মডিউল ডক্স: [https://hexdocs.pm/elixir/Date.html](https://hexdocs.pm/elixir/Date.html)
- Erlang ক্যালেন্ডার মডিউল: [http://erlang.org/doc/man/calendar.html](http://erlang.org/doc/man/calendar.html)
- Timex - Elixir এর তারিখ এবং সময়ের জন্য একটি লাইব্রেরি: [https://hexdocs.pm/timex/Timex.html](https://hexdocs.pm/timex/Timex.html)
