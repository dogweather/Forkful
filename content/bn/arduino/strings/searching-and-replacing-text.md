---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:15:31.337948-06:00
description: "\u099F\u09C7\u0995\u09CD\u09B8\u099F \u0996\u09C1\u0981\u099C\u09C7\
  \ \u09AC\u09C7\u09B0 \u0995\u09B0\u09C7 \u09AA\u09CD\u09B0\u09A4\u09BF\u09B8\u09CD\
  \u09A5\u09BE\u09AA\u09A8 \u0995\u09B0\u09BE \u0986\u09AA\u09A8\u09BE\u0995\u09C7\
  \ \u0995\u09CB\u09A8\u09CB \u099F\u09C7\u0995\u09CD\u09B8\u099F\u09C7\u09B0 \u09A8\
  \u09BF\u09B0\u09CD\u09A6\u09BF\u09B7\u09CD\u099F \u0985\u0995\u09CD\u09B7\u09B0\
  \ \u09AC\u09BE \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982\u0997\u09C1\u09B2\u09BF\
  \ \u0996\u09C1\u0981\u099C\u09C7 \u09AC\u09C7\u09B0 \u0995\u09B0\u09C7 \u09A4\u09BE\
  \ \u0985\u09A8\u09CD\u09AF \u0995\u09BF\u099B\u09C1\u09B0 \u09B8\u09BE\u09A5\u09C7\
  \ \u09AA\u09CD\u09B0\u09A4\u09BF\u09B8\u09CD\u09A5\u09BE\u09AA\u09A8 \u0995\u09B0\
  \u09A4\u09C7 \u09B8\u09BE\u09B9\u09BE\u09AF\u09CD\u09AF \u0995\u09B0\u09C7\u0964\
  \u2026"
lastmod: '2024-03-17T18:47:44.307149-06:00'
model: gpt-4-0125-preview
summary: "\u099F\u09C7\u0995\u09CD\u09B8\u099F \u0996\u09C1\u0981\u099C\u09C7 \u09AC\
  \u09C7\u09B0 \u0995\u09B0\u09C7 \u09AA\u09CD\u09B0\u09A4\u09BF\u09B8\u09CD\u09A5\
  \u09BE\u09AA\u09A8 \u0995\u09B0\u09BE \u0986\u09AA\u09A8\u09BE\u0995\u09C7 \u0995\
  \u09CB\u09A8\u09CB \u099F\u09C7\u0995\u09CD\u09B8\u099F\u09C7\u09B0 \u09A8\u09BF\
  \u09B0\u09CD\u09A6\u09BF\u09B7\u09CD\u099F \u0985\u0995\u09CD\u09B7\u09B0 \u09AC\
  \u09BE \u09B8\u09CD\u099F\u09CD\u09B0\u09BF\u0982\u0997\u09C1\u09B2\u09BF \u0996\
  \u09C1\u0981\u099C\u09C7 \u09AC\u09C7\u09B0 \u0995\u09B0\u09C7 \u09A4\u09BE \u0985\
  \u09A8\u09CD\u09AF \u0995\u09BF\u099B\u09C1\u09B0 \u09B8\u09BE\u09A5\u09C7 \u09AA\
  \u09CD\u09B0\u09A4\u09BF\u09B8\u09CD\u09A5\u09BE\u09AA\u09A8 \u0995\u09B0\u09A4\u09C7\
  \ \u09B8\u09BE\u09B9\u09BE\u09AF\u09CD\u09AF \u0995\u09B0\u09C7\u0964\u2026"
title: "\u099F\u09C7\u0995\u09CD\u09B8\u099F \u0985\u09A8\u09C1\u09B8\u09A8\u09CD\u09A7\
  \u09BE\u09A8 \u098F\u09AC\u0982 \u09AA\u09CD\u09B0\u09A4\u09BF\u09B8\u09CD\u09A5\
  \u09BE\u09AA\u09A8"
---

{{< edit_this_page >}}

## কি এবং কেন?

টেক্সট খুঁজে বের করে প্রতিস্থাপন করা আপনাকে কোনো টেক্সটের নির্দিষ্ট অক্ষর বা স্ট্রিংগুলি খুঁজে বের করে তা অন্য কিছুর সাথে প্রতিস্থাপন করতে সাহায্য করে। প্রোগ্রামাররা কোড, ডেটা অথবা ব্যবহারকারীর ইনপুট ঝামেলা ছাড়াই পরিবর্তন করার জন্য এটি করে থাকেন।

## কিভাবে:

Arduino উচ্চ-স্তরের ভাষায় যেভাবে স্ট্রিং অনুসন্ধান এবং প্রতিস্থাপনের সাপোর্ট করে তেমন একদম নেটিভ সাপোর্ট করে না। তবে, আপনি চারিত্রিক অ্যারে নিয়ে কাজ করতে পারেন অথবা `String` ক্লাস ব্যবহার করতে পারেন যা `replace()` মেথড অফার করে। প্রথম পদ্ধতি মেমোরি-দক্ষ, অন্যদিকে দ্বিতীয় পদ্ধতি আরও সোজাসাপ্টা। আসুন স্পষ্টতার জন্য `String` ক্লাস-এর উপর ফোকাস করি।

```Arduino
void setup() {
  Serial.begin(9600);
  String text = "I like apples and apples are great!";
  text.replace("apples", "oranges");
  Serial.println(text);
}

void loop() {
  // এখানে কিছু করার নেই।
}
```

নমুনা আউটপুট:
```
I like oranges and oranges are great!
```

## গভীরে যান

অতীতে, মাইক্রোকন্ট্রোলারে স্ট্রিং ম্যানিপুলেশন কাজ বিরল ছিল — মেমোরি সীমিত ছিল, এবং অ্যাপ্লিকেশনগুলি সরল ছিল। এই দিনগুলিতে, আরও জটিল প্রকল্প এবং মাইক্রোকন্ট্রোলার প্রযুক্তিতে অগ্রগতির দরুন প্রচুর মেমোরি স্পেসের সাথে, এমন ইউটিলিটি গুলো খুব সাধারণ।

যদি আপনি এর ডাইনামিক মেমোরি ব্যবহারের কারণে `String` ক্লাস ব্যবহার করতে না চান, যা ফ্রাগমেন্টেশনের কারণ হতে পারে, তাহলে আপনি এখনও C-স্টাইল স্ট্রিংসে (null-terminated চারিত্রিক অ্যারে) `strchr()`, `strstr()` ফাংশন এবং ম্যানুয়াল কপি বা লুপ দিয়ে প্রতিস্থাপন ব্যবহার করে খুঁজে বের করতে এবং প্রতিস্থাপন করতে পারেন। এটি আরও জড়িত কিন্তু মেমোরির উপর আপনাকে বেশি নিয়ন্ত্রণ দেয়।

উদাহরণস্বরূপ, একটি উপস্থাপনা স্ট্রিং প্রতিস্থাপনের একটি বিকল্প উপায় এরকম দেখতে পারে:

```Arduino
void replaceSubstring(char *input, const char *search, const char *replace) {
  char buffer[100];
  char *p;

  // 'strstr' চেক করে এটি 'search' কে 'input' এর অংশ হিসেবে আছে কিনা।
  if (!(p = strstr(input, search))) return;

  // 'search' খোঁজা পর্যন্ত অংশটি কপি করুন।
  strncpy(buffer, input, p - input);
  buffer[p - input] = '\0';

  // 'replace' এবং বাকি 'input' যুক্ত করুন 'search' এর পর থেকে।
  sprintf(buffer+(p - input), "%s%s", replace, p + strlen(search));

  // ফলাফল আউটপুট করুন
  strcpy(input, buffer);
}

void setup() {
  Serial.begin(9600);
  char text[] = "I like apples and apples are great!";
  replaceSubstring(text, "apples", "oranges");
  Serial.println(text);
}

void loop() {
  // এখানেও কিছু করার নেই।
}
```

নমুনা আউটপুট:
```
I like oranges and oranges are great!
```

## আরও দেখুন

- [Arduino রেফারেন্স: স্ট্রিং অবজেক্ট](https://www.arduino.cc/reference/en/language/variables/data-types/stringobject/)
- [Arduino রেফারেন্স: স্ট্রিং প্রতিস্থাপন ফাংশন](https://www.arduino.cc/reference/en/language/variables/data-types/string/functions/replace/)
- [Cplusplus.com: C স্ট্রিং ফাংশনস](http://www.cplusplus.com/reference/cstring/)
