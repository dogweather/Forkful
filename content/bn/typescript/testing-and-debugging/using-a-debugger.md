---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:23:24.650372-06:00
description: "\u09A1\u09BF\u09AC\u09BE\u0997\u09BE\u09B0 \u09B9\u09B2 \u098F\u09AE\
  \u09A8 \u098F\u0995\u099F\u09BF \u099F\u09C1\u09B2 \u09AF\u09BE \u0986\u09AA\u09A8\
  \u09BE\u0995\u09C7 \u0986\u09AA\u09A8\u09BE\u09B0 \u0995\u09CB\u09A1\u09C7\u09B0\
  \ \u0985\u09AD\u09CD\u09AF\u09A8\u09CD\u09A4\u09B0\u09C0\u09A3 \u0995\u09BE\u09B0\
  \u09CD\u09AF\u09AA\u09CD\u09B0\u09A3\u09BE\u09B2\u09C0 \u09AA\u09B0\u09C0\u0995\u09CD\
  \u09B7\u09BE \u0995\u09B0\u09A4\u09C7 \u098F\u09AC\u0982 \u09A4\u09BE \u099A\u09BE\
  \u09B2\u09BE\u09A8\u09CB\u09B0 \u09B8\u09AE\u09AF\u09BC \u09AA\u09B0\u09BF\u09AC\
  \u09B0\u09CD\u09A4\u09A8 \u0995\u09B0\u09A4\u09C7 \u09A6\u09C7\u09AF\u09BC\u0964\
  \ \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE\
  \ \u09A4\u09BE\u09A6\u09C7\u09B0 \u0995\u09CB\u09A1 \u09A7\u09BE\u09AA\u09C7\u2026"
lastmod: '2024-03-17T18:47:43.769715-06:00'
model: gpt-4-0125-preview
summary: "\u09A1\u09BF\u09AC\u09BE\u0997\u09BE\u09B0 \u09B9\u09B2 \u098F\u09AE\u09A8\
  \ \u098F\u0995\u099F\u09BF \u099F\u09C1\u09B2 \u09AF\u09BE \u0986\u09AA\u09A8\u09BE\
  \u0995\u09C7 \u0986\u09AA\u09A8\u09BE\u09B0 \u0995\u09CB\u09A1\u09C7\u09B0 \u0985\
  \u09AD\u09CD\u09AF\u09A8\u09CD\u09A4\u09B0\u09C0\u09A3 \u0995\u09BE\u09B0\u09CD\u09AF\
  \u09AA\u09CD\u09B0\u09A3\u09BE\u09B2\u09C0 \u09AA\u09B0\u09C0\u0995\u09CD\u09B7\u09BE\
  \ \u0995\u09B0\u09A4\u09C7 \u098F\u09AC\u0982 \u09A4\u09BE \u099A\u09BE\u09B2\u09BE\
  \u09A8\u09CB\u09B0 \u09B8\u09AE\u09AF\u09BC \u09AA\u09B0\u09BF\u09AC\u09B0\u09CD\
  \u09A4\u09A8 \u0995\u09B0\u09A4\u09C7 \u09A6\u09C7\u09AF\u09BC\u0964 \u09AA\u09CD\
  \u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u09A4\u09BE\u09A6\
  \u09C7\u09B0 \u0995\u09CB\u09A1 \u09A7\u09BE\u09AA\u09C7\u2026"
title: "\u09A1\u09BF\u09AC\u09BE\u0997\u09BE\u09B0 \u09AC\u09CD\u09AF\u09AC\u09B9\u09BE\
  \u09B0 \u0995\u09B0\u09BE"
---

## কিভাবে:
TypeScript এ একটি ডিবাগারের সাথে শুরু করতে, আপনার কেবল একটি সমর্থিত IDE (যেমন Visual Studio Code) এবং একটি `launch.json` কনফিগারেশনের প্রয়োজন। এখানে একটি Node.js অ্যাপ্লিকেশনের জন্য একটি দ্রুত উদাহরণ দেওয়া হল:

```TypeScript
// app.ts
function greet(name: string) {
    console.log(`Hello, ${name}!`);
}

const userName = 'Ada';
greet(userName);
```

এটি ডিবাগ করতে, `.vscode` ফোল্ডারের অধীনে একটি `launch.json` ফাইল তৈরি করুন:

```JSON
{
    "version": "0.2.0",
    "configurations": [
        {
            "type": "node",
            "request": "launch",
            "name": "Launch Program",
            "skipFiles": ["<node_internals>/**"],
            "program": "${workspaceFolder}/app.ts",
            "preLaunchTask": "tsc: build - tsconfig.json",
            "outFiles": ["${workspaceFolder}/build/**/*.js"]
        }
    ]
}
```

তারপর, আপনার IDE-এ লাইন নম্বরের বাম পাশে ক্লিক করে `greet` ফাংশনে একটি ব্রেকপয়েন্ট সেট করুন। F5 চাপুন ডিবাগিং শুরু করতে, এবং দেখুন আপনার অ্যাপ ব্রেকপয়েন্টে থামছে। এখন আপনি ভ্যারিয়েবলগুলির উপর মাউস নিয়ে যেতে, এক্সপ্রেশন দেখতে এবং আপনার কোডের মধ্যে দিয়ে সহজেই ধাপে ধাপে অগ্রসর হতে পারেন।

## গভীর ডুব
ইন্টিগ্রেটেড ডেভেলপমেন্ট এনভায়রনমেন্টস (IDEs) চটকদার না হওয়ার আগে, প্রিন্ট স্টেটমেন্ট (অথবা `console.log` ডিবাগিং) দিয়ে প্রায়শই ডিবাগিং করা হত। এটি করা যেত, কিছুটা হলেও, কিন্তু এটি ছিল চোখ বেঁধে খড়ের গাদায় সূচ খুঁজে পাওয়ার মতো।

আধুনিক ডিবাগারগুলি হল সমস্যা সমাধানের জন্য একটি সুইস আর্মি ছুরি। TypeScript এবং Node.js-এর বিকাশের সাথে সাথে, বিল্ট-ইন Node.js ইন্সপেক্টর থেকে শুরু করে ক্লায়েন্ট-সাইড ডিবাগিংয়ের জন্য ব্রাউজার দেভ টুলস পর্যন্ত নানান ডিবাগার উপলব্ধ।

Node.js ইন্সপেক্টর কাজ করে আপনার চলমান অ্যাপ্লিকেশনের সাথে যুক্ত হয়ে; এটি Chrome DevTools Protocol এর মাধ্যমে যোগাযোগ করে, আপনার Chrome ব্রাউজারকে একটি শক্তিশালী ডিবাগিং কনসোলে পরিণত করে। এই সংহতি প্রথাগত কমান্ড-লাইন ডিবাগিং অনুশীলনের তুলনায় একটি দৃশ্যমান ইন্টারেক্টিভ এবং বিস্তারিত ডিবাগিং সেশনের অনুমতি দেয়।

## আরও দেখুন
আরও কিছু পড়ার জন্য এবং কিছু পেশাদার টিপসের জন্য, দেখুন:

- [Visual Studio Code-এ TypeScript ডিবাগিং](https://code.visualstudio.com/docs/typescript/typescript-debugging)
- [Node.js ডিবাগিং গাইড](https://nodejs.org/en/docs/guides/debugging-getting-started/)
- [Chrome DevTools ডকুমেন্টেশন](https://developers.google.com/web/tools/chrome-devtools)
