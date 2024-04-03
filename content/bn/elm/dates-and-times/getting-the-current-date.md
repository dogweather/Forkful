---
changelog:
- 2024-03-17, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-17 17:48:38.639923-06:00
description: "Elm-\u098F \u09AC\u09B0\u09CD\u09A4\u09AE\u09BE\u09A8 \u09A4\u09BE\u09B0\
  \u09BF\u0996 \u09AA\u09C7\u09A4\u09C7 \u09AE\u09BE\u09A8\u09C7 \u09B8\u09BF\u09B8\
  \u09CD\u099F\u09C7\u09AE \u09A5\u09C7\u0995\u09C7 \u09AC\u09B0\u09CD\u09A4\u09AE\
  \u09BE\u09A8 \u0995\u09CD\u09AF\u09BE\u09B2\u09C7\u09A8\u09CD\u09A1\u09BE\u09B0\
  \ \u09A4\u09BE\u09B0\u09BF\u0996 \u0986\u09A8\u09BE\u0964 \u0986\u09AE\u09B0\u09BE\
  \ \u0998\u099F\u09A8\u09BE\u09AC\u09B2\u09C0\u09B0 \u09B8\u09AE\u09AF\u09BC \u099A\
  \u09BF\u09B9\u09CD\u09A8\u09BF\u09A4 \u0995\u09B0\u09BE, \u0995\u09BE\u09B0\u09CD\
  \u09AF\u0995\u09CD\u09B0\u09AE \u09A8\u09BF\u09B0\u09CD\u09A7\u09BE\u09B0\u09A3\
  , \u0985\u09A5\u09AC\u09BE \u09B8\u09AE\u09AF\u09BC\u09C7\u09B0 \u09A6\u09C8\u09B0\
  \u09CD\u0998\u09CD\u09AF \u099F\u09CD\u09B0\u09CD\u09AF\u09BE\u0995\u2026"
lastmod: '2024-03-17T18:47:43.959343-06:00'
model: gpt-4-0125-preview
summary: "Elm-\u098F \u09AC\u09B0\u09CD\u09A4\u09AE\u09BE\u09A8 \u09A4\u09BE\u09B0\
  \u09BF\u0996 \u09AA\u09C7\u09A4\u09C7 \u09AE\u09BE\u09A8\u09C7 \u09B8\u09BF\u09B8\
  \u09CD\u099F\u09C7\u09AE \u09A5\u09C7\u0995\u09C7 \u09AC\u09B0\u09CD\u09A4\u09AE\
  \u09BE\u09A8 \u0995\u09CD\u09AF\u09BE\u09B2\u09C7\u09A8\u09CD\u09A1\u09BE\u09B0\
  \ \u09A4\u09BE\u09B0\u09BF\u0996 \u0986\u09A8\u09BE\u0964 \u0986\u09AE\u09B0\u09BE\
  \ \u0998\u099F\u09A8\u09BE\u09AC\u09B2\u09C0\u09B0 \u09B8\u09AE\u09AF\u09BC \u099A\
  \u09BF\u09B9\u09CD\u09A8\u09BF\u09A4 \u0995\u09B0\u09BE, \u0995\u09BE\u09B0\u09CD\
  \u09AF\u0995\u09CD\u09B0\u09AE \u09A8\u09BF\u09B0\u09CD\u09A7\u09BE\u09B0\u09A3\
  , \u0985\u09A5\u09AC\u09BE \u09B8\u09AE\u09AF\u09BC\u09C7\u09B0 \u09A6\u09C8\u09B0\
  \u09CD\u0998\u09CD\u09AF \u099F\u09CD\u09B0\u09CD\u09AF\u09BE\u0995 \u0995\u09B0\
  \u09BE\u09B0 \u099C\u09A8\u09CD\u09AF \u098F\u099F\u09BF \u0995\u09B0\u09BF\u0964\
  ."
title: "\u09AC\u09B0\u09CD\u09A4\u09AE\u09BE\u09A8 \u09A4\u09BE\u09B0\u09BF\u0996\
  \ \u09AA\u09C7\u09A4\u09C7"
weight: 29
---

## কিভাবে:
Elm তারিখগুলোকে `Time` মডিউলের মাধ্যমে নিয়ন্ত্রণ করে। আপনি বর্তমান সময়কে POSIX টাইমস্ট্যাম্প হিসেবে পাবেন, এরপর তারিখে রূপান্তর করবেন।

```Elm
import Browser
import Task
import Time

type Msg = GetCurrentTime Time.Posix

update : Msg -> Model -> (Model, Cmd Msg)
update msg model =
    case msg of
        GetCurrentTime posixTime ->
            let
                -- POSIX সময়কে তারিখ রেকর্ডে রূপান্তর করুন
                date = Time.toDate posixTime
            in
            -- আপনার মডেলকে যথাযথভাবে আপডেট করুন এখানে
            ({ model | date = date }, Cmd.none)

-- বর্তমান সময় পাওয়ার উদ্যোগ নেওয়া
getCurrentTime : Cmd Msg
getCurrentTime =
    Task.perform GetCurrentTime Time.now

-- উদাহরণ আউটপুট:
-- date { year = 2023, month = Mar, day = 26 }
```

## গভীর ডুব
পুরানো ওয়েব ভাষায়, তারিখ পাওয়া এক লাইনের কোডের মতো সহজ। Elm ভিন্ন। এটি Elm আর্কিটেকচারের মাধ্যমে বর্তমান সময় প্রাপ্তির মতো পার্শ্ব-প্রভাবগুলিকে স্পষ্ট করে তোলে। এটি কোডের পবিত্রতা এবং রক্ষণাবেক্ষণকে উত্সাহিত করে।

বিকল্পগুলি তৃতীয় পক্ষের প্যাকেজ ব্যবহার করা বা আপনার সার্ভার কোডে তারিখগুলো হ্যান্ডেল করে Elm-এ ফ্ল্যাগ বা পোর্টগুলির মাধ্যমে পাস করা অন্তর্ভুক্ত।

ইমপ্লিমেন্টেশনের দিক থেকে, Elm-এর `Time.now` POSIX টাইমস্ট্যাম্প হিসেবে সময় পায় (Unix epoch থেকে মিলিসেকেন্ড)। এটি সময়ক্ষেত্র-নিরপেক্ষ, এবং আপনি এটিকে `Time` মডিউল থেকে ফাংশন ব্যবহার করে প্রয়োজনমতো ফর্ম্যাট করতে পারেন।

## দেখুনও
- [Elm Time ডকুমেন্টেশন](https://package.elm-lang.org/packages/elm/time/latest/)
- [Elm-এর কমান্ড ও সাবস্ক্রিপশনের গাইড](https://guide.elm-lang.org/effects/)
