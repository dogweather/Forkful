---
title:                "স্ট্রিং জোড়া দেওয়া"
date:                  2024-03-17T17:46:29.296843-06:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-17, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## কি এবং কেন?
স্ট্রিং জোড়া দেওয়া মানে আলাদা আলাদা স্ট্রিং গুলিকে একসাথে আঠালো করে একটি নতুন স্ট্রিং তৈরি করা। প্রোগ্রামাররা এটি টেক্সট গতিশীলভাবে সমন্বয় করার জন্য করে থাকেন, যেমন অভিবাদন, বার্তা সংযুক্ত করা বা কেবল ডাটাকে পঠনযোগ্য ফর্ম্যাটে সাজানোর জন্য।

## কিভাবে:
```Swift
let firstName = "Taylor"
let lastName = "Swift"
let fullName = firstName + " " + lastName  // + অপারেটর ব্যবহার করে
print(fullName)  // আউটপুট: "Taylor Swift"

let age = 31
let greeting = "Hello, \(firstName)! You're \(age) years old."  // স্ট্রিং ইন্টারপোলেশন ব্যবহার করে
print(greeting)  // আউটপুট: "Hello, Taylor! You're 31 years old."

var message = "This"
message += " is" // += অপারেটর ব্যবহার করে স্ট্রিংয়ে যোগ করা হচ্ছে
message += " Sparta!"
print(message)  // আউটপুট: "This is Sparta!"
```

## গভীর ডুব
অনেক আগে, C মতো প্রোগ্রামিং ভাষার লোকেরা ফাংশনের মাধ্যমে স্ট্রিং নিয়ে ম্যানুয়ালি কাজ করতো, এরি অ্যারে এবং নাল-টার্মিনেটেড স্ট্রিং নিয়ে ব্যবস্থা করতে হত। Swift এটি সহজ করে দিয়েছে। স্ট্রিংয়ের জন্য '+' অপারেটর Java এবং C++ মতো ভাষাগুলি থেকে এসেছে, যা স্ট্রিংগুলি একসাথে লাগানোর পরিচিত উপায় সরবরাহ করে।

'+' ছাড়াও আরও অপশন রয়েছে। Swift-এ স্ট্রিং ইন্টারপোলেশন শুধুমাত্র ঝলমলে হওয়ার চেয়ে বেশি - এটি আপনার স্ট্রিংয়ের মধ্যে সরাসরি মান এম্বেড করার একটি টাইপ-নিরাপদ উপায়। টাইপগুলি কাস্ট করার বা কিছু মিলানোর চিন্তা না করে চলতে পারেন।

উন্নত সংযোজন কেবল শব্দ ছুড়ে দেওয়ার চেয়ে বেশি। যখন পারফরমেন্স প্রধান বিষয়, '+=' অসাবধানভাবে ব্যবহার করা আপনাকে ধীর করে দিতে পারে। কেন? কারণ যদি আপনি লুপে একটি স্ট্রিংয়ে যোগ করছেন, Swift প্রতিবারে নতুন স্ট্রিং তৈরি করতে পারে, যা খুব তাড়াতাড়ি নয়। পরিবর্তে, বড় ডাটা বা জটিল লুপের সাথে বিশেষ করে দক্ষতার জন্য 'join()' বা 'String'-এর 'append()' ব্যবহার করা বিবেচনা করুন।

```Swift
// `join()` এর মাধ্যমে দক্ষ সংযোজন
let words = ["Once", "upon", "a", "time"]
let story = words.joined(separator: " ")  // অ্যারে এলিমেন্টস যোগ করার জন্য দক্ষ
print(story)  // আউটপুট: "Once upon a time"

// উপ-স্ট্রিং যোগ করার জন্য 'append(contentsOf:)' ব্যবহার
var quote = "I think, "
quote.append(contentsOf: "therefore I am")
print(quote)  // আউটপুট: "I think, therefore I am"
```

## আরও দেখুন
- স্ট্রিংস সম্পর্কে Swift ডকুমেন্টেশন: [Swift.org ডকুমেন্টেশন](https://docs.swift.org/swift-book/LanguageGuide/StringsAndCharacters.html)
- Apple-এর স্ট্রিং প্রোগ্রামিং গাইড: [Apple ডেভেলপার ডকুমেন্টেশন](https://developer.apple.com/documentation/swift/string)
