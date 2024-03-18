---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:36:23.990899-06:00
description: "XML \u098F\u09B0 \u09B8\u09BE\u09A5\u09C7 \u0995\u09BE\u099C \u0995\u09B0\
  \u09BE \u09AE\u09BE\u09A8\u09C7 XML \u09A1\u0995\u09C1\u09AE\u09C7\u09A8\u09CD\u099F\
  \u0997\u09C1\u09B2\u09BF \u0995\u09CB\u09A1\u09C7\u09B0 \u09AE\u09BE\u09A7\u09CD\
  \u09AF\u09AE\u09C7 \u09AA\u09BE\u09B0\u09CD\u09B8 \u0995\u09B0\u09BE \u098F\u09AC\
  \u0982 \u09AE\u09CD\u09AF\u09BE\u09A8\u09BF\u09AA\u09C1\u09B2\u09C7\u099F \u0995\
  \u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\
  \u09B0\u09BE \u098F\u099F\u09BF \u0995\u09B0\u09C7 \u09A4\u09A5\u09CD\u09AF \u09AA\
  \u09A1\u09BC\u09BE, \u09B2\u09BF\u0996\u09BE, \u098F\u09AC\u0982 \u09AA\u09B0\u09BF\
  \u09AC\u09B0\u09CD\u09A4\u09A8 \u0995\u09B0\u09BE\u09B0 \u099C\u09A8\u09CD\u09AF\
  , \u098F\u0995\u099F\u09BF\u2026"
lastmod: '2024-03-17T18:47:44.204872-06:00'
model: gpt-4-0125-preview
summary: "XML \u098F\u09B0 \u09B8\u09BE\u09A5\u09C7 \u0995\u09BE\u099C \u0995\u09B0\
  \u09BE \u09AE\u09BE\u09A8\u09C7 XML \u09A1\u0995\u09C1\u09AE\u09C7\u09A8\u09CD\u099F\
  \u0997\u09C1\u09B2\u09BF \u0995\u09CB\u09A1\u09C7\u09B0 \u09AE\u09BE\u09A7\u09CD\
  \u09AF\u09AE\u09C7 \u09AA\u09BE\u09B0\u09CD\u09B8 \u0995\u09B0\u09BE \u098F\u09AC\
  \u0982 \u09AE\u09CD\u09AF\u09BE\u09A8\u09BF\u09AA\u09C1\u09B2\u09C7\u099F \u0995\
  \u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\
  \u09B0\u09BE \u098F\u099F\u09BF \u0995\u09B0\u09C7 \u09A4\u09A5\u09CD\u09AF \u09AA\
  \u09A1\u09BC\u09BE, \u09B2\u09BF\u0996\u09BE, \u098F\u09AC\u0982 \u09AA\u09B0\u09BF\
  \u09AC\u09B0\u09CD\u09A4\u09A8 \u0995\u09B0\u09BE\u09B0 \u099C\u09A8\u09CD\u09AF\
  , \u098F\u0995\u099F\u09BF\u2026"
title: "XML \u098F\u09B0 \u09B8\u09BE\u09A5\u09C7 \u0995\u09BE\u099C \u0995\u09B0\u09BE"
---

{{< edit_this_page >}}

## কি এবং কেন?
XML এর সাথে কাজ করা মানে XML ডকুমেন্টগুলি কোডের মাধ্যমে পার্স করা এবং ম্যানিপুলেট করা। প্রোগ্রামাররা এটি করে তথ্য পড়া, লিখা, এবং পরিবর্তন করার জন্য, একটি structured, portable format ব্যবহার করে যা তথ্য বিনিময় এবং সংরক্ষণের জন্য ব্যাপকভাবে ব্যবহৃত হয়।

## কিভাবে:
Lua-তে নেটিভ XML পার্সিং অন্তর্ভুক্ত নেই, তবে LuaXML এবং xml2lua এর মতো লাইব্রেরি রয়েছে যা এই কাজটি সম্পন্ন করে। এখানে xml2lua দিয়ে XML পার্সিং করার একটি দ্রুত দৃষ্টান্ত দেওয়া হলো:

```Lua
local xml2lua = require("xml2lua")
local handler = require("xmlhandler.tree")

local xmlParser = xml2lua.parser(handler)
xmlParser:parse([[<root><book id="123">Programming in Lua</book></root>]])

print(handler.root.book._attr.id)  -- আউটপুট: 123
print(handler.root.book[1])        -- আউটপুট: Programming in Lua
```

XML লেখার জন্য, এখানে LuaXML ব্যবহার করে একটি মিনি উদাহরণ দেওয়া হলো:

```Lua
local luaxml = require("LuaXML")

local xml = xml.new("root")
xml:append("book")[1] = "Programming in Lua"
xml.book._attr = {id="123"}

print(xml:tag())  -- আউটপুট: <root><book id="123">Programming in Lua</book></root>
```

## গভীর ডুব
XML, যার পূর্ণ রূপ হল এক্সটেনসিবল মার্কআপ ল্যাঙ্গুয়েজ, ৯০-এর দশকের মাঝামাঝি থেকে ডাটা প্রতিনিধিত্ব এবং বিনিময়ের একটি মানদণ্ড হয়ে উঠেছে। এটি তথ্যকে গঠন দেয় এবং মানুষের পড়ার যোগ্য এবং মেশিন পার্সকরণযোগ্য উভয়ই।

যদিও JSON এবং YAML তাদের সারল্যের জন্য এখন প্রাধান্য পেয়েছে, XML অনেক enterprise এবং legacy সিস্টেমে প্রচলিত। Lua-তে নেটিভ XML হ্যান্ডলিং অন্তর্ভুক্ত নেই কারণ Lua ছোট এবং মডিউলের মাধ্যমে এক্সটেনসিবল ডিজাইন করা হয়েছে।

LuaXML, xml2lua, এবং অন্যান্যের মতো Lua উপলব্ধ XML লাইব্রেরিগুলি এই ফাঁকটি পূরণ করে। LuaXML একটি লাইটওয়েট XML রিডার এবং রাইটার প্রদান করে, অন্যদিকে xml2lua একটি ইভেন্ট-ড্রাইভেন পদ্ধতি ব্যবহার করে যা SAX পার্সারগুলির মতো। এই লাইব্্ররীগুলি সাধারণত পোর্টেবিলিটির জন্য খাঁটি Lua-তে বাস্তবায়িত হয়, যদিও কিছু কিছু কর্মক্ষমতার জন্য সি-তে নির্ভরশীল হতে পারে।

কর্মক্ষমতা এবং মেমরি ব্যবহারের ক্ষেত্রে, Lua-র XML লাইব্রেরি সম্ভবত নেটিভ সাপোর্ট সহ ভাষাগুলির তুলনায় দ্রুত নয়। তবে, Lua-তে বেশিরভাগ ব্যবহারের ক্ষেত্রে, বিশেষ করে গেম ডেভেলপমেন্ট অথবা এম্বেডেড সিস্টেমের জন্য স্ক্রিপ্টিং করা, এই লাইব্রেরিগুলি সিস্টেমে অতিরিক্ত লোড ছাড়াই ভাল কাজ করে।

## আরও দেখুন
- LuaXML GitHub-এ: https://github.com/LuaDist/luaxml
- xml2lua GitHub-এ: https://github.com/manoelcampos/xml2lua
- Lua.org-এর লাইব্রেরির তালিকা: https://lua-users.org/wiki/LibrariesAndBindings
