---
changelog:
- 2024-03-17, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-17 17:47:51.233350-06:00
description: "\u0993\u09AF\u09BC\u09C7\u09AC \u09AA\u09C7\u099C \u09A1\u09BE\u0989\
  \u09A8\u09B2\u09CB\u09A1 \u0995\u09B0\u09BE\u09B0 \u0985\u09B0\u09CD\u09A5 \u09B9\
  \u09B2\u09CB \u098F\u09B0 \u09AC\u09BF\u09B7\u09AF\u09BC\u09AC\u09B8\u09CD\u09A4\
  \u09C1, \u09AF\u09C7\u09AE\u09A8 HTML, CSS, \u098F\u09AC\u0982 JavaScript \u09AA\
  \u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09C7\u099F\u09BF\u0995\u09AD\u09BE\
  \u09AC\u09C7 \u0997\u09CD\u09B0\u09B9\u09A3 \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\
  \u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u09A4\u09BE\u09A5\
  \u09CD\u09AF \u09AA\u09CD\u09B0\u0995\u09CD\u09B0\u09BF\u09AF\u09BC\u09BE\u099C\u09BE\
  \u09A4 \u0995\u09B0\u09A4\u09C7,\u2026"
lastmod: '2024-03-17T18:47:43.903084-06:00'
model: gpt-4-0125-preview
summary: "\u0993\u09AF\u09BC\u09C7\u09AC \u09AA\u09C7\u099C \u09A1\u09BE\u0989\u09A8\
  \u09B2\u09CB\u09A1 \u0995\u09B0\u09BE\u09B0 \u0985\u09B0\u09CD\u09A5 \u09B9\u09B2\
  \u09CB \u098F\u09B0 \u09AC\u09BF\u09B7\u09AF\u09BC\u09AC\u09B8\u09CD\u09A4\u09C1\
  , \u09AF\u09C7\u09AE\u09A8 HTML, CSS, \u098F\u09AC\u0982 JavaScript \u09AA\u09CD\
  \u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09C7\u099F\u09BF\u0995\u09AD\u09BE\u09AC\
  \u09C7 \u0997\u09CD\u09B0\u09B9\u09A3 \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\
  \u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u09A4\u09BE\u09A5\u09CD\
  \u09AF \u09AA\u09CD\u09B0\u0995\u09CD\u09B0\u09BF\u09AF\u09BC\u09BE\u099C\u09BE\u09A4\
  \ \u0995\u09B0\u09A4\u09C7, \u09AA\u09B0\u09BF\u09AC\u09B0\u09CD\u09A4\u09A8 \u09AA\
  \u09B0\u09CD\u09AF\u09AC\u09C7\u0995\u09CD\u09B7\u09A3 \u0995\u09B0\u09A4\u09C7\
  \ \u0985\u09A5\u09AC\u09BE \u09A4\u09BE\u09A6\u09C7\u09B0 \u0993\u09AF\u09BC\u09C7\
  \u09AC \u0985\u09CD\u09AF\u09BE\u09AA\u09B8 \u09AA\u09B0\u09C0\u0995\u09CD\u09B7\
  \u09BE \u0995\u09B0\u09A4\u09C7 \u098F\u099F\u09BF \u0995\u09B0\u09C7 \u09A5\u09BE\
  \u0995\u09C7\u09A8\u0964."
title: "\u098F\u0995\u099F\u09BF \u0993\u09AF\u09BC\u09C7\u09AC\u09AA\u09C7\u099C\
  \ \u09A1\u09BE\u0989\u09A8\u09B2\u09CB\u09A1 \u0995\u09B0\u09BE"
weight: 42
---

## কীভাবে:
```java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.net.URL;

public class WebPageDownloader {
    public static void main(String[] args) {
        String urlStr = "http://example.com";
        try {
            URL url = new URL(urlStr);
            try (BufferedReader reader = new BufferedReader(new InputStreamReader(url.openStream()))) {
                String line;
                while ((line = reader.readLine()) != null) {
                    System.out.println(line);
                }
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

নমুনা আউটপুট এরকম দেখাবে:

```
<!doctype html>
<html>
<head>
    <title>Example Domain</title>
    ...
</head>
...
</html>
```

## গভীরে ডুব দেয়া
আগের দিনগুলিতে, ওয়েব পেজ ডাউনলোড করা অতি সাধারণ ছিল—HTTP সহজ ছিল, ওয়েবসাইটগুলি বেশিরভাগ স্ট্যাটিক HTML ছিল। আজকের ওয়েব জটিল—HTTPS, JavaScript-নির্ভর বিষয়বস্তু, এবং AJAX প্লাবন ভেবে দেখুন।

স্ট্যাটিক বিষয়বস্তুর জন্য, `java.net.URL` এবং `java.net.HttpURLConnection` সরাসরি পছন্দ—না ঝঙ্কার, শুধু কাজ করে। কিন্তু যদি আপনি JavaScript দ্বারা লোড করা ডাইনামিক বিষয়বস্তুর সাইটগুলিকে লক্ষ্য করেন, অন্য টুল্স যেমন Selenium বা HtmlUnit ব্যবহার করা দরকার হবে।

ভুলবেন না, ডাউনলোড করা পৃষ্ঠাটির সাথে আপনি কি করতে চান সেটির উপর সঠিক টুল নির্বাচন করা নির্ভর করে। HTML পার্স করা? Jsoup আপনার বন্ধু। JavaScript বাস্তবায়ন করা? একটি হেডলেস ব্রাউজার বিবেচনা করুন। `java.net` ক্লাসগুলি শুধু বরফের চূড়া কিন্তু তা সাধারণ ওয়েবপেজ থেকে তথ্য স্ক্র্যাপিং বা দ্রুত কাজের জন্য উপযুক্ত।

ভদ্রতা নীতির কথা মনে রাখবেন: দ্রুত পরপর অনুরোধের সাথে একটি সাইটকে ঘায়েল করবেন না, নাহলে নিষিদ্ধ করার জন্য আপনার দাবি জানানো হবে। এবং আপনি যে ওয়েবসাইটের `robots.txt` নির্দেশিকা দ্বারা সুন্দরভাবে খেলছেন তা নিশ্চিত করুন।

## দেখুন এছাড়াও
- HTML পার্সিং এবং এক্সট্র্যাকশনের জন্য [Jsoup লাইব্রেরি](https://jsoup.org/)।
- জাভা স্ক্রিপ্ট বাস্তবায়নসহ আরো জটিল কাজের জন্য [Selenium WebDriver](https://www.selenium.dev/documentation/en/webdriver/)।
- জাভার অন্তর্নির্মিত উপায় দ্বারা HTTP মোকাবেলার বিস্তারিত জানতে [HttpURLConnection](https://docs.oracle.com/javase/8/docs/api/java/net/HttpURLConnection.html) গাইড।
- [HtmlUnit](http://htmlunit.sourceforge.net/), জাভা প্রোগ্রামের জন্য "GUI-লেস ব্রাউজার", জাভাস্ক্রিপ্ট-ভারী পেজের জন্য দুর্দান্ত।
