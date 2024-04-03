---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:20:47.781022-06:00
description: "\u098F\u0995\u099F\u09BF \u09A8\u09A4\u09C1\u09A8 \u099C\u09BE\u09AD\
  \u09BE \u09AA\u09CD\u09B0\u099C\u09C7\u0995\u09CD\u099F \u09B6\u09C1\u09B0\u09C1\
  \ \u0995\u09B0\u09BE \u09AF\u09C7\u09A8 \u0986\u09AA\u09A8\u09BE\u09B0 \u09AE\u09BE\
  \u09B8\u09CD\u099F\u09BE\u09B0\u09AA\u09BF\u09B8\u09C7\u09B0 \u099C\u09A8\u09CD\u09AF\
  \ \u098F\u0995\u099F\u09BF \u09A8\u09A4\u09C1\u09A8 \u0995\u09CD\u09AF\u09BE\u09A8\
  \u09AD\u09BE\u09B8 \u09A4\u09C8\u09B0\u09BF \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\
  \u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u09A8\u09A4\u09C1\
  \u09A8 \u09AA\u09CD\u09B0\u099C\u09C7\u0995\u09CD\u099F \u09B6\u09C1\u09B0\u09C1\
  \ \u0995\u09B0\u09C7 \u09A7\u09BE\u09B0\u09A3\u09BE\u0995\u09C7 \u0995\u09BE\u09B0\
  \u09CD\u09AF\u0995\u09B0\u09C0\u2026"
lastmod: '2024-03-17T18:47:43.905068-06:00'
model: gpt-4-0125-preview
summary: "\u098F\u0995\u099F\u09BF \u09A8\u09A4\u09C1\u09A8 \u099C\u09BE\u09AD\u09BE\
  \ \u09AA\u09CD\u09B0\u099C\u09C7\u0995\u09CD\u099F \u09B6\u09C1\u09B0\u09C1 \u0995\
  \u09B0\u09BE \u09AF\u09C7\u09A8 \u0986\u09AA\u09A8\u09BE\u09B0 \u09AE\u09BE\u09B8\
  \u09CD\u099F\u09BE\u09B0\u09AA\u09BF\u09B8\u09C7\u09B0 \u099C\u09A8\u09CD\u09AF\
  \ \u098F\u0995\u099F\u09BF \u09A8\u09A4\u09C1\u09A8 \u0995\u09CD\u09AF\u09BE\u09A8\
  \u09AD\u09BE\u09B8 \u09A4\u09C8\u09B0\u09BF \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\
  \u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u09A8\u09A4\u09C1\
  \u09A8 \u09AA\u09CD\u09B0\u099C\u09C7\u0995\u09CD\u099F \u09B6\u09C1\u09B0\u09C1\
  \ \u0995\u09B0\u09C7 \u09A7\u09BE\u09B0\u09A3\u09BE\u0995\u09C7 \u0995\u09BE\u09B0\
  \u09CD\u09AF\u0995\u09B0\u09C0 \u09B8\u09AB\u099F\u0993\u09AF\u09BC\u09CD\u09AF\u09BE\
  \u09B0\u09C7 \u09AA\u09B0\u09BF\u09A3\u09A4 \u0995\u09B0\u09BE\u09B0 \u099C\u09A8\
  \u09CD\u09AF, \u098F\u09AC\u0982 \u09AA\u09CD\u09B0\u09A4\u09BF\u099F\u09BF \u09A8\
  \u09A4\u09C1\u09A8 \u09B6\u09C1\u09B0\u09C1 \u09B9\u09B2 \u0989\u09A6\u09CD\u09AD\
  \u09BE\u09AC\u09A8 \u0985\u09A5\u09AC\u09BE \u09B8\u09AE\u09BE\u09A7\u09BE\u09A8\
  \u09C7\u09B0 \u09A6\u09BF\u0995\u09C7 \u098F\u0995 \u09A7\u09BE\u09AA\u0964."
title: "\u09A8\u09A4\u09C1\u09A8 \u09AA\u09CD\u09B0\u0995\u09B2\u09CD\u09AA \u09B6\
  \u09C1\u09B0\u09C1 \u0995\u09B0\u09BE"
weight: 1
---

## কিভাবে:
চলুন এটা শুরু করি। আমরা কমান্ড লাইন ব্যবহার করে একটি সাধারণ জাভা প্রজেক্ট তৈরি করব এবং একটি ক্লাসিক "হ্যালো, ওয়ার্ল্ড!" প্রোগ্রাম কম্পাইল এবং চালাব৤

প্রথমে, আপনার প্রজেক্টের জন্য একটি ডিরেক্টরি তৈরি করুন এবং তাতে নেভিগেট করুন:

```bash
mkdir MyJavaProject
cd MyJavaProject
```

এখন, আপনার জাভা ফাইলটি তৈরি করুন:

```bash
echo 'public class HelloWorld { public static void main(String[] args) { System.out.println("Hello, World!"); }}' > HelloWorld.java
```

কম্পাইলের সময়:

```bash
javac HelloWorld.java
```

আপনার মাস্টারপিসে পরিচালনা করুন:

```bash
java HelloWorld
```

দেখুন! কনসোলে আউটপুট দেখা যাবে:

```java
Hello, World!
```

## গভীর ডুব:
একসময়, জাভা প্রজেক্টগুলি হাতে হাতে পরিচালিত হতো, যা একটি সার্কাসে ফাইল জাগলিং এর মতো। আজকাল, আমাদের কাছে Maven এবং Gradle এর মতো টুলস আছে যা এই দৈনন্দিন কাজগুলি স্বয়ংক্রিয় করে দেয়।

উদাহরণ স্বরূপ, Maven আজকের অধিকাংশ জাভা ডেভেলপাররা যা পরিচিত সেই মান প্রজেক্ট লেআউট নির্ধারণ করেছে। এটি নির্ভরশীলতাগুলিও সামলায় যাতে আপনাকে ম্যানুয়ালি জার ডাউনলোড করতে হয় না এবং ক্লাসপাথ দুঃস্বপ্নের সাথে লড়াই করতে হয় না।

Gradle পরে দৃশ্যে আসে, আরো নমনীয়তা প্রস্তাব করে এবং স্ক্রিপ্টিং এর জন্য একটি Groovy-ভিত্তিক DSL (ডোমেইন স্পেসিফিক ভাষা) ব্যবহার করে। এটি Maven এর মতো, কিন্তু অতিরিক্ত প্লাগিনস ছাড়া কাস্টম স্ক্রিপ্টের জন্য আরও স্বাধীনতা দেয়।

বিকল্প? অবশ্যই, আছে Ant সহ Ivy, কিন্তু এটি একটু পুরনো স্কুলের, যেন ক্যাসেট টেপে গান শোনা। আপনাকে নস্টালজিয়া পছন্দ করতে হবে, কিন্তু স্ট্রিমিং সার্ভিসের এই যুগে এটি সবার জন্য নাও হতে পারে।

যখন আপনি একটি নতুন জাভা প্রজেক্ট শুরু করেন, চিন্তা করুন এটি কত বড় এবং জটিল হবে। শেখার জন্য অথবা ছোট প্রজেক্টের জন্য, ম্যানুয়াল ব্যবস্থাপনা ঠিক আছে। কিন্তু, আপনি যদি কিছু গুরুত্বপূর্ণ তৈরি করার পরিকল্পনা করেন অথবা একটি দলে কাজ করেন, তাহলে একটি বিল্ড টুল হল যেতে হবে পথ।

## দেখুন এছাড়াও:
বিল্ড টুলস ব্যবহার করে এগিয়ে যাওয়ার জন্য, নিম্নলিখিত দেখুন:

- [Maven শুরু করার গাইড](https://maven.apache.org/guides/getting-started/index.html)
- [Gradle দিয়ে জাভা প্রজেক্টস বিল্ড করা](https://spring.io/guides/gs/gradle/)
- [Ant এর পরিচিতি](https://ant.apache.org/manual/index.html)

এবং যারা JDK এর নতুন ফিচারগুলিতে গভীর ডুব দিতে চান, [Java Platform, Standard Edition Oracle Documentation](https://docs.oracle.com/en/java/javase/index.html) হল একটি গুপ্তধন।
