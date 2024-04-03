---
date: 2024-01-20 18:00:20.777171-07:00
description: "\u05E9\u05DC\u05D9\u05D7\u05EA \u05D1\u05E7\u05E9\u05EA HTTP \u05D4\u05D9\
  \u05D0 \u05D3\u05E8\u05DA \u05DC\u05EA\u05E7\u05E9\u05E8 \u05E2\u05DD \u05E9\u05E8\
  \u05EA\u05D9\u05DD \u05D1\u05D0\u05D9\u05E0\u05D8\u05E8\u05E0\u05D8 - \u05D0\u05EA\
  \u05D4 \u05E9\u05D5\u05D0\u05DC \u05DE\u05E9\u05D4\u05D5, \u05D4\u05DD \u05E2\u05D5\
  \u05E0\u05D9\u05DD. \u05EA\u05DB\u05E0\u05D9\u05EA\u05E0\u05D9\u05DD \u05E9\u05D5\
  \u05DC\u05D7\u05D9\u05DD \u05D1\u05E7\u05E9\u05D5\u05EA \u05DB\u05D0\u05DC\u05D4\
  \ \u05DB\u05D3\u05D9 \u05DC\u05E7\u05D1\u05DC \u05E0\u05EA\u05D5\u05E0\u05D9\u05DD\
  , \u05DC\u05E9\u05DC\u05D5\u05D7 \u05DE\u05D9\u05D3\u05E2, \u05D0\u05D5 \u05DC\u05D1\
  \u05E6\u05E2 \u05E4\u05E2\u05D5\u05DC\u05D5\u05EA \u05DE\u05E8\u05D7\u05D5\u05E7\
  ."
lastmod: '2024-03-13T22:44:39.125534-06:00'
model: gpt-4-1106-preview
summary: "\u05E9\u05DC\u05D9\u05D7\u05EA \u05D1\u05E7\u05E9\u05EA HTTP \u05D4\u05D9\
  \u05D0 \u05D3\u05E8\u05DA \u05DC\u05EA\u05E7\u05E9\u05E8 \u05E2\u05DD \u05E9\u05E8\
  \u05EA\u05D9\u05DD \u05D1\u05D0\u05D9\u05E0\u05D8\u05E8\u05E0\u05D8 - \u05D0\u05EA\
  \u05D4 \u05E9\u05D5\u05D0\u05DC \u05DE\u05E9\u05D4\u05D5, \u05D4\u05DD \u05E2\u05D5\
  \u05E0\u05D9\u05DD."
title: "\u05E9\u05DC\u05D9\u05D7\u05EA \u05D1\u05E7\u05E9\u05EA HTTP"
weight: 44
---

## איך לעשות:
ב-Java, שליחת בקשת HTTP היא די פשוטה. חלק מהדוגמאות ישתמשו בממשק `HttpClient`, המבוסס על יכולות שהוצגו ב-Java 11:

```Java
import java.net.URI;
import java.net.http.HttpClient;
import java.net.http.HttpRequest;
import java.net.http.HttpResponse;

public class HttpExample {
    public static void main(String[] args) {
        HttpClient client = HttpClient.newHttpClient();
        HttpRequest request = HttpRequest.newBuilder()
                .uri(URI.create("https://api.example.com/data"))
                .build();
        client.sendAsync(request, HttpResponse.BodyHandlers.ofString())
                .thenApply(HttpResponse::body)
                .thenAccept(System.out::println)
                .join();
    }
}
```

אם הכל עובד כמו שצריך, יודפס תוכן הבקשה שקיבלת.

## עיון מעמיק:
במשך שנים, שליחת בקשות HTTP ב-Java היתה קשה יותר. תכניתנים נאלצו להשתמש ב-`HttpURLConnection` או ספריות חיצוניות כמו Apache HttpClient. מ-Java 11 והלאה, הממשק `HttpClient` מספק דרך ישירה ומודרנית יותר. הוא כולל תמיכה ב-HTTP/2, שליחת בקשות אסינכרוניות ועוד.

אלטרנטיבות ל-`HttpClient` כוללות ספריות פופולריות כמו OkHttp וRetrofit, שמספקות יכולות נוספות וחוויית משתמש נעימה יותר לאנשים שעובדים הרבה עם REST APIs.

## ראה גם:
- [Documentation for the `HttpClient`](https://docs.oracle.com/en/java/javase/11/docs/api/java.net.http/java/net/http/HttpClient.html) - תיעוד רשמי מאורקל.
- [OkHttp](https://square.github.io/okhttp/) - דף הבית של OkHttp להורדות ותיעוד.
- [Retrofit](https://square.github.io/retrofit/) - דף הבית של Retrofit להורדות ותיעוד.
