---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:17:34.377626-06:00
description: "HTTP \u0985\u09A8\u09C1\u09B0\u09CB\u09A7 \u09AA\u09BE\u09A0\u09BE\u09A8\
  \u09CB \u09B9\u09B2 \u0993\u09AF\u09BC\u09C7\u09AC \u09B8\u09BE\u09B0\u09CD\u09AD\
  \u09BE\u09B0\u09C7 \u09A1\u09C7\u099F\u09BE \u09AC\u09BE \u0995\u09CD\u09B0\u09BF\
  \u09AF\u09BC\u09BE \u099A\u09BE\u0993\u09AF\u09BC\u09BE\u09B0 \u09AA\u09CD\u09B0\
  \u0995\u09CD\u09B0\u09BF\u09AF\u09BC\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\
  \u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE API-\u098F\u09B0 \u09B8\u09BE\u09A5\u09C7\
  \ \u09AE\u09BF\u09A5\u09B8\u09CD\u0995\u09CD\u09B0\u09BF\u09AF\u09BC\u09BE \u0995\
  \u09B0\u09A4\u09C7, \u0993\u09AF\u09BC\u09C7\u09AC \u0995\u09A8\u09CD\u099F\u09C7\
  \u09A8\u09CD\u099F \u09B8\u0982\u0997\u09CD\u09B0\u09B9 \u0995\u09B0\u09A4\u09C7\
  , \u09AC\u09BE \u09B8\u09C7\u09AC\u09BE\u2026"
lastmod: '2024-03-17T18:47:44.079184-06:00'
model: gpt-4-0125-preview
summary: "HTTP \u0985\u09A8\u09C1\u09B0\u09CB\u09A7 \u09AA\u09BE\u09A0\u09BE\u09A8\
  \u09CB \u09B9\u09B2 \u0993\u09AF\u09BC\u09C7\u09AC \u09B8\u09BE\u09B0\u09CD\u09AD\
  \u09BE\u09B0\u09C7 \u09A1\u09C7\u099F\u09BE \u09AC\u09BE \u0995\u09CD\u09B0\u09BF\
  \u09AF\u09BC\u09BE \u099A\u09BE\u0993\u09AF\u09BC\u09BE\u09B0 \u09AA\u09CD\u09B0\
  \u0995\u09CD\u09B0\u09BF\u09AF\u09BC\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\
  \u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE API-\u098F\u09B0 \u09B8\u09BE\u09A5\u09C7\
  \ \u09AE\u09BF\u09A5\u09B8\u09CD\u0995\u09CD\u09B0\u09BF\u09AF\u09BC\u09BE \u0995\
  \u09B0\u09A4\u09C7, \u0993\u09AF\u09BC\u09C7\u09AC \u0995\u09A8\u09CD\u099F\u09C7\
  \u09A8\u09CD\u099F \u09B8\u0982\u0997\u09CD\u09B0\u09B9 \u0995\u09B0\u09A4\u09C7\
  , \u09AC\u09BE \u09B8\u09C7\u09AC\u09BE \u0997\u09C1\u09B2\u09CB\u09B0 \u09AE\u09A7\
  \u09CD\u09AF\u09C7 \u09AF\u09CB\u0997\u09BE\u09AF\u09CB\u0997 \u0995\u09B0\u09A4\
  \u09C7 \u098F\u099F\u09BF \u0995\u09B0\u09C7 \u09A5\u09BE\u0995\u09C7\u0964."
title: "HTTP \u0985\u09A8\u09C1\u09B0\u09CB\u09A7 \u09AA\u09CD\u09B0\u09C7\u09B0\u09A3\
  \ \u0995\u09B0\u09BE"
weight: 44
---

## কিভাবে:
চলুন মজার বিষয়ে চলে যাই। আপনার `http-client` এবং `http-client-tls` প্যাকেজ প্রয়োজন হবে। আপনার স্ট্যাক সেট করুন এবং এগুলোকে আপনার `package.yaml` অথবা `.cabal` ফাইলে যোগ করুন। তারপর, `stack build` বা উপযুক্ত কমান্ড চালান তাদের অনুসন্ধানের জন্য।

এখানে একটি সিম্পল GET অনুরোধ রয়েছে:

```Haskell
import Network.HTTP.Client
import Network.HTTP.Client.TLS
import qualified Data.ByteString.Lazy.Char8 as L8

main :: IO ()
main = do
    manager <- newManager tlsManagerSettings
    request <- parseRequest "http://httpbin.org/get"
    response <- httpLbs request manager
    L8.putStrLn $ responseBody response
```

এটি `httpbin.org` থেকে পাওয়া JSON প্রিন্ট করবে।

## গভীরে দেখা
পূর্বে, Haskell এর HTTP অনুরোধ কম সোজা ছিল, কিন্তু `http-client` এর মতো লাইব্রেরিগুলি প্রক্রিয়াটি সহজ করে তুলেছে।

বিকল্প? অবশ্যই। `wreq`, `req` এবং অন্যান্য আছে, প্রায়শই সিন্ট্যাক্টিক সুগার বা অতিরিক্ত ফিচার সহ। কিন্তু `http-client` আপনার ড্রয়ারে থাকা সেই নির্ভরযোগ্য সুইস আর্মি নাইফের মত, যেটি সবসময় কাজটি সারে।

অন্তর্নিহিতভাবে, `http-client` কানেকশন সামলাইতে একটি `Manager` ব্যবহার করে। এটি দক্ষ এবং সকেটগুলো পুনরায় ব্যবহার করে। আপনি এটি টিউন করতে পারেন, কিন্তু শুরুতে ডিফল্টগুলি ঠিক আছে।

## আরও দেখুন
আপনার টুলকিট প্রসারিত করতে, এগুলি দেখুন:

- [The `http-client` প্যাকেজ](https://www.stackage.org/package/http-client)
- [আরও আধুনিক দৃষ্টিকোণের `wreq` প্যাকেজ](https://www.stackage.org/package/wreq)
- [Haskell লাইব্রেরিগুলোর জন্য Hackage](https://hackage.haskell.org/)
