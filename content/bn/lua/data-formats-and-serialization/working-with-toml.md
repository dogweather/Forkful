---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:30:50.834754-06:00
description: "TOML \u09A8\u09BF\u09AF\u09BC\u09C7 \u0995\u09BE\u099C \u0995\u09B0\u09BE\
  \ \u09AE\u09BE\u09A8\u09C7 Lua \u098F\u09B0 \u09B8\u0999\u09CD\u0997\u09C7 TOML\
  \ (Tom's Obvious, Minimal Language) \u09A1\u09C7\u099F\u09BE \u09AA\u09BE\u09B0\u09CD\
  \u09B8\u09BF\u0982 \u098F\u09AC\u0982 \u099C\u09C7\u09A8\u09BE\u09B0\u09C7\u099F\
  \ \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\
  \u09BE\u09B0\u09B0\u09BE \u098F\u09B0 \u09AA\u09A0\u09A8\u09AF\u09CB\u0997\u09CD\
  \u09AF\u09A4\u09BE \u098F\u09AC\u0982 \u09B8\u09BE\u09A7\u09BE\u09B0\u09A3\u2026"
lastmod: '2024-03-17T18:47:44.203930-06:00'
model: gpt-4-0125-preview
summary: "TOML \u09A8\u09BF\u09AF\u09BC\u09C7 \u0995\u09BE\u099C \u0995\u09B0\u09BE\
  \ \u09AE\u09BE\u09A8\u09C7 Lua \u098F\u09B0 \u09B8\u0999\u09CD\u0997\u09C7 TOML\
  \ (Tom's Obvious, Minimal Language) \u09A1\u09C7\u099F\u09BE \u09AA\u09BE\u09B0\u09CD\
  \u09B8\u09BF\u0982 \u098F\u09AC\u0982 \u099C\u09C7\u09A8\u09BE\u09B0\u09C7\u099F\
  \ \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\
  \u09BE\u09B0\u09B0\u09BE \u098F\u09B0 \u09AA\u09A0\u09A8\u09AF\u09CB\u0997\u09CD\
  \u09AF\u09A4\u09BE \u098F\u09AC\u0982 \u09B8\u09BE\u09A7\u09BE\u09B0\u09A3 \u09B8\
  \u09BF\u09A8\u099F\u09CD\u09AF\u09BE\u0995\u09CD\u09B8\u09C7\u09B0 \u0995\u09BE\u09B0\
  \u09A3\u09C7 \u0995\u09A8\u09AB\u09BF\u0997 \u09AB\u09BE\u0987\u09B2\u0997\u09C1\
  \u09B2\u09BF\u09B0 \u099C\u09A8\u09CD\u09AF TOML \u09AC\u09CD\u09AF\u09AC\u09B9\u09BE\
  \u09B0 \u0995\u09B0\u09C7 \u09A5\u09BE\u0995\u09C7\u09A8, \u09AF\u09BE \u09B8\u09B9\
  \u099C\u09C7\u0987 \u098F\u0995\u099F\u09BF \u09A1\u09C7\u099F\u09BE \u09B8\u09CD\
  \u099F\u09CD\u09B0\u09BE\u0995\u099A\u09BE\u09B0\u09C7 \u0985\u09A8\u09C1\u09AC\u09BE\
  \u09A6 \u0995\u09B0\u09BE \u09AF\u09BE\u09AF\u09BC\u0964."
title: "\u099F\u09AE\u09B2 \u09A8\u09BF\u09AF\u09BC\u09C7 \u0995\u09BE\u099C \u0995\
  \u09B0\u09BE"
weight: 39
---

## কিভাবে:
প্রথমে, আপনার Lua পরিবেশে একটি TOML পার্সার আছে কিনা তা নিশ্চিত করুন। এই উদাহরণের জন্য আমরা `lua-toml` ব্যবহার করব।

```Lua
local toml = require("toml")

-- TOML string পার্স করুন
local toml_data = [[
title = "TOML Example"

[owner]
name = "Tom Preston-Werner"
dob = 1979-05-27T07:32:00Z
]]

local data = toml.parse(toml_data)
print(data.title) -- "TOML Example"

-- TOML string জেনারেট করুন
local table_data = {
  title = "TOML Example",
  owner = {
    name = "Tom Preston-Werner",
    dob = os.time({year=1979, month=5, day=27, hour=7, min=32})
  }
}

local toml_string = toml.encode(table_data)
print(toml_string)
```

নমুনা আউটপুট:
```
TOML Example
```

## গভীর ডাইভ
TOML 2013 সালে Tom Preston-Werner কর্তৃক XML এবং YAML এর মত ডেটা সেরিয়ালাইজেশন ভাষার বিকল্প হিসেবে তৈরি করা হয়েছিল, যা কনফিগারেশন ডেটাকে প্রতিনিধিত্ব করার জন্য একটি সহজতর ফর্ম্যাট অফার করে। JSON যদিও সর্বজনীন, এর সিনট্যাক্স কনফিগ ফাইলগুলির জন্য অসুবিধাজনক হতে পারে। TOML মানুষের জন্য একটি পরিষ্কার সিনট্যাক্স নিয়ে আসে, যা .ini ফাইলগুলির মতো দেখতে কিন্তু নেস্টিং ক্ষমতা এবং ডেটা টাইপগুলিকে অন্তর্ভুক্ত করে।

TOML এর বিকল্পগুলি হল JSON, YAML, এবং XML। তবে, TOML বিশেষভাবে কনফিগের জন্য ডিজাইন করা হয়েছে এবং এটি YAML এর চেয়ে সহজিকর, JSON এর তুলনায় কনফিগ পার্পাসের জন্য অধিক পঠনযোগ্য এবং XML এর চেয়ে কম ফুলস্ক্রিপ্টেড।

Lua তে TOML ব্যবস্থাপনা বাস্তবায়ন সাধারণত একটি তৃতীয়-পক্ষের লাইব্রেরির প্রয়োজন। পারফরম্যান্স এবং বৈশিষ্ট্য বিভিন্ন থেকে প্রাথমিক পার্সিং থেকে পূর্ণ সিরিয়ালাইজেশন সমর্থন পর্যন্ত ভিন্ন হতে পারে। বড় কনফিগ ফাইলগুলি সাথে আচরণ করা বা ঘন ঘন পঠন/লিখন অপারেশনের ক্ষেত্রে, লাইব্রেরির পারফরম্যান্স এবং সর্বশেষ TOML সংস্করণের সাথে মিল বিবেচনা করুন।

## আরও দেখুন
- TOML স্পেসিফিকেশন: https://toml.io/en/
- `lua-toml` লাইব্রেরি: https://github.com/jonstoler/lua-toml
- ডেটা সিরিয়ালাইজেশন ফর্ম্যাটের তুলনা: https://en.wikipedia.org/wiki/Comparison_of_data-serialization_formats
