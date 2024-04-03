---
date: 2024-01-20 17:39:24.304740-07:00
description: "Converting a string to lowercase means making every letter in the string\
  \ a small letter. It's handy for case-insensitive comparisons or preparing text\
  \ for\u2026"
lastmod: '2024-03-13T22:44:59.884286-06:00'
model: gpt-4-1106-preview
summary: Converting a string to lowercase means making every letter in the string
  a small letter.
title: Converting a string to lower case
weight: 4
---

## How to:
```Rust
fn main() {
    let greeting = "HeLLo, WoRlD!";
    let lowercase_greeting = greeting.to_lowercase();
    println!("{}", lowercase_greeting); // "hello, world!"
}
```
Output:
```
hello, world!
```

## Deep Dive
Before the `.to_lowercase()` method, you might have seen Rustaceans using `.to_ascii_lowercase()` for the same task, which only affected ASCII characters. The Rust standard library evolved, offering `.to_lowercase()` for full Unicode support—meaning it can handle more than just English! This matters a lot if your app steps out into the wider, multilingual world.

What's under the hood? Well, the `to_lowercase()` method isn't just swapping out 'A' to 'a'. It's more like a tiny linguist, knowledgeable in Unicode's ways. It follows the Unicode standard to correctly lowercase characters respecting their cultural nuances. 

Of course, there are alternatives. You can bust out a loop, plow through each char, and convert it yourself. But why reinvent the wheel when Rust's standard library has put in the work?

## See Also
- [Rust docs on `to_lowercase()`](https://doc.rust-lang.org/std/primitive.str.html#method.to_lowercase)
- [Rust String docs](https://doc.rust-lang.org/std/string/struct.String.html)
- [Unicode case mapping](https://www.unicode.org/reports/tr21/tr21-5.html)
