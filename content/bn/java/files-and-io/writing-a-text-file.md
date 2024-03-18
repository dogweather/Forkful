---
title:                "একটি টেক্সট ফাইল লিখা"
date:                  2024-03-17T18:40:01.567648-06:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-17, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## কি এবং কেন?

জাভা ব্যবহার করে টেক্সট ফাইল লিখা মানে ভাষার সামর্থ্য ব্যবহার করে ফাইল সিস্টেমে ফাইল তৈরি এবং তাতে কন্টেন্ট রাইট করা। প্রোগ্রামাররা বিভিন্ন কারণে এটা করে থাকেন, যেমন লগিং, ডেটা এক্সপোর্ট করা, অথবা অ্যাপ্লিকেশনের স্টেট সংরক্ষণ করা পরবর্তী সময় পুনরুদ্ধারের জন্য।

## কিভাবে:

### `java.nio.file` ব্যবহার করে (মানক লাইব্রেরি)

জাভার নিউ আই/ও (NIO) প্যাকেজ (`java.nio.file`) ফাইলের সাথে ডিলিং করার জন্য আরও বহুমুখী পদ্ধতি প্রদান করে। `Files.write()` ব্যবহার করে ফাইলে রাইট করার একটি সরল উপায় নিচে দেওয়া হলঃ

```java
import java.nio.file.Files;
import java.nio.file.Paths;
import java.util.Arrays;
import java.util.List;

public class TextFileWriterNIO {
    public static void main(String[] args) {
        List<String> lines = Arrays.asList("লাইন ১", "লাইন ২", "লাইন ৩");
        try {
            Files.write(Paths.get("example.txt"), lines);
            System.out.println("ফাইল সফলভাবে লিখা হয়েছে!");
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

আউটপুট:

```
ফাইল সফলভাবে লিখা হয়েছে!
```

### `java.io` ব্যবহার করে (মানক লাইব্রেরি)

একটি আরও পরম্পরাগত দৃষ্টিভঙ্গির জন্য, `java.io.FileWriter` টেক্সট ফাইল সহজে লিখার জন্য একটি ভাল বিকল্প:

```java
import java.io.FileWriter;
import java.io.IOException;

public class TextFileWriterIO {
    public static void main(String[] args) {
        try (FileWriter writer = new FileWriter("example.txt")) {
            writer.write("হ্যালো, ওয়ার্ল্ড!\n");
            writer.append("এটি আরেকটি লাইন।");
            System.out.println("ফাইল সফলভাবে লিখা হয়েছে!");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

আউটপুট:

```
ফাইল সফলভাবে লিখা হয়েছে!
```

### অ্যাপাচি কমন্স আইও ব্যবহার করে

অ্যাপাচি কমন্স আইও লাইব্রেরি অনেক অপারেশন, ফাইল রাইটিং সহ সহজ করে দেয়। `FileUtils.writeStringToFile()` ব্যবহার করে ফাইলে লেখার পদ্ধতি নিচে দেওয়া হলঃ:

প্রথমে, আপনার প্রজেক্টে নির্ভরতা যোগ করুন। যদি মেভেন ব্যবহার করেন, যুক্ত করুনঃ

```xml
<dependency>
  <groupId>org.apache.commons</groupId>
  <artifactId>commons-io</artifactId>
  <version>2.11.0</version> <!-- সর্বশেষ ভার্সনের জন্য চেক করুন -->
</dependency>
```

তারপর, নিচের কোড ব্যবহার করে ফাইলে টেক্সট লেখাঃ

```java
import org.apache.commons.io.FileUtils;
import java.io.File;
import java.io.IOException;

public class TextFileWriterCommonsIO {
    public static void main(String[] args) {
        try {
            FileUtils.writeStringToFile(new File("example.txt"), "এটি কমন্স আইও ব্যবহার করে লেখা টেক্সট।", "UTF-8");
            System.out.println("ফাইল সফলভাবে লিখা হয়েছে!");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

আউটপুট:

```
ফাইল সফলভাবে লিখা হয়েছে!
```
