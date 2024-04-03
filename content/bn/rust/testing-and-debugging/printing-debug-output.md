---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:08:21.773965-06:00
description: "\u09A1\u09BF\u09AC\u09BE\u0997 \u0986\u0989\u099F\u09AA\u09C1\u099F\
  \ \u09AE\u09C1\u09A6\u09CD\u09B0\u09A3 \u0986\u09AA\u09A8\u09BE\u0995\u09C7 \u0986\
  \u09AA\u09A8\u09BE\u09B0 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09C7\
  \u09B0 \u0985\u09AC\u09B8\u09CD\u09A5\u09BE \u09A6\u09C7\u0996\u09A4\u09C7 \u09A6\
  \u09C7\u09AF\u09BC \u09AF\u09C7\u0996\u09BE\u09A8\u09C7 \u09AA\u09C2\u09B0\u09CD\
  \u09A3\u09BE\u0999\u09CD\u0997 \u09A1\u09BF\u09AC\u09BE\u0997\u09BE\u09B0\u09C7\u09B0\
  \ \u09AA\u09CD\u09B0\u09AF\u09BC\u09CB\u099C\u09A8 \u09A8\u09C7\u0987\u0964 \u098F\
  \u099F\u09BF \u09A6\u09CD\u09B0\u09C1\u09A4, \u0985\u0997\u09CB\u099B\u09BE\u09B2\
  \u09CB, \u098F\u09AC\u0982 \u09AF\u0996\u09A8 \u0986\u09AA\u09A8\u09BE\u0995\u09C7\
  \ \u09A8\u09BF\u09AC\u09C7\u09A6\u09BF\u09A4 \u09A1\u09BF\u09AC\u09BE\u0997\u09BF\
  \u0982\u2026"
lastmod: '2024-03-17T18:47:43.811967-06:00'
model: gpt-4-0125-preview
summary: "\u09A1\u09BF\u09AC\u09BE\u0997 \u0986\u0989\u099F\u09AA\u09C1\u099F \u09AE\
  \u09C1\u09A6\u09CD\u09B0\u09A3 \u0986\u09AA\u09A8\u09BE\u0995\u09C7 \u0986\u09AA\
  \u09A8\u09BE\u09B0 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09C7\u09B0\
  \ \u0985\u09AC\u09B8\u09CD\u09A5\u09BE \u09A6\u09C7\u0996\u09A4\u09C7 \u09A6\u09C7\
  \u09AF\u09BC \u09AF\u09C7\u0996\u09BE\u09A8\u09C7 \u09AA\u09C2\u09B0\u09CD\u09A3\
  \u09BE\u0999\u09CD\u0997 \u09A1\u09BF\u09AC\u09BE\u0997\u09BE\u09B0\u09C7\u09B0\
  \ \u09AA\u09CD\u09B0\u09AF\u09BC\u09CB\u099C\u09A8 \u09A8\u09C7\u0987\u0964 \u098F\
  \u099F\u09BF \u09A6\u09CD\u09B0\u09C1\u09A4, \u0985\u0997\u09CB\u099B\u09BE\u09B2\
  \u09CB, \u098F\u09AC\u0982 \u09AF\u0996\u09A8 \u0986\u09AA\u09A8\u09BE\u0995\u09C7\
  \ \u09A8\u09BF\u09AC\u09C7\u09A6\u09BF\u09A4 \u09A1\u09BF\u09AC\u09BE\u0997\u09BF\
  \u0982 \u099F\u09C1\u09B2\u09C7\u09B0 \u09B6\u0995\u09CD\u09A4\u09BF\u09B0 \u09AA\
  \u09CD\u09B0\u09AF\u09BC\u09CB\u099C\u09A8 \u09B9\u09AF\u09BC \u09A8\u09BE \u09A4\
  \u0996\u09A8 \u099C\u09C7\u09A6\u09BF \u09AC\u09BE\u0997\u0997\u09C1\u09B2\u09BF\
  \ \u0985\u09A8\u09C1\u09B8\u09B0\u09A3 \u0995\u09B0\u09BE\u09B0 \u099C\u09A8\u09CD\
  \u09AF \u09A8\u09BF\u0996\u09C1\u0981\u09A4\u0964."
title: "\u09A1\u09BF\u09AC\u09BE\u0997 \u0986\u0989\u099F\u09AA\u09C1\u099F \u09AA\
  \u09CD\u09B0\u09BF\u09A8\u09CD\u099F \u0995\u09B0\u09BE"
weight: 33
---

## কিভাবে:
একটি সাধারণ কিছু মুদ্রণ করতে, `println!` ব্যবহার করুন। যদি আপনাকে ডিবাগিংয়ের জন্য একটি মান মুদ্রণ করা প্রয়োজন হয়, তখন `dbg!` সুবিধাজনক হতে পারে।

```Rust
fn main() {
    let mut vec = vec![1, 2, 3];
    
    // বেসিক মুদ্রণ
    println!("হ্যালো, রাস্টেশিয়ানরা!");

    // `{:?}` ব্যবহার করে println! এর সাথে ডিবাগ ফরম্যাটিং 
    println!("{:?}", vec);

    // `dbg!` এর সাথে ডিবাগ, stderr তে মুদ্রণ করে এবং মান ফেরত দেয়
    dbg!(&vec);

    // `dbg!` ব্যবহার করার পর vec পরিবর্তন 
    vec.push(4);
    dbg!(vec);
}
```

নমুনা আউটপুট:

```
হ্যালো, রাস্টেশিয়ানরা!
[1, 2, 3]
[src/main.rs:9] &vec = [
    1,
    2,
    3,
]
[src/main.rs:13] vec = [
    1,
    2,
    3,
    4,
]
```

## গভীর ডাইভ
ডিবাগ আউটপুট মুদ্রণ প্রোগ্রামিংয়ের প্রাথমিক দিনগুলিতে একটি সরল অংশ হিসেবে ছিল। এর সাদাসিদে প্রায়ই সমস্যাগুলি দ্রুত নির্ণয় করার জন্য একে একটি পছন্দনীয় পছন্দে পরিণত করে।

রাস্টে, `println!` ব্যবহারকারী-বান্ধব বার্তাগুলি প্রদর্শনের জন্য দারুণ। যাদু মূলত `dbg!` এর সাথে আসে, যা রাস্ট 1.32 এ প্রবর্তিত হয়, এটি কোডে তার অবস্থানটির সাথে মানটি মুদ্রণ করে। এটি স্ট্যান্ডার্ড ত্রুটি (stderr) তে আউটপুট দেয়, তাই এটি স্ট্যান্ডার্ড আউটপুট (stdout) এর সাথে মিশে যাবে না এবং প্রয়োজন হলে আলাদাভাবে পুনঃনির্দেশ করা যেতে পারে।

জটিল ধরণের জন্য, আপনি `Debug` ট্রেইট অনুকরণ করতে পারেন যা স্বয়ংক্রিয়ভাবে `println!` এবং `dbg!` ব্যবহার করে একটি ফরম্যাট তৈরি করে। এটা আপনার স্ট্রাকচার এবং ইনামগুলির উপরে `#[derive(Debug)]` এনোটেশন করে যা করে।

বিকল্প হিসেবে, যেমন `log` এবং `env_logger` মত সঠিক লগারগুলি বিদ্যমান, এবং আপনি যদি আরও নির্দিষ্ট নিয়ন্ত্রণ চান, বিবেচনা করুন `gdb` অথবা `lldb` মত ডিবাগার যা `rust-gdb` অথবা `rust-lldb` মত ইন্টিগ্রেশনের মাধ্যমে রাস্টের সাথে কাজ করে।

## আরও দেখুন
রাস্টের ডিবাগ মুদ্রণ ও ফরম্যাটিং অপশনের বিষয়ে আরও জানতে:

- `println!` এবং ফর্ম্যাটিং সম্পর্কে রাস্ট বুক: https://doc.rust-lang.org/std/fmt/index.html
- `dbg!` ম্যাক্রো ডকুমেন্টেশন: https://doc.rust-lang.org/std/macro.dbg.html
- `gdb` এবং `lldb` এর সাথে ডিবাগিং সম্পর্কে অফিসিয়াল গাইড: https://rust-lang.github.io/rustup-components-history
- লগিং-এর জন্য আরও গঠিত পদ্ধতি হিসাবে `log` ক্রেট: https://crates.io/crates/log
- `log` ফ্যাসাডের জন্য একটি সাধারণ লগার বাস্তবায়ন, `env_logger` ক্রেট: https://crates.io/crates/env_logger
