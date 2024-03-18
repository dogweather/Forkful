---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:06:12.790614-06:00
description: "\u098F\u0995\u099F\u09BF \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982\
  \ \u09A5\u09C7\u0995\u09C7 \u09A4\u09BE\u09B0\u09BF\u0996 \u09AA\u09BE\u09B0\u09CD\
  \u09B8 \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\u09C7 \u09A1\u09C7\u099F \u098F\u09AC\
  \u0982 \u09B8\u09AE\u09AF\u09BC\u09C7\u09B0 \u099F\u09C7\u0995\u09CD\u09B8\u099A\
  \u09C1\u09AF\u09BC\u09BE\u09B2 \u09AA\u09CD\u09B0\u09A4\u09BF\u09A8\u09BF\u09A7\u09BF\
  \u09A4\u09CD\u09AC\u0995\u09C7 \u098F\u09AE\u09A8 \u098F\u0995 \u09AB\u09B0\u09AE\
  \u09CD\u09AF\u09BE\u099F\u09C7 \u09B0\u09C2\u09AA\u09BE\u09A8\u09CD\u09A4\u09B0\
  \ \u0995\u09B0\u09BE \u09AF\u09BE \u098F\u0995\u099F\u09BF Lua \u09AA\u09CD\u09B0\
  \u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09C7\u09B0 \u09AE\u09A7\u09CD\u09AF\u09C7\
  \ \u09B8\u09B9\u099C\u09C7\u0987\u2026"
lastmod: '2024-03-17T18:47:44.189084-06:00'
model: gpt-4-0125-preview
summary: "\u098F\u0995\u099F\u09BF \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u09A5\
  \u09C7\u0995\u09C7 \u09A4\u09BE\u09B0\u09BF\u0996 \u09AA\u09BE\u09B0\u09CD\u09B8\
  \ \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\u09C7 \u09A1\u09C7\u099F \u098F\u09AC\u0982\
  \ \u09B8\u09AE\u09AF\u09BC\u09C7\u09B0 \u099F\u09C7\u0995\u09CD\u09B8\u099A\u09C1\
  \u09AF\u09BC\u09BE\u09B2 \u09AA\u09CD\u09B0\u09A4\u09BF\u09A8\u09BF\u09A7\u09BF\u09A4\
  \u09CD\u09AC\u0995\u09C7 \u098F\u09AE\u09A8 \u098F\u0995 \u09AB\u09B0\u09AE\u09CD\
  \u09AF\u09BE\u099F\u09C7 \u09B0\u09C2\u09AA\u09BE\u09A8\u09CD\u09A4\u09B0 \u0995\
  \u09B0\u09BE \u09AF\u09BE \u098F\u0995\u099F\u09BF Lua \u09AA\u09CD\u09B0\u09CB\u0997\
  \u09CD\u09B0\u09BE\u09AE\u09C7\u09B0 \u09AE\u09A7\u09CD\u09AF\u09C7 \u09B8\u09B9\
  \u099C\u09C7\u0987\u2026"
title: "\u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u09A5\u09C7\u0995\u09C7 \u09A4\
  \u09BE\u09B0\u09BF\u0996 \u09AA\u09BE\u09B0\u09CD\u09B8 \u0995\u09B0\u09BE"
---

{{< edit_this_page >}}

## কি এবং কেন?
একটি স্ট্রিং থেকে তারিখ পার্স করা মানে ডেট এবং সময়ের টেক্সচুয়াল প্রতিনিধিত্বকে এমন এক ফরম্যাটে রূপান্তর করা যা একটি Lua প্রোগ্রামের মধ্যে সহজেই ম্যানিপুলেট, স্টোর, অথবা তুলনা করা যায়। প্রোগ্রামাররা এই কাজ সম্পাদন করে যাতে তারা শিডিউলিং, লগিং, অথবা কোনো সময়-সংক্রান্ত হিসাবনিকাশগুলো সহজে করতে পারে এবং মানব-পাঠযোগ্য তারিখের ফরম্যাটের এবং কম্পিউটার দ্বারা দক্ষতার সাথে প্রক্রিয়াকৃত পরিকাঠামোগত ডেটা টাইপের মধ্যে সেতু গড়ে তুলতে পারে।

## কিভাবে:
Lua-এ ডেট এবং সময় ম্যানিপুলেশন-এর জন্য বিল্ট-ইন সাপোর্ট নেই, ছাড়া `os.date` এবং `os.time` ফাংশন দ্বারা প্রদান করা সীমিত ফাংশনালিটি। তবে, এই সীমিত প্রয়োজনে এগুলো ব্যবহার করা যেতে পারে, এবং জটিল প্রয়োজনের জন্য `luadate` লাইব্রেরি, একটি বাহ্যিক লাইব্রেরি, ব্যবহার করা যায়।

**`os.date` এবং `os.time` ব্যবহার করে:**
```lua
-- একটি মানব-পাঠযোগ্য তারিখকে টাইমস্ট্যাম্পে রূপান্তর এবং ফিরে পেতে
local dateString = "2023-09-21 15:00:00"
local pattern = "(%d+)-(%d+)-(%d+) (%d+):(%d+):(%d+)"
local year, month, day, hour, minute, second = dateString:match(pattern)

local timestamp = os.time({
  year = year,
  month = month,
  day = day,
  hour = hour,
  min = minute,
  sec = second
})

-- টাইমস্ট্যাম্পকে আবার মানব-পাঠযোগ্য ফরম্যাটে রূপান্তর
local formattedDate = os.date("%Y-%m-%d %H:%M:%S", timestamp)
print(formattedDate)  -- আউটপুট: 2023-09-21 15:00:00
```

**`luadate` ব্যবহার করে (তৃতীয় পক্ষের লাইব্রেরি):**
`luadate` ব্যবহার করতে নিশ্চিত করুন এটি LuaRocks অথবা আপনার পছন্দের প্যাকেজ ম্যানেজার দ্বারা ইনস্টল করা হয়েছে। `luadate` ডেট এবং সময় পার্সিং এবং ম্যানিপুলেশনের ব্যাপক ক্ষমতা যোগ করে।

```lua
local date = require('date')

-- সরাসরি একটি তারিখ স্ট্রিং পার্স করে
local parsedDate = date.parse("2023-09-21 15:00:00")
print(parsedDate:fmt("%Y-%m-%d %H:%M:%S"))  -- আউটপুট: 2023-09-21 15:00:00

-- সময়কাল যোগ করে
local oneWeekLater = parsedDate:adddays(7)
print(oneWeekLater:fmt("%Y-%m-%d %H:%M:%S"))  -- আউটপুট: 2023-09-28 15:00:00
```

`luadate` লাইব্রেরি Lua-তে তারিখের সাথে কাজ করার আরও অন্তর্দৃষ্টিসম্পন্ন এবং শক্তিশালী উপায় প্রদান করে, যা স্ট্রিং থেকে পার্সিং, ফরম্যাটিং, এবং তারিখের উপর অংকীয় অপারেশন সহ অনেকগুলি কাজে অনেক সহজে সম্পন্ন করা যায়, যা সময়ের উপাত্ত নিয়ে কাজ করা সহজ করে তোলে।
