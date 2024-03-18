---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:19:22.693062-06:00
description: "\u09AC\u09C7\u09B8\u09BF\u0995 \u0985\u09A5\u09C7\u09A8\u099F\u09BF\u0995\
  \u09C7\u09B6\u09A8 HTTP \u0985\u09A8\u09C1\u09B0\u09CB\u09A7\u09C7 \u098F\u0995\u099F\
  \u09BF \u09AC\u09CD\u09AF\u09AC\u09B9\u09BE\u09B0\u0995\u09BE\u09B0\u09C0\u09B0\
  \ \u09A8\u09BE\u09AE:\u09AA\u09BE\u09B8\u0993\u09AF\u09BC\u09BE\u09B0\u09CD\u09A1\
  \ \u0985\u09AD\u09BF\u09A8\u09AF\u09BC \u09AF\u09CB\u0997 \u0995\u09B0\u09C7\u0964\
  \ \u09A1\u09C7\u09AD\u09C7\u09B2\u09AA\u09BE\u09B0\u09B0\u09BE \u0993\u09AF\u09BC\
  \u09C7\u09AC\u09C7 \u0995\u09C7 \u0995\u09BF \u099A\u09BE\u09AF\u09BC \u09A4\u09BE\
  \ \u09AA\u09CD\u09B0\u09AE\u09BE\u09A3\u09C7\u09B0 \u099C\u09A8\u09CD\u09AF \u098F\
  \u099F\u09BF \u098F\u0995\u099F\u09BF \u09A6\u09CD\u09B0\u09C1\u09A4-\u098F\u09AC\
  \u0982-\u09AE\u09AF\u09BC\u09B2\u09BE\u2026"
lastmod: '2024-03-17T18:47:43.993012-06:00'
model: gpt-4-0125-preview
summary: "\u09AC\u09C7\u09B8\u09BF\u0995 \u0985\u09A5\u09C7\u09A8\u099F\u09BF\u0995\
  \u09C7\u09B6\u09A8 HTTP \u0985\u09A8\u09C1\u09B0\u09CB\u09A7\u09C7 \u098F\u0995\u099F\
  \u09BF \u09AC\u09CD\u09AF\u09AC\u09B9\u09BE\u09B0\u0995\u09BE\u09B0\u09C0\u09B0\
  \ \u09A8\u09BE\u09AE:\u09AA\u09BE\u09B8\u0993\u09AF\u09BC\u09BE\u09B0\u09CD\u09A1\
  \ \u0985\u09AD\u09BF\u09A8\u09AF\u09BC \u09AF\u09CB\u0997 \u0995\u09B0\u09C7\u0964\
  \ \u09A1\u09C7\u09AD\u09C7\u09B2\u09AA\u09BE\u09B0\u09B0\u09BE \u0993\u09AF\u09BC\
  \u09C7\u09AC\u09C7 \u0995\u09C7 \u0995\u09BF \u099A\u09BE\u09AF\u09BC \u09A4\u09BE\
  \ \u09AA\u09CD\u09B0\u09AE\u09BE\u09A3\u09C7\u09B0 \u099C\u09A8\u09CD\u09AF \u098F\
  \u099F\u09BF \u098F\u0995\u099F\u09BF \u09A6\u09CD\u09B0\u09C1\u09A4-\u098F\u09AC\
  \u0982-\u09AE\u09AF\u09BC\u09B2\u09BE\u2026"
title: "\u09AC\u09C7\u09B8\u09BF\u0995 \u0985\u09A5\u09C7\u09A8\u09CD\u099F\u09BF\u0995\
  \u09C7\u09B6\u09A8 \u09B8\u09B9 HTTP \u09B0\u09BF\u0995\u09C1\u09DF\u09C7\u09B8\u09CD\
  \u099F \u09AA\u09CD\u09B0\u09C7\u09B0\u09A3"
---

{{< edit_this_page >}}

## কি এবং কেন?

বেসিক অথেনটিকেশন HTTP অনুরোধে একটি ব্যবহারকারীর নাম:পাসওয়ার্ড অভিনয় যোগ করে। ডেভেলপাররা ওয়েবে কে কি চায় তা প্রমাণের জন্য এটি একটি দ্রুত-এবং-ময়লা উপায় হিসেবে ব্যবহার করে।

## কিভাবে:

Kotlin লাইব্রেরি `ktor` অথবা `okhttp`-র মতো লাইব্রেরি দ্বারা HTTP অনুরোধগুলি সম্পাদন করে। এখন আমরা `okhttp` দিয়ে শুরু করব।

প্রথমে, আপনার build.gradle এ লাইব্রেরিটি যোগ করুন:

```groovy
dependencies {
    implementation("com.squareup.okhttp3:okhttp:4.9.0")
}
```

কোডিং শুরু করুন:

```kotlin
import okhttp3.Credentials
import okhttp3.OkHttpClient
import okhttp3.Request
import java.io.IOException

fun main() {
    val client = OkHttpClient()

    val username = "admin"
    val password = "password123"
    val credentials = Credentials.basic(username, password)

    val request = Request.Builder()
        .url("http://example.com/resource")
        .header("Authorization", credentials)
        .build()

    client.newCall(request).execute().use { response ->
        if (!response.isSuccessful) throw IOException("Unexpected code $response")

        println(response.body!!.string())
    }
}
```

রান বাটনে ক্লিক করুন এবং আপনার কনসোল দেখুন। আপনি নিরাপদ সম্পদ ফাঁস হতে দেখা উচিৎ।

## গভীর ডুব

প্রাচীন সময়ে, HTTP বেসিক অথ ছিল যা যেতে হবে। সহজ: কেবল `username:password`-কে base64-এ পরিণত করুন এবং এটি হেডারে যোগ করুন। একা একা নিরাপদ নয়, তাই HTTPS পার্টি যোগ দেয়।

বিকল্প? অনেক। টোকেনের জন্য OAuth, সাধারণতার জন্য API কী, অথবা একটি আপগ্রেডের জন্য ডাইজেস্ট অথেনটিকেশন। বেসিক অথ শুরু করার জন্য বা অভ্যন্তরীণ টুলসের জন্য ভালো, কিন্তু আধুনিক, নিরাপত্তা-সচেতন ওয়েবের জন্য নয়।

বাস্তবায়নের বিস্তারিত: চাকা আবিষ্কার করবেন না। লাইব্রেরিগুলি এনকোডিং এবং প্রোটোকলের নৈপুণ্যগুলি সম্পাদন করে। OkHttp এমনকি রিট্রাই এবং সংযোগের জন্য আপনার হয়ে কাজ করে। মনে রাখবেন, HTTP-র ওপর বেসিক অথ একটি না চলা পথ—সবসময় HTTPS ব্যবহার করুন ট্রানজিটে প্রমাণপত্রগুলি নিরাপদ রাখতে।

## আরও দেখুন

- OkHttp-র অফিসিয়াল ডকুমেন্টেশন: [https://square.github.io/okhttp/](https://square.github.io/okhttp/)
- কোটলিন ভাষার পাতা (সমস্ত কোটলিন বিষয়ক): [https://kotlinlang.org/](https://kotlinlang.org/)
- বেসিক অথ সম্পর্কে আরো জানুন: [https://tools.ietf.org/html/rfc7617](https://tools.ietf.org/html/rfc7617)
- বেসিক অথের বিকল্প যেমন OAuth 2.0: [https://oauth.net/2/](https://oauth.net/2/)
