---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:29:51.692472-06:00
description: "Rust-\u098F JSON (JavaScript Object Notation) \u09A8\u09BF\u09DF\u09C7\
  \ \u0995\u09BE\u099C \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\u09C7 \u09B9\u09B2 JSON\
  \ \u09A1\u09C7\u099F\u09BE \u0995\u09C7 Rust \u09A1\u09C7\u099F\u09BE \u09B8\u09CD\
  \u099F\u09CD\u09B0\u09BE\u0995\u099A\u09BE\u09B0\u09C7 \u09AA\u09BE\u09B0\u09CD\u09B8\
  \ \u0995\u09B0\u09BE \u098F\u09AC\u0982 \u0986\u09AC\u09BE\u09B0 Rust \u09A1\u09C7\
  \u099F\u09BE \u09B8\u09CD\u099F\u09CD\u09B0\u09BE\u0995\u099A\u09BE\u09B0\u0997\u09C1\
  \u09B2\u09CB\u0995\u09C7 JSON-\u098F\u2026"
lastmod: '2024-03-17T18:47:43.832325-06:00'
model: gpt-4-0125-preview
summary: "Rust-\u098F JSON (JavaScript Object Notation) \u09A8\u09BF\u09DF\u09C7 \u0995\
  \u09BE\u099C \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\u09C7 \u09B9\u09B2 JSON \u09A1\
  \u09C7\u099F\u09BE \u0995\u09C7 Rust \u09A1\u09C7\u099F\u09BE \u09B8\u09CD\u099F\
  \u09CD\u09B0\u09BE\u0995\u099A\u09BE\u09B0\u09C7 \u09AA\u09BE\u09B0\u09CD\u09B8\
  \ \u0995\u09B0\u09BE \u098F\u09AC\u0982 \u0986\u09AC\u09BE\u09B0 Rust \u09A1\u09C7\
  \u099F\u09BE \u09B8\u09CD\u099F\u09CD\u09B0\u09BE\u0995\u099A\u09BE\u09B0\u0997\u09C1\
  \u09B2\u09CB\u0995\u09C7 JSON-\u098F\u2026"
title: "JSON \u098F\u09B0 \u09B8\u09BE\u09A5\u09C7 \u0995\u09BE\u099C \u0995\u09B0\
  \u09BE"
---

{{< edit_this_page >}}

## কি এবং কেন?

Rust-এ JSON (JavaScript Object Notation) নিয়ে কাজ করা মানে হল JSON ডেটা কে Rust ডেটা স্ট্রাকচারে পার্স করা এবং আবার Rust ডেটা স্ট্রাকচারগুলোকে JSON-এ সিরিয়ালাইজ করা। প্রোগ্রামাররা ওয়েব API-সমূহ, কনফিগারেশন ফাইল বা JSON ব্যবহৃত যেকোনো ডেটা এক্সচেঞ্জ ফরম্যাটের সাথে ইন্টার্যাক্ট করার জন্য এটি করে থাকে, এর হালকা ও মানব-পাঠ্য ফরম্যাটের কারণে।

## কিভাবে:

Rust-এ JSON নিয়ে কাজ করার জন্য, `serde` ক্রেট এবং সিরিয়ালাইজেশন এবং ডিসিরিয়ালাইজেশনের জন্য `serde_json` ব্যাপকভাবে ব্যবহৃত হয়। প্রথমে, আপনার `Cargo.toml`-এ এগুলো অন্তর্ভুক্ত করা নিশ্চিত করুন:

```toml
[dependencies]
serde = { version = "1.0", features = ["derive"] }
serde_json = "1.0"
```

### উদাহরণ 1: JSON থেকে Rust Struct-এ ডিসিরিয়ালাইজ করা

একটি Rust struct সংজ্ঞায়িত করুন এবং `Deserialize` এবং `Serialize` জন্য ডেরাইভ ম্যাক্রোস ব্যবহার করুন:

```rust
use serde::{Deserialize, Serialize};

#[derive(Serialize, Deserialize)]
struct User {
    id: u32,
    name: String,
    email: String,
}

fn main() {
    let json_data = r#"
        {
            "id": 1,
            "name": "Jane Doe",
            "email": "jane.doe@example.com"
        }
    "#;

    let user: User = serde_json::from_str(json_data).unwrap();

    println!("User ID: {}", user.id);
    println!("User Name: {}", user.name);
    println!("User Email: {}", user.email);
}
```

**আউটপুট:**

```
User ID: 1
User Name: Jane Doe
User Email: jane.doe@example.com
```

### উদাহরণ 2: Rust Struct থেকে JSON এ সিরিয়ালাইজ করা

একই `User` স্ট্রাক্ট ব্যবহার করে:

```rust
let user = User {
    id: 1,
    name: "Jane Doe".to_string(),
    email: "jane.doe@example.com".to_string(),
};

let json_data = serde_json::to_string(&user).unwrap();

println!("{}", json_data);
```

**আউটপুট:**

```json
{"id":1,"name":"Jane Doe","email":"jane.doe@example.com"}
```

এই উদাহরণগুলি JSON থেকে Rust স্ট্রাকচারে ডিসিরিয়ালাইজিং এবং Rust স্ট্রাকচারগুলি আবার JSON স্ট্রিং-এ সিরিয়ালাইজ করার মৌলিক প্রক্রিয়াটি দেখায়। Serde JSON নিয়ে কাজ করার জন্য ধনী সেট অফ টুলস সরবরাহ করে, যাতে ঐচ্ছিক ফিল্ড, জটিল নেস্টিং এবং JSON সরাসরি সমর্থন না করে এমন টাইপগুলি নিয়ে কাজ করা অন্তর্ভুক্ত আছে।
