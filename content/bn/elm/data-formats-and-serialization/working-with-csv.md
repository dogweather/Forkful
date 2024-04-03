---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:27:56.903535-06:00
description: "CSV (Comma Separated Values) \u09A8\u09BF\u09AF\u09BC\u09C7 \u0995\u09BE\
  \u099C \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\u09C7 \u099F\u09C7\u09AC\u09BF\u09B2\
  \u09BE\u09B0 \u09A1\u09C7\u099F\u09BE\u0995\u09C7 \u098F\u0995\u099F\u09BF \u09B8\
  \u09BF\u09AE\u09CD\u09AA\u09B2, \u09AA\u09CD\u09B2\u09C7\u0987\u09A8\u099F\u09C7\
  \u0995\u09CD\u09B8\u099F \u09AB\u09B0\u09AE\u09CD\u09AF\u09BE\u099F\u09C7 \u09B8\
  \u0982\u09B0\u0995\u09CD\u09B7\u09A3 \u0995\u09B0\u09C7 \u098F\u09AE\u09A8 \u09AB\
  \u09BE\u0987\u09B2\u0997\u09C1\u09B2\u09BF \u09AA\u09BE\u09B0\u09CD\u09B8\u09BF\u0982\
  \ \u098F\u09AC\u0982 \u099C\u09C7\u09A8\u09BE\u09B0\u09C7\u099F\u09BF\u0982 \u0995\
  \u09B0\u09BE\u0964\u2026"
lastmod: '2024-03-17T18:47:43.972474-06:00'
model: gpt-4-0125-preview
summary: "CSV (Comma Separated Values) \u09A8\u09BF\u09AF\u09BC\u09C7 \u0995\u09BE\
  \u099C \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\u09C7 \u099F\u09C7\u09AC\u09BF\u09B2\
  \u09BE\u09B0 \u09A1\u09C7\u099F\u09BE\u0995\u09C7 \u098F\u0995\u099F\u09BF \u09B8\
  \u09BF\u09AE\u09CD\u09AA\u09B2, \u09AA\u09CD\u09B2\u09C7\u0987\u09A8\u099F\u09C7\
  \u0995\u09CD\u09B8\u099F \u09AB\u09B0\u09AE\u09CD\u09AF\u09BE\u099F\u09C7 \u09B8\
  \u0982\u09B0\u0995\u09CD\u09B7\u09A3 \u0995\u09B0\u09C7 \u098F\u09AE\u09A8 \u09AB\
  \u09BE\u0987\u09B2\u0997\u09C1\u09B2\u09BF \u09AA\u09BE\u09B0\u09CD\u09B8\u09BF\u0982\
  \ \u098F\u09AC\u0982 \u099C\u09C7\u09A8\u09BE\u09B0\u09C7\u099F\u09BF\u0982 \u0995\
  \u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\
  \u09B0\u09BE \u09AA\u09CD\u09B0\u09BE\u09AF\u09BC\u0987 \u09AC\u09BF\u09AD\u09BF\
  \u09A8\u09CD\u09A8 \u0985\u09CD\u09AF\u09BE\u09AA\u09CD\u09B2\u09BF\u0995\u09C7\u09B6\
  \u09A8\u09C7\u09B0 \u09AE\u09A7\u09CD\u09AF\u09C7 \u09B8\u09B9\u099C\u09C7 \u09A1\
  \u09C7\u099F\u09BE \u0986\u09A6\u09BE\u09A8-\u09AA\u09CD\u09B0\u09A6\u09BE\u09A8\
  \ \u09B8\u0995\u09CD\u09B7\u09AE \u0995\u09B0\u09A4\u09C7 \u0985\u09A5\u09AC\u09BE\
  \ \u099F\u09BE\u0987\u09AA-\u09B8\u09C7\u09AB \u0989\u09AA\u09BE\u09AF\u09BC\u09C7\
  \ Elm \u09AE\u09A7\u09CD\u09AF\u09C7 \u09AC\u09C3\u09B9\u09CE \u09A1\u09C7\u099F\
  \u09BE\u09B8\u09C7\u099F \u09A6\u0995\u09CD\u09B7\u09A4\u09BE\u09B0 \u09B8\u09BE\
  \u09A5\u09C7 \u09AA\u09CD\u09B0\u0995\u09CD\u09B0\u09BF\u09AF\u09BC\u09BE \u0995\
  \u09B0\u09A4\u09C7 \u098F\u099F\u09BF \u09B8\u09BE\u09A7\u09BE\u09B0\u09A3\u09AD\
  \u09BE\u09AC\u09C7 \u0985\u09A8\u09C1\u09B6\u09C0\u09B2\u09A8 \u0995\u09B0\u09C7\
  \ \u09A5\u09BE\u0995\u09C7\u09A8\u0964."
title: "CSV \u098F\u09B0 \u09B8\u09BE\u09A5\u09C7 \u0995\u09BE\u099C \u0995\u09B0\u09BE"
weight: 37
---

## কিভাবে:
Elm এ CSV পার্সিং অথবা জেনারেশনের জন্য বিল্ট-ইন সাপোর্ট নেই; এর পরিবর্তে, `panosoft/elm-csv` এর মতো তৃতীয় পক্ষের প্যাকেজগুলিকে প্রায়ই ব্যবহৃত হয়। নিচের উদাহরণগুলি এই লাইব্রেরির মৌলিক ব্যবহারের জন্য CSV পার্সিং এবং জেনারেটিং দেখায়।

### CSV পার্সিং
প্রথমে, আপনাকে আপনার Elm প্রকল্পে CSV প্যাকেজ যোগ করতে হবে:

```bash
elm install panosoft/elm-csv
```

তারপর, আপনি একটি CSV স্ট্রিংকে রেকর্ডের লিস্টে পার্স করতে পারেন। একটি সিম্পল উদাহরণ:

```elm
import Csv

csvData : String
csvData =
    "name,age\nJohn Doe,30\nJane Smith,25"

parseResult : Result String (List (List String))
parseResult =
    Csv.parse csvData

-- নমুনা আউটপুট: Ok [["name","age"],["John Doe","30"],["Jane Smith","25"]]
```

### CSV জেনারেটিং
Elm ডেটা থেকে একটি CSV স্ট্রিং জেনারেট করতে, `Csv.encode` ফাংশন ব্যবহার করুন:

```elm
import Csv

records : List (List String)
records =
    [ ["name", "age"]
    , ["John Doe", "30"]
    , ["Jane Smith", "25"]
    ]

csvOutput : String
csvOutput =
    Csv.encode records

-- নমুনা আউটপুট: "name,age\nJohn Doe,30\nJane Smith,25\n"
```

এই সিম্পলিস্টিক অ্যাপ্রোচটি আপনাকে আপনার Elm অ্যাপ্লিকেশনগুলিতে CSV ফাংশনালিটিস ইন্টিগ্রেট করতে সক্ষম করে, ডেটা ম্যানিপুলেশন এবং আদান-প্রদানের জন্য টাইপ-সেফ পরিবেশ ব্যবহার করে।
