---
changelog:
- 2024-03-17, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-17 17:47:41.147330-06:00
description: "\u098F\u0995\u099F\u09BF \u0993\u09AF\u09BC\u09C7\u09AC \u09AA\u09C7\
  \u099C \u09A1\u09BE\u0989\u09A8\u09B2\u09CB\u09A1 \u0995\u09B0\u09BE \u09AE\u09BE\
  \u09A8\u09C7 \u09A8\u09BF\u09B0\u09CD\u09A6\u09BF\u09B7\u09CD\u099F \u098F\u0995\
  \u099F\u09BF URL \u09A5\u09C7\u0995\u09C7 \u098F\u0987\u099A\u099F\u09BF\u098F\u09AE\
  \u098F\u09B2 \u0986\u09A8\u09BE \u09AF\u09BE\u09A4\u09C7 \u09B8\u09CD\u09A5\u09BE\
  \u09A8\u09C0\u09AF\u09BC\u09AD\u09BE\u09AC\u09C7 \u09A6\u09C7\u0996\u09BE \u09AF\
  \u09BE\u09DF \u0985\u09A5\u09AC\u09BE \u09AC\u09CD\u09AF\u09AC\u09B9\u09BE\u09B0\
  \ \u0995\u09B0\u09BE \u09AF\u09BE\u09DF\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\
  \u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u0993\u09AF\u09BC\u09C7\u09AC \u09B8\
  \u09CD\u0995\u09CD\u09B0\u09CD\u09AF\u09BE\u09AA\u09BF\u0982,\u2026"
lastmod: '2024-03-17T18:47:43.992055-06:00'
model: gpt-4-0125-preview
summary: "\u098F\u0995\u099F\u09BF \u0993\u09AF\u09BC\u09C7\u09AC \u09AA\u09C7\u099C\
  \ \u09A1\u09BE\u0989\u09A8\u09B2\u09CB\u09A1 \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\
  \u09C7 \u09A8\u09BF\u09B0\u09CD\u09A6\u09BF\u09B7\u09CD\u099F \u098F\u0995\u099F\
  \u09BF URL \u09A5\u09C7\u0995\u09C7 \u098F\u0987\u099A\u099F\u09BF\u098F\u09AE\u098F\
  \u09B2 \u0986\u09A8\u09BE \u09AF\u09BE\u09A4\u09C7 \u09B8\u09CD\u09A5\u09BE\u09A8\
  \u09C0\u09AF\u09BC\u09AD\u09BE\u09AC\u09C7 \u09A6\u09C7\u0996\u09BE \u09AF\u09BE\
  \u09DF \u0985\u09A5\u09AC\u09BE \u09AC\u09CD\u09AF\u09AC\u09B9\u09BE\u09B0 \u0995\
  \u09B0\u09BE \u09AF\u09BE\u09DF\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\
  \u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u0993\u09AF\u09BC\u09C7\u09AC \u09B8\u09CD\
  \u0995\u09CD\u09B0\u09CD\u09AF\u09BE\u09AA\u09BF\u0982, \u0985\u09AB\u09B2\u09BE\
  \u0987\u09A8 \u09AA\u09BE\u09A0\u0995\u09BE\u09B2\u09C7 \u09AC\u09BE \u09B8\u09CD\
  \u09AC\u09AF\u09BC\u0982\u0995\u09CD\u09B0\u09BF\u09AF\u09BC \u09AA\u09B0\u09C0\u0995\
  \u09CD\u09B7\u09A3\u09C7\u09B0 \u09AE\u09A4\u09CB \u0995\u09BE\u099C\u09C7\u09B0\
  \ \u099C\u09A8\u09CD\u09AF \u098F\u099F\u09BF \u0995\u09B0\u09C7\u09A8\u0964."
title: "\u098F\u0995\u099F\u09BF \u0993\u09AF\u09BC\u09C7\u09AC\u09AA\u09C7\u099C\
  \ \u09A1\u09BE\u0989\u09A8\u09B2\u09CB\u09A1 \u0995\u09B0\u09BE"
weight: 42
---

## কিভাবে:
আসুন কোটলিনের `HttpURLConnection` ব্যবহার করে দ্রুত একটি ওয়েব পেজ আনি। আমরা সুচারু পটভূমি অপারেশনের জন্য করুটিনসও ব্যবহার করবো। এখানে একটি মূলধারা:

```kotlin
import java.net.HttpURLConnection
import java.net.URL
import kotlinx.coroutines.*

fun main() = runBlocking {
    val url = "http://example.com"
    val result = withContext(Dispatchers.IO) {
        downloadWebPage(url)
    }
    println(result)
}

fun downloadWebPage(urlAddress: String): String {
    val url = URL(urlAddress)
    val connection = url.openConnection() as HttpURLConnection
    চেষ্টা করুন {
        connection.connect()
        return connection.inputStream.bufferedReader().use { it.readText() }
    } অবশেষে {
        connection.disconnect()
    }
}
```

নমুনা আউটপুট:

```
<!doctype html>
<html>
<head>
    <title>Example Domain</title>
...
</html>
```
ভালো লাগলো, তাই না? আপনি ওয়েব পেজের এইচটিএমএল পেয়ে গেছেন!

## গভীর ডুব
ওয়েব পেজ ডাউনলোড করা ওয়েব এর শুরু থেকে পুরোনো প্রক্রিয়া। ৯০ এর দশকে, লোকেরা `wget` এবং `curl` এর মতো কমান্ড-লাইন টুলস ব্যবহার করত। এগুলো এখনো ব্যবহার হয় কিন্তু আরও নিয়ন্ত্রণ বা অ্যাপে ওয়েব সামগ্রী আনার কাজে যখন আপনি ইচ্ছা করেন, আপনি কোডিং করেন।

কোটলিনে, আপনি জাভার `HttpURLConnection` বা OkHttp বা Ktor এর মতো লাইব্রেরিগুলো ব্যবহার করতে পারেন যা অধিক বৈশিষ্ট্যাবলী সহ শক্তিশালী পদ্ধতি প্রদান করে। উপরের উদাহরণটি সাধারণ; বাস্তব জীবনে, আপনি ভুল সংশোধন, রিডিরেক্ট, এবং পারফরমেন্সের বিষয়ে চিন্তা করতেন। হয়তো রিট্রাই অথবা টাইমআউট যোগ করতে পারেন? এবং ভিন্ন ক্যারেক্টার এনকোডিংস এবং কন্টেন্ট টাইপগুলি সম্পর্কিত আচরণ সম্পর্কে ভুলবেন না।

আপনি থ্রেডিংও বিবেচনা করতেন। বিশাল পেজ আনতে গিয়ে মূল থ্রেডকে ঝুলিয়ে রাখতে চাইবেন না, তাই না? এখানেই করুটিনস প্রয়োজন - এগুলো আপনার অ্যাপকে সাড়া দিতে দেয়, পটভূমিতে আনতে ডাউনলোড করতে দেয় ঘাম ছাড়া।

## দেখুন আরও
- **OkHttp**: https://square.github.io/okhttp/
- **Ktor Client**: https://ktor.io/docs/client.html
- **Kotlin Coroutines**: https://kotlinlang.org/docs/coroutines-overview.html
- **Java HttpURLConnection**: https://docs.oracle.com/javase/8/docs/api/java/net/HttpURLConnection.html

এটা সূত্রটি—পেজটি পেতে, এটা সম্বন্ধে বুদ্ধিমান হতে, এবং সর্বদা ডাটা এবং এর উৎসকে সম্মান করা। সুখী কোডিং!
