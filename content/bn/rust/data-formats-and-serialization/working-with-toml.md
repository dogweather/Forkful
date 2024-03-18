---
title:                "টমল নিয়ে কাজ করা"
date:                  2024-03-17T18:31:08.897475-06:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-17, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## কি এবং কেন?
TOML একটি মানুষের পড়ার উপযোগী ডেটা সিরিয়ালাইজেশন ভাষা, প্রায়ই কনফিগের জন্য ব্যবহৃত হয়। প্রোগ্রামাররা TOML ব্যবহার করে এর সাধারণতা এবং স্পষ্টতার জন্য, যা Rust এ হ্যাশ ম্যাপে সহজে অনুবাদ করা যায়।

## কিভাবে:
```Rust
// 1. আপনার Cargo.toml এ 'toml' crate যুক্ত করুন
// [dependencies]
// toml = "0.5"

// 2. Rust এ একটি struct এ TOML কে Deserialize করুন
use toml::Value;

fn main() {
    let toml_content = r#"
        [server]
        host = "localhost"
        port = 8080
    "#;

    let value = toml_content.parse::<Value>().unwrap();
    let host = value.get("server").unwrap().get("host").unwrap();
    let port = value.get("server").unwrap().get("port").unwrap();
    
    println!("সার্ভার চলছে {}:{}", host, port);
    // আউটপুট: সার্ভার চলছে "localhost":8080
}
```

## গভীর ডাইভ
TOML, যার পূর্ণ নাম Tom's Obvious, Minimal Language, টম প্রেস্টন-ওয়ার্নার দ্বারা ২০১৩ সালে সৃষ্টি করা হয়েছিল। এর লক্ষ্য হল কনফিগ ফাইলের জন্য JSON বা YAML এর চেয়ে আরও পঠনীয় হওয়া। TOML এর নকশা অস্পষ্ট সিনট্যাক্স, ন্যূনতমতার এবং ডাটা টাইপে সহজে মানচিত্রণে মনোনিবেশ করা হয়েছে।

TOML এর বিকল্পগুলি হল JSON, YAML, এবং XML, কিন্তু TOML মানব পাঠযোগ্যতা এবং অ-প্রোগ্রামারের দ্বারা ফাইল সম্পাদনা যে পরিস্থিতিগুলিতে বিশেষ গুরুত্বপূর্ণ, সেইসব পরিস্থিতিতে জয়ী হয়। Rust এ TOML এর সাথে কাজ করার সময়, serde সিরিয়ালাইজেশন এবং ডিসিরিয়ালাইজেশনের জন্য একটি শক্ত ভিত্তি প্রদান করে, TOML কে Rust এর structs এ নিয়ে আসতে ট্রেইটস ব্যবহার করে।

TOML এর সাথে কাজ করার একটি চ্যালেঞ্জ হল এর টাইপ এবং গঠনের উপর কঠোরতা। প্রোগ্রামারকে TOML ডেটার স্কিমাকে সঠিকভাবে ব্যবহার করতে Rust এর একটি ভাল গঠিত টাইপ সিস্টেম নির্ধারণ করতে হবে।

## আরও দেখুন
- [TOML ডকুমেন্টেশন](https://toml.io/en/)
- [serde_toml Crate](https://docs.rs/serde_toml/)
- [Rust প্রোগ্রামিং ভাষার বই](https://doc.rust-lang.org/stable/book/)
- [TOML GitHub রেপো](https://github.com/toml-lang/toml)
