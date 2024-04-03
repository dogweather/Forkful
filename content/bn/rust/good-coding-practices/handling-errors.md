---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 17:51:11.819883-06:00
description: "\u09A4\u09CD\u09B0\u09C1\u099F\u09BF \u09B8\u09BE\u09AE\u09B2\u09BE\u09A8\
  \u09CB \u09AE\u09BE\u09A8\u09C7 \u09B9\u09B2 \u09AF\u0996\u09A8 \u099C\u09BF\u09A8\
  \u09BF\u09B8\u09AA\u09A4\u09CD\u09B0 \u09AD\u09C1\u09B2 \u09A6\u09BF\u0995\u09C7\
  \ \u09AF\u09BE\u09DF \u09A4\u0996\u09A8 \u09A4\u09BE\u09A6\u09C7\u09B0 \u09B8\u09BE\
  \u09AE\u09B2\u09BE\u09A8\u09CB\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\
  \u09AE\u09BE\u09B0\u09B0\u09BE \u098F\u099F\u09BF \u0995\u09B0\u09C7 \u0985\u09AA\
  \u09CD\u09B0\u09A4\u09CD\u09AF\u09BE\u09B6\u09BF\u09A4 \u0998\u099F\u09A8\u09BE\
  \ \u09B8\u09AE\u09CD\u09AD\u09BE\u09AC\u09A8\u09BE \u09AE\u09CB\u0995\u09BE\u09AC\
  \u09C7\u09B2\u09BE \u0995\u09B0\u09A4\u09C7, \u09A8\u09BF\u09B6\u09CD\u099A\u09BF\
  \u09A4 \u0995\u09B0\u09BE\u09B0 \u099C\u09A8\u09CD\u09AF \u09AF\u09C7\u2026"
lastmod: '2024-03-17T18:47:43.817168-06:00'
model: gpt-4-0125-preview
summary: "\u09A4\u09CD\u09B0\u09C1\u099F\u09BF \u09B8\u09BE\u09AE\u09B2\u09BE\u09A8\
  \u09CB \u09AE\u09BE\u09A8\u09C7 \u09B9\u09B2 \u09AF\u0996\u09A8 \u099C\u09BF\u09A8\
  \u09BF\u09B8\u09AA\u09A4\u09CD\u09B0 \u09AD\u09C1\u09B2 \u09A6\u09BF\u0995\u09C7\
  \ \u09AF\u09BE\u09DF \u09A4\u0996\u09A8 \u09A4\u09BE\u09A6\u09C7\u09B0 \u09B8\u09BE\
  \u09AE\u09B2\u09BE\u09A8\u09CB\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\
  \u09AE\u09BE\u09B0\u09B0\u09BE \u098F\u099F\u09BF \u0995\u09B0\u09C7 \u0985\u09AA\
  \u09CD\u09B0\u09A4\u09CD\u09AF\u09BE\u09B6\u09BF\u09A4 \u0998\u099F\u09A8\u09BE\
  \ \u09B8\u09AE\u09CD\u09AD\u09BE\u09AC\u09A8\u09BE \u09AE\u09CB\u0995\u09BE\u09AC\
  \u09C7\u09B2\u09BE \u0995\u09B0\u09A4\u09C7, \u09A8\u09BF\u09B6\u09CD\u099A\u09BF\
  \u09A4 \u0995\u09B0\u09BE\u09B0 \u099C\u09A8\u09CD\u09AF \u09AF\u09C7 \u09A4\u09BE\
  \u09A6\u09C7\u09B0 Rust \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u0997\
  \u09C1\u09B2\u09CB \u09B6\u0995\u09CD\u09A4\u09BF\u09B6\u09BE\u09B2\u09C0 \u098F\
  \u09AC\u0982 \u0995\u09CB\u09A8 \u099B\u09CB\u099F\u09CD\u099F \u09AC\u09BE\u09A7\
  \u09BE\u09DF \u0995\u09C7\u09AC\u09B2 \u09AC\u09A8\u09CD\u09A7 \u09A8\u09BE \u09B9\
  \u09DF\u09C7 \u09AF\u09BE\u09DF\u0964."
title: "\u09A4\u09CD\u09B0\u09C1\u099F\u09BF\u0997\u09C1\u09B2\u09BF \u09AA\u09B0\u09BF\
  \u099A\u09BE\u09B2\u09A8\u09BE \u0995\u09B0\u09BE"
weight: 16
---

## কিভাবে:
Rust ত্রুটি সামলায় দুটি প্রধান উপায়ে: পুনরুদ্ধারযোগ্য এবং অপুনরুদ্ধারযোগ্য ত্রুটি। দেখা যাক উভয়কে।

পুনরুদ্ধারযোগ্য ত্রুটি `Result<T, E>` ব্যবহার করে:

```Rust
use std::fs::File;

fn open_file(filename: &str) -> Result<File, std::io::Error> {
    let f = File::open(filename);
    
    match f {
        Ok(file) => Ok(file),
        Err(e) => Err(e),
    }
}

fn main() {
    match open_file("hello.txt") {
        Ok(_file) => println!("ফাইল সফলভাবে খোলা হয়েছে।"),
        Err(_e) => println!("ফাইল খুলতে ব্যর্থ হয়েছে।"),
    }
}
```

আউটপুট হতে পারে "ফাইল সফলভাবে খোলা হয়েছে।" অথবা "ফাইল খুলতে ব্যর্থ হয়েছে।" আপনার `hello.txt` এর উপর নির্ভর করে।

অপুনরুদ্ধারযোগ্য ত্রুটির জন্য, আমরা `panic!` ব্যবহার করি:

```Rust
fn main() {
    // এটি প্রোগ্রামটিকে প্যানিক করাবে কারণ ফাইলটি সম্ভবত অস্তিত্বে নেই।
    let _f = File::open("nowhere.txt").unwrap();
}
```

এটা চালান, এবং আপনি একটি প্যানিক বার্তা দেখতে পাবেন। আপনার প্রোগ্রাম সরাসরি থেমে যাবে।

## গভীর ডুব
ঐতিহাসিকভাবে, প্রোগ্রামিংয়ে ত্রুটি সামলানো একটি জটিল ব্যাপার হয়ে উঠেছিল। Rust এটি ঠিক করে দেয় পুনরুদ্ধারযোগ্য এবং অপুনরুদ্ধারযোগ্য ত্রুটির মধ্যে স্পষ্ট পার্থক্য এনে।

`Result` ইনাম পুনরুদ্ধারযোগ্য ত্রুটির জন্য। এটি স্পষ্ট – আপনি `Ok` বা `Err` ভ্যারিয়েন্ট সামলান। আপনার কাছে `unwrap()` এবং `expect()` মতো পদ্ধতিগুলোও আছে, কিন্তু সেগুলো দ্রুত এবং নোংরা শর্টকাট যা `panic!` এ পরিণত হতে পারে।

`panic!` হল Rust’s এর উপায় বলতে যে কিছু সত্যি খারাপ ঘটেছে, এবং এটা সামলাতে পারছে না। এটি এমন একটি অপুনরুদ্ধারযোগ্য ত্রুটি যা সাথে সাথে নির্বাহ বন্ধ করে দেয়। Rust এ প্যানিক প্রায়শই অনুভূত হয় যে ত্রুটিগুলোর সম্মুখীন হওয়ার কথা আপনি ভাবেননি, যেমন অ্যারের সীমার বাইরে সূচনা।

`Result` দ্বারা ত্রুটি হ্যান্ডলিং পছন্দনীয় যখন আপনি ত্রুটি সম্মুখীন হতে প্রত্যাশা করেন। এটি ঐতিহ্যগত Rust, যার মানে হল এটি Rust ডেভেলপারদের করার ঐক্যমত্য উপায়। `Option<T>` ও আছে, যখন একটি ত্রুটি কেবল `None` বলে বিবেচনা করা হয় পরিবর্তে `Some(T)`। এটি সব কিছু অপ্রত্যাশিত ছাড়াই মোকাবেলা করার ব্যাপা�
