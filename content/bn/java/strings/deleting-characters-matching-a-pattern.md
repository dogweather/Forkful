---
changelog:
- 2024-03-17, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-17 17:47:32.994930-06:00
description: "\u098F\u0995\u099F\u09BF \u09AA\u09CD\u09AF\u09BE\u099F\u09BE\u09B0\u09CD\
  \u09A8\u09C7\u09B0 \u09B8\u09BE\u09A5\u09C7 \u09AE\u09BF\u09B2\u09C7 \u09AF\u09BE\
  \u0993\u09AF\u09BC\u09BE \u0985\u0995\u09CD\u09B7\u09B0\u0997\u09C1\u09B2\u09BF\
  \ \u09AE\u09C1\u099B\u09C7 \u09AB\u09C7\u09B2\u09BE\u09B0 \u0985\u09B0\u09CD\u09A5\
  \ \u09B9\u09B2 \u098F\u0995\u099F\u09BF \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982\
  \ \u09A5\u09C7\u0995\u09C7 \u09A8\u09BF\u09B0\u09CD\u09A6\u09BF\u09B7\u09CD\u099F\
  \ \u0985\u0995\u09CD\u09B7\u09B0\u09C7\u09B0 \u0995\u09CD\u09B0\u09AE \u0996\u09C1\
  \u0981\u099C\u09C7 \u09AC\u09C7\u09B0 \u0995\u09B0\u09BE \u098F\u09AC\u0982 \u09A4\
  \u09BE \u09A6\u09C2\u09B0 \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\
  \u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u09A1\u09C7\u099F\u09BE\u2026"
lastmod: '2024-03-17T18:47:43.886950-06:00'
model: gpt-4-0125-preview
summary: "\u098F\u0995\u099F\u09BF \u09AA\u09CD\u09AF\u09BE\u099F\u09BE\u09B0\u09CD\
  \u09A8\u09C7\u09B0 \u09B8\u09BE\u09A5\u09C7 \u09AE\u09BF\u09B2\u09C7 \u09AF\u09BE\
  \u0993\u09AF\u09BC\u09BE \u0985\u0995\u09CD\u09B7\u09B0\u0997\u09C1\u09B2\u09BF\
  \ \u09AE\u09C1\u099B\u09C7 \u09AB\u09C7\u09B2\u09BE\u09B0 \u0985\u09B0\u09CD\u09A5\
  \ \u09B9\u09B2 \u098F\u0995\u099F\u09BF \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982\
  \ \u09A5\u09C7\u0995\u09C7 \u09A8\u09BF\u09B0\u09CD\u09A6\u09BF\u09B7\u09CD\u099F\
  \ \u0985\u0995\u09CD\u09B7\u09B0\u09C7\u09B0 \u0995\u09CD\u09B0\u09AE \u0996\u09C1\
  \u0981\u099C\u09C7 \u09AC\u09C7\u09B0 \u0995\u09B0\u09BE \u098F\u09AC\u0982 \u09A4\
  \u09BE \u09A6\u09C2\u09B0 \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\
  \u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u09A1\u09C7\u099F\u09BE\u2026"
title: "\u098F\u0995\u099F\u09BF \u09A8\u09AE\u09C1\u09A8\u09BE \u09AE\u09C7\u09B2\
  \u09C7 \u0985\u0995\u09CD\u09B7\u09B0\u0997\u09C1\u09B2\u09BF \u09AE\u09C1\u099B\
  \u09C7 \u09AB\u09C7\u09B2\u09BE"
---

{{< edit_this_page >}}

## কি এবং কেন?
একটি প্যাটার্নের সাথে মিলে যাওয়া অক্ষরগুলি মুছে ফেলার অর্থ হল একটি স্ট্রিং থেকে নির্দিষ্ট অক্ষরের ক্রম খুঁজে বের করা এবং তা দূর করা। প্রোগ্রামাররা ডেটা পরিষ্কার করার জন্য, অপ্রয়োজনীয় তথ্য বাদ দেওয়ার জন্য অথবা স্ট্রিংগুলিকে একটি প্রয়োজনীয় প্যাটার্নের সাথে মেলে এমন ফরম্যাটে নিয়ে আসার জন্য এটি করে।

## কিভাবে:
Java-তে, আমরা অনেক সময় অক্ষরগুলি মুছে ফেলার জন্য `String.replaceAll()` পদ্ধতি একটি regex প্যাটার্নের সাথে ব্যবহার করি। এখানে একটি দ্রুত উদাহরণ দেওয়া হল:

```Java
public class PatternDeletionExample {
    public static void main(String[] args) {
        String originalString = "Hello, 123 World! This-is a test-string.";
        String pattern = "\\d|-"; // \d একটি সংখ্যা, - একটি আক্ষরিক ড্যাশ

        String cleanedString = originalString.replaceAll(pattern, "");
        System.out.println(cleanedString); // প্রিন্ট করে: Hello,  World! This is a teststring.
    }
}
```
এই কোডটি সংখ্যা এবং ড্যাশ সরিয়ে আমাদের স্ট্রিং পরিষ্কার করে।

## গভীর ডুব
অতীতে, লোকেরা হ্যান্ডি মেথড এবং regex ছাড়াই স্ট্রিং ম্যানিপুলেট করত। তারা এটি করত কঠিন উপায়ে, চর দ্বারা চর, যা একটি ব্যথা ছিল। তারপর নিয়মিত প্রকাশ (regex) আসে, এবং জিনিসগুলি অনেক আসান হয়ে গেল। Regex হল একটি শক্তিশালী প্যাটার্ন মিলানোর মান, যা টেক্সট প্রসেসিং-এ ব্যবহৃত হয়।

তাহলে কেন `replaceAll()`? এটি Java-র `String` ক্লাসের একটি অংশ, এবং যেহেতু স্ট্রিংগুলি সর্বত্র ব্যবহৃত হয়, এটি প্যাটার্ন ভিত্তিক টেক্সট মডিফিকেশনের জন্য যাওয়া-আসার স্থান হয়ে উঠেছে। এটি দুইটি প্যারামিটার নেয়: প্যাটার্ন মুছে ফেলার জন্য regex এবং তার স্থানে যা বসানো হবে—আমাদের ক্ষেত্রে, এটি মুছে ফেলার জন্য একটি খালি স্ট্রিং।

আরও জটিল কাজের জন্য `Pattern` এবং `Matcher` শ্রেণীগুলির মতো বিকল্প রয়েছে। এগুলি আরও নিখুঁত কাজের জন্য কাজে আসে, যেমন মুছে ফেলা ছাড়াই প্যাটার্ন খুঁজে বের করা, অথবা আরও জটিল উপায়ে তাদের প্রতিস্থাপন করা।

বাস্তবায়ন Java regex ইঞ্জিনের উপর নির্ভর করে, যা প্যাটার্নটি বিশ্লেষণ করে এবং লক্ষ্য স্ট্রিং প্রয়োগ করে। এটি অক্ষরগুলির জন্য একটি মিনি অনুসন্ধান-এবং-ধ্বংস মিশন—প্যাটার্নটি খুঁজে বের করুন, তারপর এটি মুছে ফেলুন।

## আরও দেখুন
- Java `Pattern` শ্রেণী: [java.util.regex.Pattern](https://docs.oracle.com/javase/10/docs/api/java/util/regex/Pattern.html)
- Java `Matcher` শ্রেণী: [java.util.regex.Matcher](https://docs.oracle.com/javase/10/docs/api/java/util/regex/Matcher.html)
- Regex টিউটোরিয়াল: [Regular Expressions – User Guide](https://docs.oracle.com/javase/tutorial/essential/regex/)
- `replaceAll()` পদ্ধতি: [java.lang.String#replaceAll](https://docs.oracle.com/en/java/javase/15/docs/api/java.base/java/lang/String.html#replaceAll(java.lang.String,java.lang.String))
