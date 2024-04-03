---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:42:41.543859-06:00
description: "Haskell-\u098F \u09B8\u09CD\u099F\u09CD\u09AF\u09BE\u09A8\u09CD\u09A1\
  \u09BE\u09B0\u09CD\u09A1 \u098F\u09B0\u09B0 (stderr) \u09B2\u09C7\u0996\u09BE \u09AA\
  \u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u0997\u09C1\u09B2\u09BF\u0995\u09C7\
  \ \u09A4\u09BE\u09A6\u09C7\u09B0 \u0986\u0989\u099F\u09AA\u09C1\u099F\u0995\u09C7\
  \ \u09B8\u09BE\u09A7\u09BE\u09B0\u09A3 \u09AB\u09B2\u09BE\u09AB\u09B2 \u098F\u09AC\
  \u0982 \u09A4\u09CD\u09B0\u09C1\u099F\u09BF \u09AC\u09BE\u09B0\u09CD\u09A4\u09BE\
  \u09B0 \u09AE\u09A7\u09CD\u09AF\u09C7 \u09AA\u09BE\u09B0\u09CD\u09A5\u0995\u09CD\
  \u09AF \u0995\u09B0\u09A4\u09C7 \u09A6\u09C7\u09AF\u09BC\u0964 \u09B8\u09AE\u09B8\
  \u09CD\u09AF\u09BE \u09B8\u0982\u0995\u09C7\u09A4 \u098F\u09AC\u0982\u2026"
lastmod: '2024-03-17T18:47:44.101738-06:00'
model: gpt-4-0125-preview
summary: "Haskell-\u098F \u09B8\u09CD\u099F\u09CD\u09AF\u09BE\u09A8\u09CD\u09A1\u09BE\
  \u09B0\u09CD\u09A1 \u098F\u09B0\u09B0 (stderr) \u09B2\u09C7\u0996\u09BE \u09AA\u09CD\
  \u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u0997\u09C1\u09B2\u09BF\u0995\u09C7 \u09A4\
  \u09BE\u09A6\u09C7\u09B0 \u0986\u0989\u099F\u09AA\u09C1\u099F\u0995\u09C7 \u09B8\
  \u09BE\u09A7\u09BE\u09B0\u09A3 \u09AB\u09B2\u09BE\u09AB\u09B2 \u098F\u09AC\u0982\
  \ \u09A4\u09CD\u09B0\u09C1\u099F\u09BF \u09AC\u09BE\u09B0\u09CD\u09A4\u09BE\u09B0\
  \ \u09AE\u09A7\u09CD\u09AF\u09C7 \u09AA\u09BE\u09B0\u09CD\u09A5\u0995\u09CD\u09AF\
  \ \u0995\u09B0\u09A4\u09C7 \u09A6\u09C7\u09AF\u09BC\u0964 \u09B8\u09AE\u09B8\u09CD\
  \u09AF\u09BE \u09B8\u0982\u0995\u09C7\u09A4 \u098F\u09AC\u0982 \u09A1\u09BF\u09AC\
  \u09BE\u0997\u09BF\u0982 \u098F\u09B0 \u099C\u09A8\u09CD\u09AF \u098F\u099F\u09BF\
  \ \u0985\u09A4\u09CD\u09AF\u09A8\u09CD\u09A4 \u0997\u09C1\u09B0\u09C1\u09A4\u09CD\
  \u09AC\u09AA\u09C2\u09B0\u09CD\u09A3, \u0986\u0989\u099F\u09AA\u09C1\u099F\u0995\
  \u09C7 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09C7\u09B0 \u09AA\
  \u09CD\u09B0\u09A7\u09BE\u09A8 \u09A1\u09C7\u099F\u09BE \u09AC\u09BE \u09AB\u09B2\
  \u09BE\u09AB\u09B2 \u09AC\u09B9\u09A8 \u0995\u09B0\u09C7 \u098F\u09AE\u09A8 \u09B8\
  \u09CD\u099F\u09CD\u09AF\u09BE\u09A8\u09CD\u09A1\u09BE\u09B0\u09CD\u09A1 \u0986\u0989\
  \u099F\u09AA\u09C1\u099F (stdout) \u098F\u09B0 \u09B8\u09BE\u09A5\u09C7 \u099C\u099F\
  \u09BF\u09B2 \u09A8\u09BE \u0995\u09B0\u09C7\u0964."
title: "\u09B8\u09CD\u099F\u09CD\u09AF\u09BE\u09A8\u09CD\u09A1\u09BE\u09B0\u09CD\u09A1\
  \ \u098F\u09B0\u09B0\u09C7 \u09B2\u09BF\u0996\u09A8"
weight: 25
---

## কিভাবে:
Haskell-এ, `System.IO` মডিউলের সাহায্যে stderr লেখা সরাসরি সম্ভব। নিচে একটি বেসিক উদাহরণ দেখানো হলো:

```haskell
import System.IO

main :: IO ()
main = do
  hPutStrLn stderr "এটি একটি ত্রুটি বার্তা।"
```

এই প্রোগ্রামের stderr এ আউটপুট হবে:

```
এটি একটি ত্রুটি বার্তা।
```

যদি আপনি একটি আরও জটিল অ্যাপ্লিকেশনে কাজ করেন, অথবা লগিং (ত্রুটি সহ) এর উপরে ভাল নিয়ন্ত্রণ পেতে চান, আপনি তৃতীয় পক্ষের লাইব্রেরি চয়ন করতে পারেন। একটি জনপ্রিয় পছন্দ হল `monad-logger` যা Haskell প্রোগ্রামিংয়ের `mtl` স্টাইলের সাথে একীভূত হয়। এখানে `monad-logger` ব্যবহার করে একটি ছোট স্নিপেট দেওয়া হলো:

```haskell
{-# LANGUAGE OverloadedStrings #-}
import Control.Monad.Logger

main :: IO ()
main = runStderrLoggingT $ do
  logErrorN "এটি একটি ত্রুটি বার্তা যা monad-logger ব্যবহার করে।"
```

চালানো হলে, `monad-logger` ভার্সনও একটি ত্রুটি বার্তা আউটপুট করে, কিন্তু এটি কনফিগারেশনের উপর নির্ভরশীল সময়তালিকা বা লগ লেভেলের মত আরও প্রসঙ্গ সহ সজ্জিত হয়ে আসে:

```
[Error] এটি একটি ত্রুটি বার্তা যা monad-logger ব্যবহার করে।
```

উভয় পদ্ধতিই stderr লিখনের উদ্দেশ্যে কাজ করে, আপনার অ্যাপ্লিকেশনের জটিলতা এবং প্রয়োজনের উপর পছন্দের সিদ্ধান্ত অনেকাংশে নির্ভর করে।
