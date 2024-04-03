---
changelog:
- 2024-03-17, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-17 17:46:33.103794-06:00
description: "\u098F\u0995\u099F\u09BF \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982\u0995\
  \u09C7 lowercase \u098F \u09B0\u09C2\u09AA\u09BE\u09A8\u09CD\u09A4\u09B0 \u0995\u09B0\
  \u09BE \u09AE\u09BE\u09A8\u09C7 \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982\u09DF\
  \u09C7\u09B0 \u09AA\u09CD\u09B0\u09A4\u09BF\u099F\u09BF \u0985\u0995\u09CD\u09B7\
  \u09B0\u0995\u09C7 \u099B\u09CB\u099F \u09B9\u09BE\u09A4\u09C7\u09B0 \u0985\u0995\
  \u09CD\u09B7\u09B0\u09C7 \u09AA\u09B0\u09BF\u09A3\u09A4 \u0995\u09B0\u09BE\u0964\
  \ \u098F\u099F\u09BF \u0995\u09C7\u09B8-\u0987\u09A8\u09B8\u09C7\u09A8\u09B8\u09BF\
  \u099F\u09BF\u09AD \u09A4\u09C1\u09B2\u09A8\u09BE \u0985\u09A5\u09AC\u09BE \u099F\
  \u09C7\u0995\u09CD\u09B8\u099F\u0995\u09C7 \u09B8\u09AE\u0997\u09CD\u09B0\u2026"
lastmod: '2024-03-17T18:47:43.795411-06:00'
model: gpt-4-0125-preview
summary: "\u098F\u0995\u099F\u09BF \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982\u0995\
  \u09C7 lowercase \u098F \u09B0\u09C2\u09AA\u09BE\u09A8\u09CD\u09A4\u09B0 \u0995\u09B0\
  \u09BE \u09AE\u09BE\u09A8\u09C7 \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982\u09DF\
  \u09C7\u09B0 \u09AA\u09CD\u09B0\u09A4\u09BF\u099F\u09BF \u0985\u0995\u09CD\u09B7\
  \u09B0\u0995\u09C7 \u099B\u09CB\u099F \u09B9\u09BE\u09A4\u09C7\u09B0 \u0985\u0995\
  \u09CD\u09B7\u09B0\u09C7 \u09AA\u09B0\u09BF\u09A3\u09A4 \u0995\u09B0\u09BE\u0964\
  \ \u098F\u099F\u09BF \u0995\u09C7\u09B8-\u0987\u09A8\u09B8\u09C7\u09A8\u09B8\u09BF\
  \u099F\u09BF\u09AD \u09A4\u09C1\u09B2\u09A8\u09BE \u0985\u09A5\u09AC\u09BE \u099F\
  \u09C7\u0995\u09CD\u09B8\u099F\u0995\u09C7 \u09B8\u09AE\u0997\u09CD\u09B0 \u09AA\
  \u09CD\u09B0\u0995\u09CD\u09B0\u09BF\u09AF\u09BC\u09BE\u099C\u09BE\u09A4 \u0995\u09B0\
  \u09BE\u09B0 \u099C\u09A8\u09CD\u09AF \u09B8\u09C1\u09AC\u09BF\u09A7\u09BE\u099C\
  \u09A8\u0995\u0964."
title: "\u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982\u0995\u09C7 \u09B2\u09CB\u09AF\u09BC\
  \u09BE\u09B0 \u0995\u09C7\u09B8\u09C7 \u09B0\u09C2\u09AA\u09BE\u09A8\u09CD\u09A4\
  \u09B0 \u0995\u09B0\u09BE"
weight: 4
---

## কিভাবে:
```Rust
fn main() {
    let greeting = "HeLLo, WoRlD!";
    let lowercase_greeting = greeting.to_lowercase();
    println!("{}", lowercase_greeting); // "hello, world!"
}
```
আউটপুট:
```
hello, world!
```

## গভীর অন্বেষণ
`.to_lowercase()` মেথডের পূর্বে, আপনি হয়ত `to_ascii_lowercase()` মেথড ব্যবহার দেখেছেন, যা শুধুমাত্র ASCII অক্ষরগুলির উপর প্রভাব ফেলেছিল। Rust স্ট্যান্ডার্ড লাইব্রেরি উন্নত হয়ে, `.to_lowercase()` এর মাধ্যমে পূর্ণ Unicode সমর্থন প্রদান করেছে—অর্থাৎ এটি শুধু ইংরেজির চেয়ে বেশি কিছু ব্যবহার করতে পারে! যদি আপনার অ্যাপ্লিকেশন বহুভাষিক বিশ্বে পা রাখে, তবে এটি অনেক গুরুত্বপূর্ণ।

আসলে কি আছে? ঠিক আছে, `to_lowercase()` মেথড শুধু `A` থেকে `a` এ পরিবর্তন করে না। এটি বরং এক ধরনের ছোট ভাষাবিদ, Unicode এর পথগুলি জানা। এটি Unicode স্ট্যান্ডার্ডের অনুসরণ করে সঠিকভাবে lowercase অক্ষরগুলি পরিণত করে, তাদের সাংস্কৃতিক বৈশিষ্ট্য সম্মান করে।

অবশ্যই, বিকল্পও আছে। আপনি একটি লুপে ঢুকে, প্রতিটি char দিয়ে এটি নিজে রূপান্তর করতে পারেন। কিন্তু Rust এর স্ট্যান্ডার্ড লাইব্রেরি যখন এই কাজে পরিশ্রম করেছে, তখন নতুন করে চাকা আবিষ্কার করার কি প্রয়োজন?

## আরও দেখুন
- [Rust ডক্স উপর `to_lowercase()`](https://doc.rust-lang.org/std/primitive.str.html#method.to_lowercase)
- [Rust String ডক্স](https://doc.rust-lang.org/std/string/struct.String.html)
- [Unicode কেস ম্যাপিং](https://www.unicode.org/reports/tr21/tr21-5.html)
