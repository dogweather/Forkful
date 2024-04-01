---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:22:52.621761-06:00
description: "\u098F\u0995\u099F\u09BF \u09A1\u09BF\u09AC\u09BE\u0997\u09BE\u09B0\
  \ \u09AC\u09CD\u09AF\u09AC\u09B9\u09BE\u09B0 \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\
  \u09C7 \u09A8\u09BF\u099C\u09C7\u0995\u09C7 \u098F\u0995\u09CD\u09B8-\u09B0\u09C7\
  \ \u09A6\u09C3\u09B7\u09CD\u099F\u09BF \u09A6\u09BE\u09A8 \u0995\u09B0\u09BE, \u09AF\
  \u09BE\u09A4\u09C7 \u0986\u09AA\u09A8\u09BF \u0986\u09AA\u09A8\u09BE\u09B0 \u0995\
  \u09CB\u09A1\u09C7\u09B0 \u098F\u0995\u09CD\u09B8\u09BF\u0995\u09BF\u0989\u09B6\u09A8\
  \u09C7\u09B0 \u09AD\u09BF\u09A4\u09B0\u09C7 \u0989\u0981\u0995\u09BF \u09A6\u09BF\
  \u09A4\u09C7 \u09AA\u09BE\u09B0\u09C7\u09A8\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\
  \u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u098F\u099F\u09BF \u0995\u09B0\
  \u09C7\u09A8 \u09AC\u09BE\u0997 \u0996\u09C1\u0981\u099C\u09C7\u2026"
lastmod: '2024-03-17T18:47:43.813947-06:00'
model: gpt-4-0125-preview
summary: "\u098F\u0995\u099F\u09BF \u09A1\u09BF\u09AC\u09BE\u0997\u09BE\u09B0 \u09AC\
  \u09CD\u09AF\u09AC\u09B9\u09BE\u09B0 \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\u09C7\
  \ \u09A8\u09BF\u099C\u09C7\u0995\u09C7 \u098F\u0995\u09CD\u09B8-\u09B0\u09C7 \u09A6\
  \u09C3\u09B7\u09CD\u099F\u09BF \u09A6\u09BE\u09A8 \u0995\u09B0\u09BE, \u09AF\u09BE\
  \u09A4\u09C7 \u0986\u09AA\u09A8\u09BF \u0986\u09AA\u09A8\u09BE\u09B0 \u0995\u09CB\
  \u09A1\u09C7\u09B0 \u098F\u0995\u09CD\u09B8\u09BF\u0995\u09BF\u0989\u09B6\u09A8\u09C7\
  \u09B0 \u09AD\u09BF\u09A4\u09B0\u09C7 \u0989\u0981\u0995\u09BF \u09A6\u09BF\u09A4\
  \u09C7 \u09AA\u09BE\u09B0\u09C7\u09A8\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\
  \u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u098F\u099F\u09BF \u0995\u09B0\u09C7\
  \u09A8 \u09AC\u09BE\u0997 \u0996\u09C1\u0981\u099C\u09C7\u2026"
title: "\u09A1\u09BF\u09AC\u09BE\u0997\u09BE\u09B0 \u09AC\u09CD\u09AF\u09AC\u09B9\u09BE\
  \u09B0 \u0995\u09B0\u09BE"
---

## কীভাবে:
রাস্ট বিভিন্ন ডিবাগারকে সমর্থন করে, কিন্তু একটি সাধারণ ডিবাগার হল `gdb` গনু/লিনাক্সের জন্য বা `lldb` macOS এর জন্য। আপনি `rust-gdb` বা `rust-lldb` ও ব্যবহার করতে পারেন, যা রাস্ট মানগুলিকে সুন্দর করে প্রিন্ট করার জন্য র‍্যাপার। এখানে একটি দৃশ্য:

```Rust
fn main() {
    let mut counter = 0;
    for _ in 0..5 {
        counter += 1;
        println!("Counter is at: {}", counter);
    }
}
```

এটি ডিবাগ করতে, ডিবাগ তথ্যের সাথে কম্পাইল করুন:

```shell
$ rustc -g counter.rs
```

তারপর `rust-gdb` তে এটি চালান:

```shell
$ rust-gdb counter
(gdb) break main
(gdb) run
(gdb) print counter
$1 = 0
(gdb) continue
Counter is at: 1
(gdb) print counter
$2 = 1
```

## গভীরে ডুব:
ডিবাগিং পাঞ্চ কার্ডের *প্রাচীন কাল* থেকে আছে, এবং এর অগ্রগতি এক ধরণের অভিশাপ নিরাময় হয়েছে। রাস্ট তার সিস্টেম-লেভেল প্রকৃতির জন্য GDB এবং LLDB এর সাথে ইন্টিগ্রেশনসমূহের সাথে নিজস্ব টুলিং প্রদান করে।

রাস্ট কোড ডিবাগ করার বিকল্পগুলি হল ইন্টিগ্রেটেড ডেভেলপমেন্ট এনভায়রনমেন্টগুলি (IDEs) ব্যবহার করা, যেগুলোর নিজস্ব ডিবাগারগুলি রয়েছে, যা কেউ কেউ আরো অন্তর্জ্ঞানী হিসেবে মনে করেন। জনপ্রিয়গুলির মধ্যে আছে CLion রাস্ট প্লাগিনের সাথে অথবা Visual Studio Code রাস্ট এক্সটেনশনের সাথে।

বাস্তবায়নের ক্ষেত্রে, রাস্ট এমন ডিবাগ প্রতীক জেনারেট করে যা এই ডিবাগারগুলি বুঝতে পারে, যা কোড ধাপে ধাপে পরীক্ষা করা, ব্রেকপয়েন্ট সেট করা, এবং চরগুলি পরীক্ষা করা সহজ করে তোলে আপনার মাথা না হারিয়ে।

## আরও দেখুন
- ডিবাগিং সম্পর্কে রাস্ট বুক: https://doc.rust-lang.org/book/ch09-02-recoverable-errors-with-result.html#guidelines-for-error-handling
- রাস্ট বাই এক্সাম্পলের এরর এবং ডিবাগিং নিয়ে নিবন্ধ: https://doc.rust-lang.org/rust-by-example/error.html
- রাস্ট ল্যাঙ্গুয়েজ সার্ভার (RLS) যা VS Code's রাস্ট এক্সটেনশনকে চালিত করে: https://github.com/rust-lang/rls
- ভিয়ুয়াল স্টুডিও কোড দিয়ে রাস্ট ডিবাগ করা: https://marketplace.visualstudio.com/items?itemName=rust-lang.rust
