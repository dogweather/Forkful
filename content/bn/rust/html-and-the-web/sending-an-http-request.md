---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:18:10.226636-06:00
description: "HTTP \u0985\u09A8\u09C1\u09B0\u09CB\u09A7 \u09AA\u09BE\u09A0\u09BE\u09A8\
  \u09CB \u09AE\u09BE\u09A8\u09C7 \u0993\u09AF\u09BC\u09C7\u09AC \u09B8\u09BE\u09B0\
  \u09CD\u09AD\u09BE\u09B0 \u09A5\u09C7\u0995\u09C7 \u09A1\u09C7\u099F\u09BE \u0986\
  \u09A8\u09BE \u09AC\u09BE \u09A1\u09C7\u099F\u09BE \u09AA\u09BE\u09A0\u09BE\u09A8\
  \u09CB\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\
  \u09BE \u0993\u09AF\u09BC\u09C7\u09AC \u09B8\u09C7\u09B0\u09BE \u09AC\u09BE APIs\
  \ \u098F\u09B0 \u09B8\u09BE\u09A5\u09C7 \u09AE\u09BF\u09A5\u09B8\u09CD\u0995\u09CD\
  \u09B0\u09BF\u09AF\u09BC\u09BE \u0995\u09B0\u09A4\u09C7 \u098F\u099F\u09BF \u0995\
  \u09B0\u09C7\u09A8 - \u09A4\u09A5\u09CD\u09AF \u0986\u09A8\u09BE, \u0986\u09AA\u09A1\
  \u09C7\u099F\u2026"
lastmod: '2024-03-17T18:47:43.805830-06:00'
model: gpt-4-0125-preview
summary: "HTTP \u0985\u09A8\u09C1\u09B0\u09CB\u09A7 \u09AA\u09BE\u09A0\u09BE\u09A8\
  \u09CB \u09AE\u09BE\u09A8\u09C7 \u0993\u09AF\u09BC\u09C7\u09AC \u09B8\u09BE\u09B0\
  \u09CD\u09AD\u09BE\u09B0 \u09A5\u09C7\u0995\u09C7 \u09A1\u09C7\u099F\u09BE \u0986\
  \u09A8\u09BE \u09AC\u09BE \u09A1\u09C7\u099F\u09BE \u09AA\u09BE\u09A0\u09BE\u09A8\
  \u09CB\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\
  \u09BE \u0993\u09AF\u09BC\u09C7\u09AC \u09B8\u09C7\u09B0\u09BE \u09AC\u09BE APIs\
  \ \u098F\u09B0 \u09B8\u09BE\u09A5\u09C7 \u09AE\u09BF\u09A5\u09B8\u09CD\u0995\u09CD\
  \u09B0\u09BF\u09AF\u09BC\u09BE \u0995\u09B0\u09A4\u09C7 \u098F\u099F\u09BF \u0995\
  \u09B0\u09C7\u09A8 - \u09A4\u09A5\u09CD\u09AF \u0986\u09A8\u09BE, \u0986\u09AA\u09A1\
  \u09C7\u099F \u09AA\u09CB\u09B7\u09CD\u099F \u0995\u09B0\u09BE, \u0986\u09AA\u09A8\
  \u09BF \u09AF\u09BE \u09AC\u09B2\u09AC\u09C7\u09A8\u0964."
title: "HTTP \u0985\u09A8\u09C1\u09B0\u09CB\u09A7 \u09AA\u09CD\u09B0\u09C7\u09B0\u09A3\
  \ \u0995\u09B0\u09BE"
weight: 44
---

## কিভাবে:
Rust-এ GET অনুরোধ পাঠানোর জন্য, আমরা `reqwest` crate ব্যবহার করি। প্রথমে, এটিকে আপনার `Cargo.toml`-এ যোগ করুন:

```toml
[dependencies]
reqwest = "0.11"
tokio = { version = "1", features = ["full"] }
```

এখন, কিছু অ্যাসিঙ্ক রাস্ট কোড তৈরি করুন:

```rust
use reqwest;
use tokio;

#[tokio::main]
async fn main() -> Result<(), reqwest::Error> {
    let response_text = reqwest::get("https://api.example.com/data")
        .await?
        .text()
        .await?;
    
    println!("প্রতিক্রিয়া: {}", response_text);
    Ok(())
}
```

নমুনা আউটপুট এরকম দেখাতে পারে:

```
প্রতিক্রিয়া: {"key": "value", "hello": "world"}
```

একটি GET অনুরোধ দিয়ে একটি endpoint এ আঘাত করা এতটাই প্রয়োজনীয়!

## গভীর ডুব
HTTP অনুরোধগুলি ইন্টারনেট বছর হিসেবে পাহাড়ের মতো পুরানো। এগুলি ওয়েব-ভিত্তিক যোগাযোগের মেরুদণ্ড। Rust ওয়েব-নির্দিষ্ট ভাষা নয় বলে `reqwest` এর মতো crates ব্যবহার করে - নমনীয়তা মুখ্য। `reqwest` `hyper` এর উপর নির্মিত, যা দ্রুত এবং নিম্ন-স্তরীয়, কিন্তু `reqwest` এর উপরে ব্যবহারের সুবিধা যোগ করে।

`reqwest`-এর বিকল্প? অবশ্যই। `hyper` গতির জন্য, `surf` আপনি যদি অ্যাসিঙ্ক রাস্টে আগ্রহী হন অথবা `ureq` সহজতার জন্য - অ্যাসিঙ্কের ঝামেলা দরকার নেই। 

প্রকৃতপক্ষে, যখন আপনি একটি HTTP অনুরোধ পাঠান, রাস্ট যা করে তা প্রায় যেকোনো ভাষার মতোই: একটি TCP সংযোগ স্থাপন করা, একটি ফর্ম্যাটেড HTTP অনুরোধ পাঠানো, এবং কাঁচা প্রতিক্রিয়া বিশ্লেষণ করা। এই অনুরোধগুলির অ্যাসিঙ্ক্রোনাস হ্যান্ডলিং হল যেখানে রাস্ট উজ্জ্বল, আপনি সার্ভারের উত্তরের অপেক্ষা করতে করতে অন্যান্য কাজ করতে পারবেন।

## আরও দেখুন
- [reqwest ডকুমেন্টেশন](https://docs.rs/reqwest/)
- [The Rust Async Book](https://rust-lang.github.io/async-book/)
- [Hyper HTTP লাইব্রেরি](https://hyper.rs/)
- [API নির্দেশিকা](https://rust-lang.github.io/api-guidelines/)
