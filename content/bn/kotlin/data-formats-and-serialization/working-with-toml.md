---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:30:34.491493-06:00
description: "TOML \u09B9\u099A\u09CD\u099B\u09C7 Tom's Obvious, Minimal Language\
  \ \u098F\u09B0 \u09B8\u0982\u0995\u09CD\u09B7\u09C7\u09AA\u0964 \u098F\u099F\u09BF\
  \ \u09AE\u09BE\u09A8\u09AC\u09C7\u09B0 \u09AA\u09A1\u09BC\u09BE\u09B0 \u098F\u09AC\
  \u0982 \u09B2\u09C7\u0996\u09BE\u09B0 \u099C\u09A8\u09CD\u09AF \u09B8\u09B9\u099C\
  , \u09A4\u09AC\u09C1\u0993 \u09AE\u09C7\u09B6\u09BF\u09A8\u09C7\u09B0 \u09A6\u09CD\
  \u09AC\u09BE\u09B0\u09BE \u09AA\u09BE\u09B0\u09CD\u09B8 \u0995\u09B0\u09BE \u09B8\
  \u09B9\u099C \u09AC\u09B2\u09C7 \u0995\u09A8\u09AB\u09BF\u0997\u09BE\u09B0\u09C7\
  \u09B6\u09A8 \u09AB\u09BE\u0987\u09B2\u09C7\u09B0 \u099C\u09A8\u09CD\u09AF\u2026"
lastmod: '2024-03-17T18:47:44.018001-06:00'
model: gpt-4-0125-preview
summary: "TOML \u09B9\u099A\u09CD\u099B\u09C7 Tom's Obvious, Minimal Language \u098F\
  \u09B0 \u09B8\u0982\u0995\u09CD\u09B7\u09C7\u09AA\u0964 \u098F\u099F\u09BF \u09AE\
  \u09BE\u09A8\u09AC\u09C7\u09B0 \u09AA\u09A1\u09BC\u09BE\u09B0 \u098F\u09AC\u0982\
  \ \u09B2\u09C7\u0996\u09BE\u09B0 \u099C\u09A8\u09CD\u09AF \u09B8\u09B9\u099C, \u09A4\
  \u09AC\u09C1\u0993 \u09AE\u09C7\u09B6\u09BF\u09A8\u09C7\u09B0 \u09A6\u09CD\u09AC\
  \u09BE\u09B0\u09BE \u09AA\u09BE\u09B0\u09CD\u09B8 \u0995\u09B0\u09BE \u09B8\u09B9\
  \u099C \u09AC\u09B2\u09C7 \u0995\u09A8\u09AB\u09BF\u0997\u09BE\u09B0\u09C7\u09B6\
  \u09A8 \u09AB\u09BE\u0987\u09B2\u09C7\u09B0 \u099C\u09A8\u09CD\u09AF\u2026"
title: "\u099F\u09AE\u09B2 \u09A8\u09BF\u09AF\u09BC\u09C7 \u0995\u09BE\u099C \u0995\
  \u09B0\u09BE"
---

{{< edit_this_page >}}

## কি এবং কেন?
TOML হচ্ছে Tom's Obvious, Minimal Language এর সংক্ষেপ। এটি মানবের পড়ার এবং লেখার জন্য সহজ, তবুও মেশিনের দ্বারা পার্স করা সহজ বলে কনফিগারেশন ফাইলের জন্য ব্যবহৃত হয়। ডেভেলপাররা কনফিগ সংক্রান্ত কাজে XML এর জটিলতা এবং JSON এর কৌশলগত সমস্যা এড়াতে TOML এর দিকে ঝোঁকে।

## কিভাবে:
Kotlin এ TOML নিয়ে কাজ করার জন্য, আপনি `ktoml` এর মতো একটা লাইব্রেরি ব্যবহার করতে পারেন। প্রথমে, আপনার `build.gradle.kts` ফাইলে নির্ভরতা যোগ করা যাক:

```kotlin
dependencies {
    implementation("com.akuleshov7:ktoml:0.2.5")
}
```

এখন, আসুন কিছু TOML পার্স করি:

```kotlin
import com.akuleshov7.ktoml.file.TomlFileReader

fun main() {
    val tomlContent = TomlFileReader.readAndParseFile("config.toml")
    
    val databaseConfig = tomlContent.getTable("database")
    val host = databaseConfig.getString("host")
    val port = databaseConfig.getLong("port")

    println("Database Host: $host")
    println("Database Port: $port")
}
```

ধরা যাক, `config.toml` এইরকম দেখাচ্ছে:

```toml
[database]
host = "localhost"
port = 5432
```

নমুনা আউটপুট হবে:

```
Database Host: localhost
Database Port: 5432
```

## গভীর ডুব
TOML, ২০১৩ সালে GitHub এর সহ-প্রতিষ্ঠাতা Tom Preston-Werner দ্বারা তৈরি, YAML এর চেয়ে সরল এবং JSON এর চেয়ে টাইপ-নিরাপদ হতে লক্ষ্য করেছিল। Rust এর `Cargo` এবং Go এর মডিউল সিস্টেমের সাথে এটি বিশেষভাবে জনপ্রিয় হয়ে উঠেছে। বিকল্প? YAML এর আরও বেশি বৈশিষ্ট্য আছে, JSON অনেক কোডিং ভাষায় সরাসরি অবজেক্টে পরিণত হয়, এবং XML সবসময় একটি ভালো বিকল্প। বাস্তবায়নে, ktoml, Apache 2.0 লাইসেন্সের অধীনে, একটি শুদ্ধ Kotlin লাইব্রেরি এবং Java লাইব্রেরীগুলি নিয়ে আসে না, পাঠন মাত্র নয়, লেখার জন্যও DSL সরবরাহ করে।

## আরও দেখুন
- TOML GitHub: https://github.com/toml-lang/toml
- ktoml GitHub: https://github.com/akuleshov7/ktoml
- TOML vs. YAML vs. JSON: https://blog.logrocket.com/comparing-configuration-files-yaml-toml-json/
