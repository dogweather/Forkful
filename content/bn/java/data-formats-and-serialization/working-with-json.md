---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:29:48.560213-06:00
description: "JSON (JavaScript Object Notation) \u098F\u09B0 \u09B8\u09BE\u09A5\u09C7\
  \ \u0995\u09BE\u099C \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\u09C7 \u0986\u09AA\u09A8\
  \u09BE\u09B0 Java \u0985\u09CD\u09AF\u09BE\u09AA\u09CD\u09B2\u09BF\u0995\u09C7\u09B6\
  \u09A8\u09C7\u09B0 \u09AD\u09BF\u09A4\u09B0\u09C7 \u098F\u0987 \u09B9\u09BE\u09B2\
  \u0995\u09BE \u09A1\u09BE\u099F\u09BE-\u0987\u09A8\u09CD\u099F\u09BE\u09B0\u099A\
  \u09C7\u099E\u09CD\u099C \u09AB\u09B0\u09AE\u09CD\u09AF\u09BE\u099F\u09C7\u09B0\
  \ \u09B8\u09BE\u09A5\u09C7 \u09AE\u09CB\u0995\u09BE\u09AC\u09BF\u09B2\u09BE \u0995\
  \u09B0\u09BE\u0964\u2026"
lastmod: '2024-03-17T18:47:43.927261-06:00'
model: gpt-4-0125-preview
summary: "JSON (JavaScript Object Notation) \u098F\u09B0 \u09B8\u09BE\u09A5\u09C7\
  \ \u0995\u09BE\u099C \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\u09C7 \u0986\u09AA\u09A8\
  \u09BE\u09B0 Java \u0985\u09CD\u09AF\u09BE\u09AA\u09CD\u09B2\u09BF\u0995\u09C7\u09B6\
  \u09A8\u09C7\u09B0 \u09AD\u09BF\u09A4\u09B0\u09C7 \u098F\u0987 \u09B9\u09BE\u09B2\
  \u0995\u09BE \u09A1\u09BE\u099F\u09BE-\u0987\u09A8\u09CD\u099F\u09BE\u09B0\u099A\
  \u09C7\u099E\u09CD\u099C \u09AB\u09B0\u09AE\u09CD\u09AF\u09BE\u099F\u09C7\u09B0\
  \ \u09B8\u09BE\u09A5\u09C7 \u09AE\u09CB\u0995\u09BE\u09AC\u09BF\u09B2\u09BE \u0995\
  \u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\
  \u09B0\u09BE \u09A8\u09C7\u099F\u0993\u09AF\u09BC\u09BE\u09B0\u09CD\u0995\u09C7\u09B0\
  \ \u0989\u09AA\u09B0 \u09B8\u09CD\u099F\u09CD\u09B0\u09BE\u0995\u099A\u09BE\u09B0\
  \ \u0995\u09B0\u09BE \u09A1\u09BE\u099F\u09BE \u09B8\u09BF\u09B0\u09BF\u09AF\u09BC\
  \u09BE\u09B2\u09BE\u0987\u099C \u098F\u09AC\u0982 \u099F\u09CD\u09B0\u09BE\u09A8\
  \u09CD\u09B8\u09AE\u09BF\u099F \u0995\u09B0\u09BE\u09B0 \u099C\u09A8\u09CD\u09AF\
  \ \u098F\u09AC\u0982 \u09A1\u09BE\u099F\u09BE \u09B8\u09B9\u099C\u09C7\u0987 \u0995\
  \u09A8\u09AB\u09BF\u0997\u09BE\u09B0 \u098F\u09AC\u0982 \u09B8\u09CD\u099F\u09CB\
  \u09B0 \u0995\u09B0\u09BE\u09B0 \u099C\u09A8\u09CD\u09AF \u099C\u09C7\u09B8\u09A8\
  \u09C7\u09B0 \u09A6\u09BF\u0995\u09C7 \u099D\u09C1\u0981\u0995\u09C7 \u09A5\u09BE\
  \u0995\u09C7, \u0995\u09BE\u09B0\u09A3 \u098F\u099F\u09BF \u09AE\u09BE\u09A8\u09AC\
  -\u09AA\u09A0\u09A8\u09AF\u09CB\u0997\u09CD\u09AF \u098F\u09AC\u0982 \u09AD\u09BE\
  \u09B7\u09BE-\u09B8\u09CD\u09AC\u09A4\u09A8\u09CD\u09A4\u09CD\u09B0\u0964."
title: "JSON \u098F\u09B0 \u09B8\u09BE\u09A5\u09C7 \u0995\u09BE\u099C \u0995\u09B0\
  \u09BE"
weight: 38
---

## কিভাবে:
চলুন আমরা আমাদের হাতাঘাতি উঠাই এবং Java-তে JSON এর সাথে কোডিং শুরু করি।

প্রথমত, আপনার একটি JSON প্রক্রিয়াকরণ লাইব্রেরির প্রয়োজন হবে যেমন `Jackson` অথবা `Google Gson`। এখানে আমরা `Jackson` ব্যবহার করব, তাই আপনার `pom.xml`-এ এই ডিপেনডেন্সি যোগ করুন:

```xml
<dependency>
    <groupId>com.fasterxml.jackson.core</groupId>
    <artifactId>jackson-databind</artifactId>
    <version>2.13.1</version>
</dependency>
```

এখন, চলুন আমরা একটি সাধারণ Java অবজেক্টকে JSON-এ সিরিয়ালাইজ (লিখি):

```java
import com.fasterxml.jackson.databind.ObjectMapper;

public class JsonExample {
    public static void main(String[] args) {
        try {
            ObjectMapper mapper = new ObjectMapper();
            Person person = new Person("Alex", 30);
            String json = mapper.writeValueAsString(person);
            System.out.println(json);
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}

class Person {
    public String name;
    public int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```

আউটপুট হওয়া উচিত:

```json
{"name":"Alex","age":30}
```

এখন, JSON-কে আবার Java অবজেক্টে ডিসিরিয়ালাইজ (পড়া) এর জন্য:

```java
import com.fasterxml.jackson.databind.ObjectMapper;

public class JsonExample {
    public static void main(String[] args) {
        String json = "{\"name\":\"Alex\",\"age\":30}";
        try {
            ObjectMapper mapper = new ObjectMapper();
            Person person = mapper.readValue(json, Person.class);
            System.out.println(person.name + " এর বয়স " + person.age + " বছর।");
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

আউটপুট হবে:

```
Alex এর বয়স 30 বছর।
```

## গভীরে ডুব:
JSON-এর সাধারণতা এবং কার্যকারিতা ওয়েবে ডাটা এক্সচেঞ্জের জন্য ডি ফ্যাক্টো মানদণ্ডে পরিণত করেছে, XML-কে তার সিংহাসন থেকে উল্টে দিয়েছে। ২০০০-এর দশকের প্রারম্ভে প্রবর্তিত, JSON JavaScript থেকে উদ্ভূত হলেও এখন তা বেশিরভাগ ভাষাতেই সমর্থিত।

JSON-এর বিকল্প হিসাবে XML আছে, যা বিস্তারিত ভাষা, এবং Protocol Buffers অথবা MessagePack মতো বাইনারি ফর্ম্যাট আছে, যা মানব-পঠনযোগ্যতায় কম কিন্তু আকার এবং গতিতে বেশি দক্ষ। প্রতি ফরম্যাটের ব্যবহারিক ক্ষেত্র আছে; বাছাই আপনার নির্দিষ্ট ডাটা চাহিদা এবং প্রেক্ষাপটের উপর নির্ভর করে।

Java-তে, `Jackson` এবং `Gson` ছাড়াও, আমাদের কাছে `JsonB` এবং `org.json` হিসাবে আরো লাইব্রেরি আছে যা JSON সম্পর্কিত কাজে লাগে। Jackson স্ট্রিম-ভিত্তিক প্রক্রিয়াকরণ প্রদান করে এবং গতির জন্য পরিচিত, যেখানে Gson এর ব্যবহারের সহজতার জন্য প্রশংসিত হয়। JsonB হলো Jakarta EE-র অংশ, যা আরও মানকীকৃত পদ্ধতি প্রদান করে।

JSON বাস্তবায়ন করার সময়, খারাপ ইনপুটের বিরুদ্ধে আপনার কোডকে মজবুত করার জন্য সঠিকভাবে আপনার ব্যতিক্রমগুলি সামলান - এবং স্বয়ংক্রিয় ডেটা বাইন্ডিংয়ের নিরাপত্তা প্রভাব বিবেচনা করে নিন - সবসময় আপনার ইনপুটগুলি যাচাই করুন!

## আরও দেখুন
- [Jackson প্রকল্প](https://github.com/FasterXML/jackson)
- [Gson প্রকল্প](https://github.com/google/gson)
- [JSON স্পেসিফিকেশন](https://www.json.org/json-en.html)
- [JsonB স্পেসিফিকেশন](https://jakarta.ee/specifications/jsonb/)
