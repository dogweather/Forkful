---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:42:41.556760-06:00
description: "\u09B8\u09CD\u099F\u09CD\u09AF\u09BE\u09A8\u09CD\u09A1\u09BE\u09B0\u09CD\
  \u09A1 \u098F\u09B0\u09B0\u09C7 (stderr) \u09B2\u09BF\u0996\u09A4\u09C7 \u0997\u09C7\
  \u09B2\u09C7 \u09AE\u09C2\u09B2\u09A4 \u098F\u09B0\u09B0 \u09AE\u09C7\u09B8\u09C7\
  \u099C \u098F\u09AC\u0982 \u09A1\u09BE\u09DF\u09BE\u0997\u09A8\u09B8\u09CD\u099F\
  \u09BF\u0995\u09CD\u09B8 \u0986\u09B2\u09BE\u09A6\u09BE \u0995\u09B0\u09C7 \u09A1\
  \u09BF\u09B0\u09C7\u0995\u09CD\u099F \u0995\u09B0\u09BE \u09B9\u09DF \u09AE\u09C2\
  \u09B2 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09C7\u09B0 \u0986\
  \u0989\u099F\u09AA\u09C1\u099F \u09A5\u09C7\u0995\u09C7, \u09AF\u09BE \u09B8\u09CD\
  \u099F\u09CD\u09AF\u09BE\u09A8\u09CD\u09A1\u09BE\u09B0\u09CD\u09A1 \u0986\u0989\u099F\
  \u09AA\u09C1\u099F\u09C7\u2026"
lastmod: '2024-03-17T18:47:43.965179-06:00'
model: gpt-4-0125-preview
summary: "\u09B8\u09CD\u099F\u09CD\u09AF\u09BE\u09A8\u09CD\u09A1\u09BE\u09B0\u09CD\
  \u09A1 \u098F\u09B0\u09B0\u09C7 (stderr) \u09B2\u09BF\u0996\u09A4\u09C7 \u0997\u09C7\
  \u09B2\u09C7 \u09AE\u09C2\u09B2\u09A4 \u098F\u09B0\u09B0 \u09AE\u09C7\u09B8\u09C7\
  \u099C \u098F\u09AC\u0982 \u09A1\u09BE\u09DF\u09BE\u0997\u09A8\u09B8\u09CD\u099F\
  \u09BF\u0995\u09CD\u09B8 \u0986\u09B2\u09BE\u09A6\u09BE \u0995\u09B0\u09C7 \u09A1\
  \u09BF\u09B0\u09C7\u0995\u09CD\u099F \u0995\u09B0\u09BE \u09B9\u09DF \u09AE\u09C2\
  \u09B2 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09C7\u09B0 \u0986\
  \u0989\u099F\u09AA\u09C1\u099F \u09A5\u09C7\u0995\u09C7, \u09AF\u09BE \u09B8\u09CD\
  \u099F\u09CD\u09AF\u09BE\u09A8\u09CD\u09A1\u09BE\u09B0\u09CD\u09A1 \u0986\u0989\u099F\
  \u09AA\u09C1\u099F\u09C7\u2026"
title: "\u09B8\u09CD\u099F\u09CD\u09AF\u09BE\u09A8\u09CD\u09A1\u09BE\u09B0\u09CD\u09A1\
  \ \u098F\u09B0\u09B0\u09C7 \u09B2\u09BF\u0996\u09A8"
---

{{< edit_this_page >}}

## কি এবং কেন? 

স্ট্যান্ডার্ড এররে (stderr) লিখতে গেলে মূলত এরর মেসেজ এবং ডায়াগনস্টিক্স আলাদা করে ডিরেক্ট করা হয় মূল প্রোগ্রামের আউটপুট থেকে, যা স্ট্যান্ডার্ড আউটপুটে (stdout) যায়। প্রোগ্রামাররা এটি করে থাকেন এরর হ্যান্ডলিং এবং লগিং আরও সহজে ম্যানেজ করার জন্য, বিশেষত যেখানে আউটপুটের পার্থক্য ডিবাগিং এবং মনিটরিংয়ের জন্য অত্যন্ত জরুরি।

## কিভাবে:

এলম মূলত ওয়েব ডেভেলপমেন্টের জন্য টার্গেট করা, যেখানে সরাসরি stderr এ লেখার ধারণাটি ঐতিহ্যবাহী কমান্ড-লাইন এনভায়রনমেন্টের মত একই রকম প্রযোজ্য নয়। তবে, Node.js বা তুলনামূলক এনভায়রনমেন্টগুলিতে চলমান এলম প্রোগ্রামের ক্ষেত্রে, JavaScript এর সাথে পোর্টস ব্যবহার করে ইন্টারঅপের মাধ্যমে একই রকম ফাংশনালিটি অর্জন করা সম্ভব। এটি সেট আপ করার পদ্ধতি এখানে:

এলম কোড (`Main.elm`):
```elm
port module Main উন্মুক্ত করে (main)

Browser আমদানি করুন

port errorOut : String -> Cmd msg

-- JS এ একটি এরর মেসেজ পাঠানোর নমুনা ফাংশন
generateError : String -> Cmd msg
generateError message =
    errorOut message

main =
    generateError "This is an error message for stderr"
```

JavaScript ইন্টারঅপ (`index.js`):
```javascript
const { Elm } = require('./Main.elm');

var app = Elm.Main.init();

app.ports.errorOut.subscribe((message) => {
  console.error(message);
});
```

এই এলম কোডটি `errorOut` নামে একটি পোর্ট সংজ্ঞায়িত করে যা এলম থেকে JavaScript-এ মেসেজ পাঠাতে অনুমতি দেয়। তারপর জাভাস্ক্রিপ্ট কোডে, আমরা এই পোর্টের মাধ্যমে পাঠানো মেসেজগুলি শুনি এবং `console.error()` ব্যবহার করে stderr-এ রিডিরেক্ট করি। এইভাবে, আপনি Elm-এর সাথে JavaScript-এর ইন্টারঅপ বৈশিষ্ট্যগুলি ব্যবহার করে একটি সাপোর্ট করা এনভায়রনমেন্টে কার্যকরভাবে stderr-এ লিখতে পারেন।

Node.js টার্মিনালে নমুনা আউটপুট (যখন `index.js` রান করা হয়):
```
This is an error message for stderr
```
