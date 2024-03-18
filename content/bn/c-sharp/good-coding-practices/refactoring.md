---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:11:07.675401-06:00
description: "\u09B0\u09BF\u09AB\u09CD\u09AF\u09BE\u0995\u09CD\u099F\u09B0\u09BF\u0982\
  \ \u09B9\u09B2 \u09AC\u09BF\u09A6\u09CD\u09AF\u09AE\u09BE\u09A8 \u0995\u09AE\u09CD\
  \u09AA\u09BF\u0989\u099F\u09BE\u09B0 \u0995\u09CB\u09A1\u09C7\u09B0 \u09AA\u09C1\
  \u09A8\u0983\u0997\u09A0\u09A8\u09C7\u09B0 \u09AA\u09CD\u09B0\u0995\u09CD\u09B0\u09BF\
  \u09AF\u09BC\u09BE \u09AF\u09BE\u09B0 \u09AE\u09A7\u09CD\u09AF \u09A6\u09BF\u09AF\
  \u09BC\u09C7 \u0995\u09CB\u09A1\u09C7\u09B0 \u09AC\u09BE\u09B9\u09CD\u09AF\u09BF\
  \u0995 \u0986\u099A\u09B0\u09A3\u09C7 \u0995\u09CB\u09A8\u09CB \u09AA\u09B0\u09BF\
  \u09AC\u09B0\u09CD\u09A4\u09A8 \u0986\u09A8\u09BE \u09B9\u09AF\u09BC \u09A8\u09BE\
  \u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE\
  \ \u0995\u09CB\u09A1 \u09AA\u09B0\u09BF\u09B7\u09CD\u0995\u09BE\u09B0 \u0995\u09B0\
  \u09BE,\u2026"
lastmod: '2024-03-17T18:47:44.046327-06:00'
model: gpt-4-0125-preview
summary: "\u09B0\u09BF\u09AB\u09CD\u09AF\u09BE\u0995\u09CD\u099F\u09B0\u09BF\u0982\
  \ \u09B9\u09B2 \u09AC\u09BF\u09A6\u09CD\u09AF\u09AE\u09BE\u09A8 \u0995\u09AE\u09CD\
  \u09AA\u09BF\u0989\u099F\u09BE\u09B0 \u0995\u09CB\u09A1\u09C7\u09B0 \u09AA\u09C1\
  \u09A8\u0983\u0997\u09A0\u09A8\u09C7\u09B0 \u09AA\u09CD\u09B0\u0995\u09CD\u09B0\u09BF\
  \u09AF\u09BC\u09BE \u09AF\u09BE\u09B0 \u09AE\u09A7\u09CD\u09AF \u09A6\u09BF\u09AF\
  \u09BC\u09C7 \u0995\u09CB\u09A1\u09C7\u09B0 \u09AC\u09BE\u09B9\u09CD\u09AF\u09BF\
  \u0995 \u0986\u099A\u09B0\u09A3\u09C7 \u0995\u09CB\u09A8\u09CB \u09AA\u09B0\u09BF\
  \u09AC\u09B0\u09CD\u09A4\u09A8 \u0986\u09A8\u09BE \u09B9\u09AF\u09BC \u09A8\u09BE\
  \u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE\
  \ \u0995\u09CB\u09A1 \u09AA\u09B0\u09BF\u09B7\u09CD\u0995\u09BE\u09B0 \u0995\u09B0\
  \u09BE,\u2026"
title: "\u09B0\u09BF\u09AB\u09CD\u09AF\u09BE\u0995\u09CD\u099F\u09B0\u09BF\u0982"
---

{{< edit_this_page >}}

## কি এবং কেন?

রিফ্যাক্টরিং হল বিদ্যমান কম্পিউটার কোডের পুনঃগঠনের প্রক্রিয়া যার মধ্য দিয়ে কোডের বাহ্যিক আচরণে কোনো পরিবর্তন আনা হয় না। প্রোগ্রামাররা কোড পরিষ্কার করা, পঠনীয়তা বাড়ানো, জটিলতা কমানো এবং রক্ষণাবেক্ষণের উন্নতি সাধনের জন্য এটি করে থাকেন।

## কিভাবে:

আসুন আমরা একটি সাধারণ C# মেথড রিফ্যাক্টর করি যা একটি সংখ্যার অ্যারের যোগফল গণনা এবং প্রিন্ট করে:

রিফ্যাক্টরিং এর আগে:
```C#
public class Calculator
{
    public void CalculateSum()
    {
        int[] numbers = { 1, 2, 3, 4, 5 };
        int sum = 0;
        for (int i = 0; i < numbers.Length; i++)
        {
            sum += numbers[i];
        }
        Console.WriteLine("The sum is " + sum);
    }
}
```

রিফ্যাক্টরিং এর পরে:
```C#
public class Calculator
{
    private readonly int[] _numbers;

    public Calculator(int[] numbers)
    {
        _numbers = numbers;
    }

    public int CalculateSum()
    {
        return _numbers.Sum();
    }

    public void DisplaySum()
    {
        Console.WriteLine($"The sum is {CalculateSum()}");
    }
}

// ব্যবহার:
var calculator = new Calculator(new[] { 1, 2, 3, 4, 5 });
calculator.DisplaySum();
```

রিফ্যাক্টরিং এর মাধ্যমে, আমরা উদ্বেগ পৃথককরণ করেছি, `Calculator` ক্লাসকে আরও লচকদার করে তুলেছি যাতে এটি যেকোনো সংখ্যার অ্যারে নিতে পারে, এবং LINQ ব্যবহার করে যোগফল গণনা আরও সংক্ষিপ্ত করেছি।

## গভীর ডুব

রিফ্যাক্টরিং এর উৎস রয়েছে স্মলটক প্রোগ্রামিং কমিউনিটিতে এবং ১৯৯০ এর দশকে মার্টিন ফাউলারের বই "Refactoring: Improving the Design of Existing Code" দ্বারা এটি জনপ্রিয় হয়। বছরের পর বছর, এটি এজাইল পদ্ধতিগুলি এবং ভাল কোডিং অনুশীলনের একটি মৌলিক অংশ হয়ে উঠেছে।

রিফ্যাক্টরিং এর বিভিন্ন পদ্ধতি রয়েছে, যেমন টেস্ট-ড্রাইভেন ডেভেলপমেন্ট (TDD) এ রেড-গ্রিন-রিফ্যাক্টর। এটি নিশ্চিত করে যে রিফ্যাক্টরিং বাগ প্রবর্তন করে না একটি ব্যর্থ টেস্ট দিয়ে শুরু করে, এটিকে পাস করা, এবং তারপর কোডটি পরিষ্কার করা।

রিফ্যাক্টরিং বাস্তবায়ন করার সময় প্রক্রিয়ার সময় কোনো কার্যকারিতা ভঙ্গ না হওয়ার নিশ্চয়তা দেওয়ার জন্য একটি বিস্তৃত পরীক্ষা সেট থাকা জরুরি। C# এর জন্য ReSharper এর মতো স্বয়ংক্রিয় রিফ্যাক্টরিং টুলগুলি কোড কাঠামো পরিবর্তনের নিরাপদ উপায় প্রদান করে এই প্রক্রিয়াতে সাহায্য করতে পারে। তবে, টুলিং কোডবেস এবং কোডিং নীতিগুলির গভীর উপলব্ধির পরিপূরক হওয়া উচিত।

## আরও দেখুন

- রিফ্যাক্টরিং নিয়ে মার্টিন ফাউলারের মৌলিক কাজ: [Refactoring: Improving the Design of Existing Code](https://martinfowler.com/books/refactoring.html)
- ভিজ্যুয়াল স্টুডিওতে রিফ্যাক্টরিং নিয়ে মাইক্রোসফটের গাইড: [Refactoring (C#)](https://docs.microsoft.com/en-us/visualstudio/ide/refactoring-in-visual-studio?view=vs-2022)
- উদাহরণ সহ রিফ্যাক্টরিং প্যাটার্নগুলির বিস্তারিত তদন্ত: [SourceMaking Refactoring](https://sourcemaking.com/refactoring)
