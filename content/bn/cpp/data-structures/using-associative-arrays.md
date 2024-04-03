---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:25:00.346174-06:00
description: "\u0985\u09CD\u09AF\u09BE\u09B8\u09CB\u09B8\u09BF\u09AF\u09BC\u09C7\u099F\
  \u09BF\u09AD \u0985\u09CD\u09AF\u09BE\u09B0\u09C7, \u09AF\u09BE C++ \u098F `std::map`\
  \ \u09AC\u09BE `std::unordered_map` \u09B9\u09BF\u09B8\u09C7\u09AC\u09C7 \u09AA\u09B0\
  \u09BF\u099A\u09BF\u09A4, \u0985\u09CD\u09AF\u09BE\u09B0\u09C7 \u0987\u09A8\u09CD\
  \u09A1\u09C7\u0995\u09CD\u09B8 \u098F\u09AC\u0982 \u09AC\u09BE\u09B8\u09CD\u09A4\
  \u09AC \u09AC\u09BF\u09B6\u09CD\u09AC\u09C7\u09B0 \u09A1\u09C7\u099F\u09BE\u09B0\
  \ \u09AE\u09A7\u09CD\u09AF\u09C7 \u098F\u0995\u099F\u09BF \u09B8\u09C7\u09A4\u09C1\
  \ \u09A4\u09C8\u09B0\u09BF \u0995\u09B0\u09C7,\u2026"
lastmod: '2024-03-17T18:47:44.357910-06:00'
model: gpt-4-0125-preview
summary: "\u0985\u09CD\u09AF\u09BE\u09B8\u09CB\u09B8\u09BF\u09AF\u09BC\u09C7\u099F\
  \u09BF\u09AD \u0985\u09CD\u09AF\u09BE\u09B0\u09C7, \u09AF\u09BE C++ \u098F `std::map`\
  \ \u09AC\u09BE `std::unordered_map` \u09B9\u09BF\u09B8\u09C7\u09AC\u09C7 \u09AA\u09B0\
  \u09BF\u099A\u09BF\u09A4, \u0985\u09CD\u09AF\u09BE\u09B0\u09C7 \u0987\u09A8\u09CD\
  \u09A1\u09C7\u0995\u09CD\u09B8 \u098F\u09AC\u0982 \u09AC\u09BE\u09B8\u09CD\u09A4\
  \u09AC \u09AC\u09BF\u09B6\u09CD\u09AC\u09C7\u09B0 \u09A1\u09C7\u099F\u09BE\u09B0\
  \ \u09AE\u09A7\u09CD\u09AF\u09C7 \u098F\u0995\u099F\u09BF \u09B8\u09C7\u09A4\u09C1\
  \ \u09A4\u09C8\u09B0\u09BF \u0995\u09B0\u09C7, \u0986\u09AA\u09A8\u09BE\u0995\u09C7\
  \ \u0985\u09B0\u09CD\u09A5\u09AA\u09C2\u09B0\u09CD\u09A3 \u0995\u09C0 \u09AC\u09CD\
  \u09AF\u09AC\u09B9\u09BE\u09B0 \u0995\u09B0\u09A4\u09C7 \u09A6\u09C7\u09AF\u09BC\
  \u0964 \u0987\u09A8\u09CD\u09A1\u09C7\u0995\u09CD\u09B8 \u09AA\u099C\u09BF\u09B6\
  \u09A8\u09C7\u09B0 \u09AA\u09B0\u09BF\u09AC\u09B0\u09CD\u09A4\u09C7 \u0995\u09C0\
  \ \u09AC\u09CD\u09AF\u09AC\u09B9\u09BE\u09B0 \u0995\u09B0\u09C7 \u09A6\u09CD\u09B0\
  \u09C1\u09A4 \u09B2\u09C1\u0995\u0986\u09AA, \u0987\u09A8\u09B8\u09BE\u09B0\u09CD\
  \u099F \u098F\u09AC\u0982 \u09A1\u09BF\u09B2\u09BF\u099F \u0995\u09B0\u09BE\u09B0\
  \ \u09AA\u09CD\u09B0\u09AF\u09BC\u09CB\u099C\u09A8\u09C7 \u098F\u09A6\u09C7\u09B0\
  \ \u0989\u09AA\u09B0 \u09A8\u09BF\u09B0\u09CD\u09AD\u09B0 \u0995\u09B0\u09BE \u09B9\
  \u09AF\u09BC\u0964."
title: "\u098F\u09B8\u09CB\u09B8\u09BF\u09AF\u09BC\u09C7\u099F\u09BF\u09AD \u0985\u09CD\
  \u09AF\u09BE\u09B0\u09C7\u09B0 \u09AC\u09CD\u09AF\u09AC\u09B9\u09BE\u09B0"
weight: 15
---

## কিভাবে:
C++ এ, অ্যাসোসিয়েটিভ অ্যারে `<map>` এবং `<unordered_map>` হেডারগুলির মাধ্যমে জীবন পায়। উভয়ের ব্যবহার দেখতে আসুন উদাহরণের মাধ্যমে দেখি।

### `std::map` ব্যবহার করে
`std::map` কী এর উপর ভিত্তি করে উপাদানগুলিকে সাজানো রাখে। শুরু করার জন্য এখানে কিভাবে:

```C++
#include <iostream>
#include <map>
#include <string>

int main() {
    std::map<std::string, int> ageMap;
    
    // মানগুলি ইনসার্ট করা
    ageMap["Alice"] = 30;
    ageMap["Bob"] = 25;
    
    // মানগুলি এক্সেস করা
    std::cout << "ববের বয়স: " << ageMap["Bob"] << std::endl;
    
    // একটি ম্যাপের উপর ইটারেট করা
    for(const auto &pair : ageMap) {
        std::cout << pair.first << " এর বয়স " << pair.second << " বছর।" << std::endl;
    }
    
    return 0;
}
```

### `std::unordered_map` ব্যবহার করে
যখন অর্ডারের প্রয়োজন না থাকে, কিন্তু পারফরম্যান্সের প্রয়োজন থাকে, `std::unordered_map` আপনার বন্ধু, যা গড় জটিলতায় দ্রুত ইনসার্ট, লুকআপ এবং ডিলিট অর্ফার করে।

```C++
#include <iostream>
#include <unordered_map>
#include <string>

int main() {
    std::unordered_map<std::string, double> productPrice;
    
    // মানগুলি ইনসার্ট করা
    productPrice["dudh"] = 2.99;
    productPrice["roti"] = 1.99;
    
    // মানগুলি এক্সেস করা
    std::cout << "Dudher daam: $" << productPrice["dudh"] << std::endl;
    
    // একটি unordered_map এর উপর ইটারেট করা
    for(const auto &pair : productPrice) {
        std::cout << pair.first << " er daam $" << pair.second << std::endl;
    }
    
    return 0;
}
```

## গভীরে ডুব:
C++ এর অ্যাসোসিয়েটিভ অ্যারে, বিশেষ করে `std::map` এবং `std::unordered_map`, কেবল উপাদান সংরক্ষণ করা নয়, এরা অনুসন্ধান, ইনসার্ট, এবং মুছে ফেলার মতো অপারেশনগুলি কার্যকর সময় জটিলতায় সম্ভব করে তোলে (`std::map` এর জন্য লগারিদমিক এবং `std::unordered_map` এর জন্য গড় কেসে স্থায়ী সময়)। এই দক্ষতা আসে অধীনস্থ ডেটা কাঠামো থেকে: `std::map` এর জন্য একটি সমতল বৃক্ষ এবং `std::unordered_map` এর জন্য একটি হ্যাশ টেবিল।

ঐতিহাসিকভাবে, এইগুলি মানক লাইব্রেরির অংশ না হওয়ার আগে, প্রোগ্রামারদের নিজেদের সংস্করণ তৈরি করতে হত বা তৃতীয়-পক্ষের লাইব্রেরিগুলি ব্যবহার করতে হত, যা অসামঞ্জস্য এবং সম্ভাব্য অকার্যকরিতার জন্য পথ তৈরি করত। C++ এর মানক লাইব্রেরিতে ম্যাপগুলির অন্তর্ভুক্তি শুধুমাত্র তাদের ব্যবহারকে মানদণ্ডবদ্ধ করেনি, বিভিন্ন কম্পাইলার এবং প্ল্যাটফর্মে তাদের পারফরম্যান্সকে অনুকূলিত করেছে।

যদিও উভয়ই শক্তিশালী, একটি `std::map` এবং `std::unordered_map` এর মধ্যে নির্বাচন আপনার ব্যবহারের বিশেষ উপর নির্ভর করে। আপনার যদি অর্ডারযুক্ত ডেটা প্রয়োজন হয় এবং সামান্য পারফরম্যান্স ট্রেড-অফের সাথে সমস্যা না থাকে, তবে `std::map` এর সাথে যান। যদি আপনার দ্রুততা প্রয়োজন হয় এবং অর্ডার সম্পর্কে আপনার কোনও যত্ন না থাকে, তবে `std::unordered_map` আপনার জন্য ভাল বিকল্প হতে পারে।

তবে, এটা মনে রাখা জরুরি যে জটিল ডেটা কাঠামোর সাথে কাজ করার সময়, সর্বদা ট্রেড-অফ থাকে। কিছু নির্দিষ্ট ক্ষেত্রে, অন্যান্য ডেটা কাঠামো বা এমনকি তৃতীয়-পক্ষের লাইব্রেরিগুলি আপনার বিশেষ চাহিদার জন্য আরও ভাল পারফরম্যান্স বা ফাংশনালিটি অর্ফার করতে পারে। আপনার প্রকল্পের প্রয়োজনীয়তার ভিত্তিতে সর্বদা আপনার বিকল্পগুলি বিবেচনা করুন।
