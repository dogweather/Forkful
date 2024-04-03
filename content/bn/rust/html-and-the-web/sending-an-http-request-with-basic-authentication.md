---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:19:43.937915-06:00
description: "HTTP \u0985\u09A8\u09C1\u09B0\u09CB\u09A7\u09C7 \u09AE\u09CC\u09B2\u09BF\
  \u0995 \u09AA\u09CD\u09B0\u09AE\u09BE\u09A3\u09C0\u0995\u09B0\u09A3\u09C7\u09B0\
  \ \u09B8\u09BE\u09A5\u09C7 \u09AA\u09BE\u09A0\u09BE\u09A8\u09CB \u09AE\u09BE\u09A8\
  \u09C7 \u09B9\u09B2 \u098F\u0995\u099C\u09A8 \u09AC\u09CD\u09AF\u09AC\u09B9\u09BE\
  \u09B0\u0995\u09BE\u09B0\u09C0 \u098F\u09AC\u0982 \u09AA\u09BE\u09B8\u0993\u09AF\
  \u09BC\u09BE\u09B0\u09CD\u09A1\u0995\u09C7 \u098F\u0995\u099F\u09BF \u0985\u09A8\
  \u09C1\u09B0\u09CB\u09A7 \u09B9\u09C7\u09A1\u09BE\u09B0\u09C7 \u09B8\u0982\u09AF\
  \u09C1\u0995\u09CD\u09A4\u09BF \u0995\u09B0\u09BE, \u09AF\u09BE\u09A4\u09C7 \u09AA\
  \u09CD\u09B0\u09AE\u09BE\u09A3 \u0995\u09B0\u09BE \u09AF\u09BE\u09AF\u09BC \u09AF\
  \u09C7 \u0986\u09AA\u09A8\u09BF\u2026"
lastmod: '2024-03-17T18:47:43.808826-06:00'
model: gpt-4-0125-preview
summary: "HTTP \u0985\u09A8\u09C1\u09B0\u09CB\u09A7\u09C7 \u09AE\u09CC\u09B2\u09BF\
  \u0995 \u09AA\u09CD\u09B0\u09AE\u09BE\u09A3\u09C0\u0995\u09B0\u09A3\u09C7\u09B0\
  \ \u09B8\u09BE\u09A5\u09C7 \u09AA\u09BE\u09A0\u09BE\u09A8\u09CB \u09AE\u09BE\u09A8\
  \u09C7 \u09B9\u09B2 \u098F\u0995\u099C\u09A8 \u09AC\u09CD\u09AF\u09AC\u09B9\u09BE\
  \u09B0\u0995\u09BE\u09B0\u09C0 \u098F\u09AC\u0982 \u09AA\u09BE\u09B8\u0993\u09AF\
  \u09BC\u09BE\u09B0\u09CD\u09A1\u0995\u09C7 \u098F\u0995\u099F\u09BF \u0985\u09A8\
  \u09C1\u09B0\u09CB\u09A7 \u09B9\u09C7\u09A1\u09BE\u09B0\u09C7 \u09B8\u0982\u09AF\
  \u09C1\u0995\u09CD\u09A4\u09BF \u0995\u09B0\u09BE, \u09AF\u09BE\u09A4\u09C7 \u09AA\
  \u09CD\u09B0\u09AE\u09BE\u09A3 \u0995\u09B0\u09BE \u09AF\u09BE\u09AF\u09BC \u09AF\
  \u09C7 \u0986\u09AA\u09A8\u09BF \u09AA\u09CD\u09B0\u09AC\u09C7\u09B6\u09BE\u09A7\
  \u09BF\u0995\u09BE\u09B0 \u09AA\u09C7\u09A4\u09C7 \u0985\u09A8\u09C1\u09AE\u09CB\
  \u09A6\u09BF\u09A4\u0964 \u0986\u09AE\u09B0\u09BE \u098F\u099F\u09BF \u0995\u09B0\
  \u09BF \u09AF\u0996\u09A8 \u09B8\u09C7\u09AC\u09BE\u0997\u09C1\u09B2\u09BF \u09A8\
  \u09BF\u09B6\u09CD\u099A\u09BF\u09A4 \u09B9\u09A4\u09C7 \u099A\u09BE\u09AF\u09BC\
  \ \u09AF\u09C7 \u0986\u09AA\u09A8\u09BF, \u0995\u09CB\u09A8\u09CB \u099C\u09CB \u09B8\
  \u09CD\u0995\u09CB \u09A8\u09AF\u09BC, \u099C\u09BF\u09A8\u09BF\u09B8 \u0985\u09CD\
  \u09AF\u09BE\u0995\u09CD\u09B8\u09C7\u09B8 \u0995\u09B0\u09BE\u09B0 \u099A\u09C7\
  \u09B7\u09CD\u099F\u09BE \u0995\u09B0\u099B\u09C7\u09A8\u0964."
title: "\u09AC\u09C7\u09B8\u09BF\u0995 \u0985\u09A5\u09C7\u09A8\u09CD\u099F\u09BF\u0995\
  \u09C7\u09B6\u09A8 \u09B8\u09B9 HTTP \u09B0\u09BF\u0995\u09C1\u09DF\u09C7\u09B8\u09CD\
  \u099F \u09AA\u09CD\u09B0\u09C7\u09B0\u09A3"
weight: 45
---

## কিভাবে:
প্রথমে, আপনার `Cargo.toml`-এ প্রয়োজনীয় ক্রেট যুক্ত করুন:

```toml
[dependencies]
reqwest = "0.11"
base64 = "0.13"
```

এখন, মৌলিক প্রমাণীকরণের সাথে একটি GET অনুরোধ পাঠানোর জন্য রাস্ট কোডটি এখানে:

```rust
use reqwest::header::{Authorization, Basic};
use std::error::Error;

#[tokio::main]
async fn main() -> Result<(), Box<dyn Error>> {
    let client = reqwest::Client::new();
    let user = "Aladdin";
    let password = "open sesame";
    
    let auth = Basic {
        username: user.into(),
        password: Some(password.into()),
    };
    
    let response = client
        .get("http://example.com/secrets")
        .header(Authorization(auth))
        .send()
        .await?;
    
    let content = response.text().await?;
    println!("Response: {}", content);
    
    Ok(())
}
```

যদি সব ঠিক থাকে, এটি গোপনীয়তাগুলি প্রিন্ট করবে। আপনি ধারণা পেয়ে যাবেন।

## গভীর অনুসন্ধান
`reqwest` এর আগে, আপনি মানুষকে `curl`-এ রাস্টের সাথে কুস্তি করতে দেখতেন। এটি যেন হ্যান্ডসো এর বিপরীতে চেইনসো পছন্দ করা। মৌলিক প্রমাণীকরণ, যদিও খুব সহজ, ফোর্ট নক্স নয়। এটি শুধুমাত্র "username:password" এর Base64 – কোনো এনক্রিপশন নেই, তাই HTTPS একটি অবশ্যই।

বিকল্প? OAuth 2.0 মৌলিক এর চারিদিকে ঘুরে বেড়ায়, স্পর্শযোগ্য প্রমাণীকরণের পরিবর্তে টোকেন অফার করে। তবে, এটি জটিল। তারপরে আছে বিয়ারার প্রমাণীকরণ, গোপন হাতমিলানের মতো টোকেন ধারণ করে।

অভ্যন্তরে, `reqwest` একটি উচ্চ-স্তরের HTTP ক্লায়েন্ট যা রাস্টের অ্যাসিঙ্ক বৈশিষ্ট্যের সাথে ভালোভাবে মিলে যায়। 'Basic' কাঠামোটি হেডার তৈরি করে, 'Authorization' এটি ভেতরে ঢোকায়, এবং প্রেস্তো, আপনি একটি গোপন ফিসফিসানি দিয়ে সার্ভারের দরজায় কড়া নাড়ছেন।

## আরও দেখুন
আরও লোর এবং জাদুকরীর জন্য:

- reqwest ডকুমেন্টেশন: [https://docs.rs/reqwest](https://docs.rs/reqwest)
- HTTP বেসিক অ্যাক্সেস প্রমাণীকরণ বুঝতে: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication](https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication)
- রাস্ট অ্যাসিঙ্ক প্রোগ্রামিং: [https://rust-lang.github.io/async-book/](https://rust-lang.github.io/async-book/)
- rust base64 ক্রেট ডকুমেন্টেশন: [https://docs.rs/base64](https://docs.rs/base64)
