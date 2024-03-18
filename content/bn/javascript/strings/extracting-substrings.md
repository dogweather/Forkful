---
title:                "সাবস্ট্রিং বের করা"
date:                  2024-03-17T17:47:51.151583-06:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-17, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## কি এবং কেন?
উপস্ত্রিং বের করা মানে একটি স্ট্রিংয়ের একাংশ গ্রহণ করা। প্রোগ্রামাররা ডাটা আলাদা করা, কিছু ফর্ম্যাট ইনপুট করা অথবা টেক্সট আউটপুটের জন্য পরিবর্তন করার লক্ষ্যে স্ট্রিংগুলি কেটে নেয়।

## কিভাবে:

### `substring` মেথড ব্যবহার করে:
```javascript
let text = "JavaScript is awesome!";
let extracted = text.substring(0, 10);
console.log(extracted); // আউটপুট: JavaScript
```

### `slice` মেথড ব্যবহার করে:
```javascript
let text = "JavaScript is awesome!";
let sliced = text.slice(-9, -1);
console.log(sliced); // আউটপুট: awesome
```

### `substr` মেথড ব্যবহার করে (অপ্রচলিত):
```javascript
let text = "JavaScript is awesome!";
let substrd = text.substr(11, 7);
console.log(substrd); // আউটপুট: awesome
```

## গভীর ভাবে দেখা
উপস্ত্রিং বের করা নতুন কিছু নয় - এটা প্রোগ্রামিং এর সাথে সমান বয়সী। `substring` এবং `slice` মেথড JavaScript-এর ১৯৯০ দশকের টুল, ভাষার প্রাথমিক ফিচার সেটের অংশ। `substr` ও তাতে ছিল, কিন্তু এখন এটি legacy কোড এবং আধুনিক অ্যাপ্লিকেশনগুলিতে এড়িয়ে চলা উচিত। 

পার্থক্য কি? `substring` এবং `slice` অনুরূপ - উভয়ই শুরু এবং শেষ ইনডেক্স প্যারামিটার নেয় - কিন্তু নেগেটিভ সংখ্যাগুলোকে ভিন্নভাবে সামলায়: `slice` নেগেটিভ ইনডেক্স সমর্থন করে, শেষ থেকে গণনা করে, অন্যদিকে `substring` তাদেরকে শূন্য হিসেবে বিবেচনা করে। এই সব মেথডগুলি মূল স্ট্রিংকে পরিবর্তন করে না; তারা নতুনগুলি তৈরি করে।

## আরো দেখুন
- স্ট্রিংস সম্পর্কে Mozilla Developer Network: [MDN Web Docs - String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
- JavaScript দিয়ে স্ট্রিং ম্যানিপুলেশন: [W3Schools - JavaScript String Methods](https://www.w3schools.com/js/js_string_methods.asp)
- JavaScript স্ট্রিং বেসিক্স: [JavaScript.info - Strings](https://javascript.info/string)
