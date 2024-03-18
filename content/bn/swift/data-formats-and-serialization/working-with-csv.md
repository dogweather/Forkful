---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:28:54.591755-06:00
description: "CSV (Comma-Separated Values) \u09AB\u09BE\u0987\u09B2\u09C7\u09B0 \u09B8\
  \u09BE\u09A5\u09C7 \u0995\u09BE\u099C \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\u09C7\
  \ \u09AA\u09BE\u09A0\u09CD\u09AF \u09AB\u09BE\u0987\u09B2 \u09A5\u09C7\u0995\u09C7\
  \ \u0997\u09A0\u09BF\u09A4 \u09A4\u09A5\u09CD\u09AF \u09AA\u09BE\u09B0\u09CD\u09B8\
  \ \u098F\u09AC\u0982 \u099C\u09C7\u09A8\u09BE\u09B0\u09C7\u099F \u0995\u09B0\u09BE\
  \ \u09AF\u09C7\u0996\u09BE\u09A8\u09C7 \u09AA\u09CD\u09B0\u09A4\u09BF \u09B2\u09BE\
  \u0987\u09A8 \u098F\u0995\u099F\u09BF \u09B0\u09C7\u0995\u09B0\u09CD\u09A1 \u09AA\
  \u09CD\u09B0\u09A4\u09BF\u09A8\u09BF\u09A7\u09BF\u09A4\u09CD\u09AC \u0995\u09B0\u09C7\
  \ \u098F\u09AC\u0982\u2026"
lastmod: '2024-03-17T18:47:44.432374-06:00'
model: gpt-4-0125-preview
summary: "CSV (Comma-Separated Values) \u09AB\u09BE\u0987\u09B2\u09C7\u09B0 \u09B8\
  \u09BE\u09A5\u09C7 \u0995\u09BE\u099C \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\u09C7\
  \ \u09AA\u09BE\u09A0\u09CD\u09AF \u09AB\u09BE\u0987\u09B2 \u09A5\u09C7\u0995\u09C7\
  \ \u0997\u09A0\u09BF\u09A4 \u09A4\u09A5\u09CD\u09AF \u09AA\u09BE\u09B0\u09CD\u09B8\
  \ \u098F\u09AC\u0982 \u099C\u09C7\u09A8\u09BE\u09B0\u09C7\u099F \u0995\u09B0\u09BE\
  \ \u09AF\u09C7\u0996\u09BE\u09A8\u09C7 \u09AA\u09CD\u09B0\u09A4\u09BF \u09B2\u09BE\
  \u0987\u09A8 \u098F\u0995\u099F\u09BF \u09B0\u09C7\u0995\u09B0\u09CD\u09A1 \u09AA\
  \u09CD\u09B0\u09A4\u09BF\u09A8\u09BF\u09A7\u09BF\u09A4\u09CD\u09AC \u0995\u09B0\u09C7\
  \ \u098F\u09AC\u0982\u2026"
title: "CSV \u098F\u09B0 \u09B8\u09BE\u09A5\u09C7 \u0995\u09BE\u099C \u0995\u09B0\u09BE"
---

{{< edit_this_page >}}

## কি এবং কেন?

CSV (Comma-Separated Values) ফাইলের সাথে কাজ করা মানে পাঠ্য ফাইল থেকে গঠিত তথ্য পার্স এবং জেনারেট করা যেখানে প্রতি লাইন একটি রেকর্ড প্রতিনিধিত্ব করে এবং প্রতিটি রেকর্ড কমা দ্বারা পৃথকীকৃত ক্ষেত্রগুলি থেকে গঠিত। প্রোগ্রামাররা প্রায়ই এই কার্যক্রমে যুক্ত থাকে টেবিলার ডাটা সহজেই ইম্পোর্ট, এক্সপোর্ট এবং ম্যানিপুলেট করার জন্য বিভিন্ন প্ল্যাটফর্ম এবং প্রোগ্রামিং ভাষাগুলি জুড়ে ব্যাপকভাবে সমর্থিত একটি ফরম্যাট ব্যবহার করতে, এর সাদাসিধা এবং মানুষের পড়ার যোগ্য ফরম্যাটের কারণে।

## কিভাবে:

সুইফটে, CSV ফাইলগুলি সরাসরি পার্স করার জন্য কোনো নেটিভ সমর্থন নেই, তবে আপনি সমস্যাটি সুইফটের `String` পদ্ধতিগুলি ব্যবহার করে বিষয়বস্তুগুলি বিভাজন করে, অথবা SwiftCSV এর মতো তৃতীয়-পক্ষের লাইব্রেরিগুলি কাজে লাগিয়ে আরও সুষ্ঠু পথে CSV ডেটা পরিচালনা করতে পারেন। এখানে উভয় পদ্ধতির বিবরণ দেওয়া হল:

### বাহ্যিক লাইব্রেরি ছাড়াই ম্যানুয়াল পার্সিং
```swift
// একটি সহজ CSV স্ট্রিং বিবেচনা করুন
let csvString = """
name,age,city
John Doe,29,New York
Jane Smith,34,Los Angeles
"""

// CSV স্ট্রিংটি লাইনে লাইনে বিভাজন
let rows = csvString.components(separatedBy: "\n")

// প্রথম সারি থেকে চাবিগুলি প্রত্যাহার
let keys = rows.first?.components(separatedBy: ",")

// দ্বিতীয় থেকে সারিগুলির উপর পুনরাবৃত্তি
var result: [[String: String]] = []
for row in rows.dropFirst() {
    let values = row.components(separatedBy: ",")
    let dict = Dictionary(uniqueKeysWithValues: zip(keys!, values))
    result.append(dict)
}

// নমুনা আউটপুট
print(result)
// আউটপুট: [{"city": "New York", "age": "29", "name": "John Doe"}, {"city": "Los Angeles", "age": "34", "name": "Jane Smith"}]
```
এই পদ্ধতিটি সরাসরি কিন্তু বিশেষ ক্ষেত্রের মতো মানগুলির মধ্যে কমাসহ CSV ফাইলগুলি নিয়ে কাজ করার সময় দৃঢ়তা অভাব রয়েছে, ক্ষেত্রের মধ্যে লাইন ব্রেক ইত্যাদি।

### SwiftCSV লাইব্রেরি ব্যবহার
প্রথমে, আপনার `Package.swift` নির্ভরতাগুলিতে SwiftCSV যোগ করে আপনার প্রোজেক্টে এটি যোগ করুন:
```swift
.package(url: "https://github.com/swiftcsv/SwiftCSV.git", from: "0.5.6")
```
তারপর, নিম্নলিখিত হিসেবে এর আমদানি এবং ব্যবহার করুন:
```swift
import SwiftCSV

// ধরে নেওয়া যাক `csvString` উপরের মতোই সংজ্ঞায়িত

// একটি CSV অবজেক্ট তৈরি করুন
if let csv = try? CSV(string: csvString) {
    // অভিধান হিসেবে সারিগুলি অ্যাক্সেস করুন
    let rows = csv.namedRows
    
    // নমুনা আউটপুট
    print(rows)
    // আউটপুট: [{"city": "New York", "age": "29", "name": "John Doe"}, {"city": "Los Angeles", "age": "34", "name": "Jane Smith"}]
}
```
SwiftCSV কমা দ্বারা ঘেরা, ক্ষেত্রের মধ্যে লাইন ব্রেক, এবং চরিত্র এনকোডিং এর মতো জটিলতাগুলি স্বয়ংক্রিয়ভাবে সম্পর্কের মাধ্যমে পার্সিং সহজ করে। তবে, বাহ্যিক ডেটা উৎসগুলির সাথে কাজ করার সময় বাস্তব অনুপ্রয়োগে সম্ভাব্য ত্রুটিগুলি পরিচালনা করা নিশ্চিত করা উচিত, বিশেষত যখন।
