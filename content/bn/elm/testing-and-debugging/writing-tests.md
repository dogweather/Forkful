---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:41:18.766649-06:00
description: "Elm \u098F \u099F\u09C7\u09B8\u09CD\u099F \u09B2\u09C7\u0996\u09BE \u09AE\
  \u09BE\u09A8\u09C7 \u0986\u09AA\u09A8\u09BE\u09B0 Elm \u0995\u09CB\u09A1\u09C7\u09B0\
  \ \u09B8\u09A0\u09BF\u0995\u09A4\u09BE \u09AF\u09BE\u099A\u09BE\u0987 \u0995\u09B0\
  \u09BE\u09B0 \u099C\u09A8\u09CD\u09AF \u099F\u09C7\u09B8\u09CD\u099F \u0995\u09C7\
  \u09B8\u0997\u09C1\u09B2\u09BF \u09A4\u09C8\u09B0\u09BF \u0995\u09B0\u09BE, \u09AF\
  \u09BE\u09A4\u09C7 \u09A8\u09BF\u09B6\u09CD\u099A\u09BF\u09A4 \u0995\u09B0\u09BE\
  \ \u09AF\u09BE\u09AF\u09BC \u09AF\u09C7 \u098F\u099F\u09BF \u09AA\u09CD\u09B0\u09A4\
  \u09CD\u09AF\u09BE\u09B6\u09BF\u09A4 \u09AE\u09A4 \u0995\u09BE\u099C \u0995\u09B0\
  \u099B\u09C7\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\
  \u09B0\u09BE\u2026"
lastmod: '2024-03-17T18:47:43.952174-06:00'
model: gpt-4-0125-preview
summary: "Elm \u098F \u099F\u09C7\u09B8\u09CD\u099F \u09B2\u09C7\u0996\u09BE \u09AE\
  \u09BE\u09A8\u09C7 \u0986\u09AA\u09A8\u09BE\u09B0 Elm \u0995\u09CB\u09A1\u09C7\u09B0\
  \ \u09B8\u09A0\u09BF\u0995\u09A4\u09BE \u09AF\u09BE\u099A\u09BE\u0987 \u0995\u09B0\
  \u09BE\u09B0 \u099C\u09A8\u09CD\u09AF \u099F\u09C7\u09B8\u09CD\u099F \u0995\u09C7\
  \u09B8\u0997\u09C1\u09B2\u09BF \u09A4\u09C8\u09B0\u09BF \u0995\u09B0\u09BE, \u09AF\
  \u09BE\u09A4\u09C7 \u09A8\u09BF\u09B6\u09CD\u099A\u09BF\u09A4 \u0995\u09B0\u09BE\
  \ \u09AF\u09BE\u09AF\u09BC \u09AF\u09C7 \u098F\u099F\u09BF \u09AA\u09CD\u09B0\u09A4\
  \u09CD\u09AF\u09BE\u09B6\u09BF\u09A4 \u09AE\u09A4 \u0995\u09BE\u099C \u0995\u09B0\
  \u099B\u09C7\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\
  \u09B0\u09BE\u2026"
title: "\u099F\u09C7\u09B8\u09CD\u099F \u09B2\u09BF\u0996\u09BE"
---

{{< edit_this_page >}}

## কী এবং কেন?

Elm এ টেস্ট লেখা মানে আপনার Elm কোডের সঠিকতা যাচাই করার জন্য টেস্ট কেসগুলি তৈরি করা, যাতে নিশ্চিত করা যায় যে এটি প্রত্যাশিত মত কাজ করছে। প্রোগ্রামাররা এটি করে থাকে তারা যেন তাদের অ্যাপ্লিকেশনগুলির মান ও নির্ভরযোগ্যতা উন্নতি করতে পারে এবং শুরুতেই বাগ ধরতে, রখরখাও সহজ করতে এবং মান উন্নতি করতে।

## কীভাবে:

Elm `elm-explorations/test` প্যাকেজ ব্যবহার করে ইউনিট এবং ফাজ টেস্ট লেখার জন্য। প্রথমত, আপনার প্রজেক্টে এই প্যাকেজটি যোগ করতে:

```elm
elm install elm-explorations/test
```

একটি টেস্ট ফাইল তৈরি করুন, ধরুন `tests/ExampleTest.elm`, এবং টেস্টিং মডিউলগুলি ইম্পোর্ট করুন। এখানে একটি সহজ টেস্ট দেওয়া হলো যা `add : Int -> Int -> Int` ফাংশনটি যাচাই করে:

```elm
module ExampleTest exposing (..)

import Expect
import Test exposing (..)
import YourModuleName exposing (add)

suite : Test
suite =
    describe "A simple addition function"
        [ test "Adding 2 and 3 yields 5" <| 
            \_ -> add 2 3 |> Expect.equal 5
        ]

```

আপনার টেস্ট চালাতে, আপনার `elm-test` প্রয়োজন হবে:

```shell
npm install -g elm-test
elm-test
```

এটি আপনার টেস্টগুলি কম্পাইল করবে এবং আপনার টার্মিনালে ফলাফল প্রিন্ট করবে। উপরে দেওয়া উদাহরণের জন্য, আউটপুট কিছু এইরকম হবে:

```
TEST RUN PASSED

Duration: 42 ms
Passed:   1
Failed:   0
```

একটি জটিল উদাহরণের জন্য, ধরুন আপনি `add` ফাংশনটিকে ফাজ টেস্ট করতে চান যাতে এটি সঠিকভাবে বিভিন্ন রেঞ্জের ইন্টিজার ইনপুট দিয়ে কাজ করতে পারে। আপনার `ExampleTest.elm` ফাইলটি আপনি যেমন পরিবর্তন করবেন:

```elm
module ExampleTest exposing (..)

import Expect
import Fuzz exposing (int)
import Test exposing (..)
import YourModuleName exposing (add)

suite : Test
suite =
    describe "Testing add with fuzzing"
        [ fuzz int "Fuzz testing add with random ints" <| 
            \int1 int2 -> add int1 int2 |> Expect.equal (int1 + int2)
        ]
```

`elm-test` আবার চালান যদি আপনি ফাজ টেস্টগুলি ক্রিয়াকলাপে দেখতে চান। আউটপুট র্যান্ডম ইনপুটের সাথে পরিবর্তন হবে কিন্তু সফল টেস্টগুলি কোনো ব্যর্থতা না ইঙ্গিত করবে:

```
TEST RUN PASSED

Duration: 183 ms
Passed:   100
Failed:   0
``` 

এই উদাহরণগুলি দেখায় কীভাবে Elm এ সহজ ইউনিট এবং ফাজ টেস্ট লিখতে এবং চালাতে হয়, `elm-explorations/test` প্যাকেজ ব্যবহার করে। টেস্টিং হল উন্নয়ন প্রক্রিয়ার একটি জীবন্ত অংশ, যা নিশ্চিত করে যে আপনার Elm অ্যাপ্লিকেশনগুলি নির্ভরযোগ্য এবং উচ্চ মানের থাকে।
