---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:10:08.611893-06:00
description: "\u0995\u09AE\u09BE\u09A8\u09CD\u09A1 \u09B2\u09BE\u0987\u09A8 \u0986\
  \u09B0\u09CD\u0997\u09C1\u09AE\u09C7\u09A8\u09CD\u099F\u09C7\u09B0 \u09AE\u09BE\u09A8\
  \u09C7 \u09B9\u099A\u09CD\u099B\u09C7 \u09AF\u0996\u09A8 \u09AC\u09CD\u09AF\u09AC\
  \u09B9\u09BE\u09B0\u0995\u09BE\u09B0\u09C0\u09B0\u09BE \u0986\u09AA\u09A8\u09BE\u09B0\
  \ \u09B8\u09CD\u0995\u09CD\u09B0\u09BF\u09AA\u09CD\u099F \u099A\u09BE\u09B2\u09BE\
  \u09A8 \u09A4\u0996\u09A8 \u09A4\u09BE\u09B0\u09BE \u09AF\u09C7 \u0985\u09A4\u09BF\
  \u09B0\u09BF\u0995\u09CD\u09A4 \u09A4\u09A5\u09CD\u09AF\u0997\u09C1\u09B2\u09CB\
  \ \u09AF\u09CB\u0997 \u0995\u09B0\u09C7, \u09A4\u09BE \u0997\u09CD\u09B0\u09B9\u09A3\
  \ \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\
  \u09BE\u09B0\u09B0\u09BE \u098F\u099F\u09BF \u0995\u09B0\u09C7\u2026"
lastmod: '2024-03-17T18:47:44.468705-06:00'
model: gpt-4-0125-preview
summary: "\u0995\u09AE\u09BE\u09A8\u09CD\u09A1 \u09B2\u09BE\u0987\u09A8 \u0986\u09B0\
  \u09CD\u0997\u09C1\u09AE\u09C7\u09A8\u09CD\u099F\u09C7\u09B0 \u09AE\u09BE\u09A8\u09C7\
  \ \u09B9\u099A\u09CD\u099B\u09C7 \u09AF\u0996\u09A8 \u09AC\u09CD\u09AF\u09AC\u09B9\
  \u09BE\u09B0\u0995\u09BE\u09B0\u09C0\u09B0\u09BE \u0986\u09AA\u09A8\u09BE\u09B0\
  \ \u09B8\u09CD\u0995\u09CD\u09B0\u09BF\u09AA\u09CD\u099F \u099A\u09BE\u09B2\u09BE\
  \u09A8 \u09A4\u0996\u09A8 \u09A4\u09BE\u09B0\u09BE \u09AF\u09C7 \u0985\u09A4\u09BF\
  \u09B0\u09BF\u0995\u09CD\u09A4 \u09A4\u09A5\u09CD\u09AF\u0997\u09C1\u09B2\u09CB\
  \ \u09AF\u09CB\u0997 \u0995\u09B0\u09C7, \u09A4\u09BE \u0997\u09CD\u09B0\u09B9\u09A3\
  \ \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\
  \u09BE\u09B0\u09B0\u09BE \u098F\u099F\u09BF \u0995\u09B0\u09C7\u2026"
title: "\u0995\u09AE\u09BE\u09A8\u09CD\u09A1 \u09B2\u09BE\u0987\u09A8 \u0986\u09B0\
  \u09CD\u0997\u09C1\u09AE\u09C7\u09A8\u09CD\u099F\u0997\u09C1\u09B2\u09BF \u09AA\u09A1\
  \u09BC\u09BE"
---

{{< edit_this_page >}}

## কি এবং কেন?
কমান্ড লাইন আর্গুমেন্টের মানে হচ্ছে যখন ব্যবহারকারীরা আপনার স্ক্রিপ্ট চালান তখন তারা যে অতিরিক্ত তথ্যগুলো যোগ করে, তা গ্রহণ করা। প্রোগ্রামাররা এটি করে থাকেন যাতে ব্যবহারকারীরা কোড পরিবর্তন না করেও আচরণ কাস্টমাইজ করতে পারে।

## কিভাবে:
Node.js-এ এটি করার সরাসরি উপায় এখানে:

```javascript
// process.argv কমান্ড লাইন আর্গুমেন্ট ধারণ করে
const args = process.argv.slice(2);

console.log(args);

// এই স্ক্রিপ্ট চালান: node yourscript.js firstArg secondArg
```

যদি আপনি `node yourscript.js pineapple 42` চালান তাহলে নিম্নলিখিত আউটপুট পাবেন:

```javascript
['pineapple', '42']
```

যেমন `yargs` মত একটি প্যাকেজ ব্যবহার করা জীবনকে সহজ করে তোলে, এটি আপনাকে নাম দ্বারা আর্গুমেন্ট ঠিক করে দেওয়া এবং অ্যাক্সেস করতে দেয়।

```javascript
// npm install yargs দিয়ে ইন্সটল করুন
const yargs = require('yargs/yargs');
const { hideBin } = require('yargs/helpers');
const argv = yargs(hideBin(process.argv)).argv;

console.log(argv);

// এটি চালান: node yourscript.js --fruit pineapple --number 42
```

এবং আপনি পাবেন:

```javascript
{ fruit: 'pineapple', number: '42' }
```

নামকৃত পরামিতি দিয়ে পরিষ্কার এবং স্পষ্ট।

## গভীর ডাইভ
অনেক আগে, C ভাষায় `argc` এবং `argv` ব্যবহার করে `main` ফাংশনে আর্গুমেন্টগুলি পড়া হত। Node.js-এ, `process.argv` হলো সেই পথ। এটি একটি অ্যারে যার প্রথম উপাদান হল নোড এক্সিকিউটেবলের পথ, দ্বিতীয়টি হল স্ক্রিপ্ট ফাইলের নাম, এবং বাকি গুলি হল আপনার আসল আর্গুমেন্টস।

`yargs` জটিল অ্যাপের জন্য দারুণ: এটি আর্গুমেন্টগুলিকে একটি সুবিধাজনক অবজেক্টে পার্স করে, ডিফল্টগুলি পরিচালনা করে, এবং এমনকি সহায়ক বার্তাগুলি অটো-জেনারেট করে।

`minimist` প্যাকেজও আছে, যদি আপনি ন্যূনতাবাদের প্রতি ঝোঁক রাখেন তাহলে `yargs`-এর একটি হালকা বিকল্প।

গভীরে, Node.js V8-এর `process.binding('options')` ব্যবহার করে পার্সিংয়ের জন্য যা সাধারণ ব্যবহারকারীর কাছে প্রকাশ করা হয় না। এই আভ্যন্তরীণ পদ্ধতিটি কমান্ড লাইন অপশনের পার্সিং এবং পুনরুদ্ধারের ব্যবস্থাপনার অধীনে প্রচুর উপকারিতা সম্বলিত করে।

## আরও দেখুন
- Node.js process.argv ডকুমেন্টেশন: https://nodejs.org/docs/latest/api/process.html#process_process_argv
- Yargs GitHub রেপো: https://github.com/yargs/yargs
- Minimist-এ npm: https://www.npmjs.com/package/minimist
