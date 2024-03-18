---
changelog:
- 2024-03-17, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-17 17:48:16.872665-06:00
description: "\u098F\u0995\u099F\u09BF \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982\u09DF\
  \u09C7\u09B0 \u09A6\u09C8\u09B0\u09CD\u0998\u09CD\u09AF \u09A8\u09BF\u09B0\u09CD\
  \u09A3\u09DF \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\u09C7 \u098F\u09B0 \u0985\u0995\
  \u09CD\u09B7\u09B0\u0997\u09C1\u09B2\u09BF \u0997\u09A3\u09A8\u09BE \u0995\u09B0\
  \u09BE\u0964 \u0986\u09AE\u09B0\u09BE \u0987\u09A8\u09AA\u09C1\u099F \u09AF\u09BE\
  \u099A\u09BE\u0987 \u0995\u09B0\u09BE, \u0985\u0995\u09CD\u09B7\u09B0\u09B8\u09AE\
  \u09C2\u09B9\u09C7\u09B0 \u09AE\u09A7\u09CD\u09AF \u09A6\u09BF\u09DF\u09C7 \u09B2\
  \u09C1\u09AA \u0995\u09B0\u09BE, \u09B8\u0982\u09B8\u09CD\u09A5\u09BE\u09A8 \u09AC\
  \u09B0\u09BE\u09A6\u09CD\u09A6 \u0995\u09B0\u09BE, \u0985\u09A5\u09AC\u09BE \u0995\
  \u09C7\u09AC\u09B2 \u099C\u09BF\u099C\u09CD\u099E\u09BE\u09B8\u09BE\u2026"
lastmod: '2024-03-17T18:47:44.028264-06:00'
model: gpt-4-0125-preview
summary: "\u098F\u0995\u099F\u09BF \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982\u09DF\
  \u09C7\u09B0 \u09A6\u09C8\u09B0\u09CD\u0998\u09CD\u09AF \u09A8\u09BF\u09B0\u09CD\
  \u09A3\u09DF \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\u09C7 \u098F\u09B0 \u0985\u0995\
  \u09CD\u09B7\u09B0\u0997\u09C1\u09B2\u09BF \u0997\u09A3\u09A8\u09BE \u0995\u09B0\
  \u09BE\u0964 \u0986\u09AE\u09B0\u09BE \u0987\u09A8\u09AA\u09C1\u099F \u09AF\u09BE\
  \u099A\u09BE\u0987 \u0995\u09B0\u09BE, \u0985\u0995\u09CD\u09B7\u09B0\u09B8\u09AE\
  \u09C2\u09B9\u09C7\u09B0 \u09AE\u09A7\u09CD\u09AF \u09A6\u09BF\u09DF\u09C7 \u09B2\
  \u09C1\u09AA \u0995\u09B0\u09BE, \u09B8\u0982\u09B8\u09CD\u09A5\u09BE\u09A8 \u09AC\
  \u09B0\u09BE\u09A6\u09CD\u09A6 \u0995\u09B0\u09BE, \u0985\u09A5\u09AC\u09BE \u0995\
  \u09C7\u09AC\u09B2 \u099C\u09BF\u099C\u09CD\u099E\u09BE\u09B8\u09BE\u2026"
title: "\u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982 \u098F\u09B0 \u09A6\u09C8\u09B0\
  \u09CD\u0998\u09CD\u09AF \u099A\u09BF\u09B9\u09CD\u09A8\u09BF\u09A4 \u0995\u09B0\
  \u09BE"
---

{{< edit_this_page >}}

## কি এবং কেন?

একটি স্ট্রিংয়ের দৈর্ঘ্য নির্ণয় করা মানে এর অক্ষরগুলি গণনা করা। আমরা ইনপুট যাচাই করা, অক্ষরসমূহের মধ্য দিয়ে লুপ করা, সংস্থান বরাদ্দ করা, অথবা কেবল জিজ্ঞাসা – আকার জানা মানে গুরুত্বপূর্ণ।

## কি ভাবে:

C#-এ, `string.Length` প্রোপার্টিটি আপনাকে একটি স্ট্রিংয়ে অক্ষরের সংখ্যা বলে দেয়। এটি কিভাবে ব্যবহার করতে হয় দেখুন:

```C#
using System;

class Program
{
    static void Main()
    {
        string example = "Hello, World!";
        Console.WriteLine(example.Length); // আউটপুট: 13
    }
}
```

সহজ, তাই না? কিন্তু মনে রাখবেন, এটা *অক্ষরগুলি* গণনা করে, বাইট নয়। ইমোজি অথবা বিশেষ অক্ষরের সাথে, জিনিসটা জটিল হতে পারে। পরে আরো জানুন।

## গভীর ডুব

ঐতিহাসিকভাবে, একটি স্ট্রিংয়ের দৈর্ঘ্য খোঁজার বিষয়টি প্রোগ্রামিংয়ে মেমরি ব্যবস্থাপনা ও ম্যানিপুলেশনের সাথে জড়িত ছিল। যেহেতু C# একটি উচ্চ-স্তরের ভাষা, এটি ওই নিম্ন-স্তরের কাজটি লুকিয়ে রাখে। তবুও, কি আছে তলদেশে তা জানা ভালো।

বিকল্প? অবশ্যই! আপনি `example.ToCharArray().Length` দেখতে পারেন বাইরে, কিন্তু এটি একই ফলাফলের জন্য অতিরিক্ত কাজ করছে।

এখন, সেই জটিল অক্ষরগুলোর কথায় আসি। C#-এর `Length` প্রোপার্টিটি একটি স্ট্রিংয়ের `char` অবজেক্টগুলি গণনা করে, প্রতিটি একটি UTF-16 কোড ইউনিটকে প্রতিনিধিত্ব করে। এটা ঠিক আছে, যতক্ষণ আপনি *সারোগেট জোড়া* – ইমোজির মত অক্ষরের সাথে দেখা না করেন যা দুটি `char` অবজেক্ট প্রয়োজন। এখানে বিষয়: `Length` এগুলি দুটি হিসেবে গণনা করে। হ্যাঁ।

*দৃশ্যমান* অক্ষর অথবা *গ্রাফিম ক্লাস্টার* এর সঠিক গণনা করতে, আপনার System.Globalization-এর `StringInfo` ক্লাসের প্রয়োজন হবে:

```C#
using System;
using System.Globalization;

class Program
{
    static void Main()
    {
        string example = "👍"; // থাম্স আপ ইমোজি

        Console.WriteLine(example.Length); // আউটপুট: 2 <- কারণ সারোগেট জোড়া!
        Console.WriteLine(new StringInfo(example).LengthInTextElements); // আউটপুট: 1
    }
}
```

পার্থক্যটা বুঝতে পারছেন? এটা শুধু বিদ্যামূলক নয়; এটি পাঠ্য প্রক্রিয়ায় গুরুত্বপূর্ণ প্রভাব ফেলতে পারে।

## আরও দেখুন

এই সংস্থানগুলির সাথে আরও জানুন:

- [স্ট্রিং সম্পর্কিত মাইক্রোসফটের অফিসিয়াল ডকুমেন্টেশন](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/strings/)
- [Unicode এবং UTF-16 বুঝতে](https://unicodebook.readthedocs.io/unicode_encodings.html)
- [StringInfo ক্লাসের ডকুমেন্টেশন](https://docs.microsoft.com/en-us/dotnet/api/system.globalization.stringinfo?view=net-6.0)

আপনার স্ট্রিংগুলিকে জানুন, বিজ্ঞানসম্মতভাবে তাদের ব্যবহার করুন, এবং প্রতিটি অর্থে গণনাকারী কোড লিখুন।
