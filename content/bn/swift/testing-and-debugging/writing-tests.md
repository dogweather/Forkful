---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:42:03.334655-06:00
description: "Swift \u098F \u099F\u09C7\u09B8\u09CD\u099F \u09B2\u09C7\u0996\u09BE\
  \ \u09AE\u09BE\u09A8\u09C7 \u098F\u09AE\u09A8 \u0995\u09CB\u09A1 \u09A4\u09C8\u09B0\
  \u09BF \u0995\u09B0\u09BE \u098F\u09AC\u0982 \u09A8\u09BF\u09B0\u09CD\u09AC\u09BE\
  \u09B9 \u0995\u09B0\u09BE \u09AF\u09BE \u0986\u09AA\u09A8\u09BE\u09B0 \u0985\u09CD\
  \u09AF\u09BE\u09AA\u09CD\u09B2\u09BF\u0995\u09C7\u09B6\u09A8\u09C7\u09B0 \u0985\u09A8\
  \u09CD\u09AF\u09BE\u09A8\u09CD\u09AF \u0995\u09CB\u09A1 \u0987\u0989\u09A8\u09BF\
  \u099F\u09C7\u09B0 \u09B8\u09A0\u09BF\u0995\u09A4\u09BE \u09AF\u09BE\u099A\u09BE\
  \u0987 \u0995\u09B0\u09C7\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\
  \u09AE\u09BE\u09B0\u09B0\u09BE \u098F\u099F\u09BF \u09A8\u09BF\u09B0\u09CD\u09AD\
  \u09B0\u09AF\u09CB\u0997\u09CD\u09AF\u09A4\u09BE\u2026"
lastmod: '2024-03-17T18:47:44.413253-06:00'
model: gpt-4-0125-preview
summary: "Swift \u098F \u099F\u09C7\u09B8\u09CD\u099F \u09B2\u09C7\u0996\u09BE \u09AE\
  \u09BE\u09A8\u09C7 \u098F\u09AE\u09A8 \u0995\u09CB\u09A1 \u09A4\u09C8\u09B0\u09BF\
  \ \u0995\u09B0\u09BE \u098F\u09AC\u0982 \u09A8\u09BF\u09B0\u09CD\u09AC\u09BE\u09B9\
  \ \u0995\u09B0\u09BE \u09AF\u09BE \u0986\u09AA\u09A8\u09BE\u09B0 \u0985\u09CD\u09AF\
  \u09BE\u09AA\u09CD\u09B2\u09BF\u0995\u09C7\u09B6\u09A8\u09C7\u09B0 \u0985\u09A8\u09CD\
  \u09AF\u09BE\u09A8\u09CD\u09AF \u0995\u09CB\u09A1 \u0987\u0989\u09A8\u09BF\u099F\
  \u09C7\u09B0 \u09B8\u09A0\u09BF\u0995\u09A4\u09BE \u09AF\u09BE\u099A\u09BE\u0987\
  \ \u0995\u09B0\u09C7\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\
  \u09BE\u09B0\u09B0\u09BE \u098F\u099F\u09BF \u09A8\u09BF\u09B0\u09CD\u09AD\u09B0\
  \u09AF\u09CB\u0997\u09CD\u09AF\u09A4\u09BE\u2026"
title: "\u099F\u09C7\u09B8\u09CD\u099F \u09B2\u09BF\u0996\u09BE"
---

{{< edit_this_page >}}

## কি এবং কেন?
Swift এ টেস্ট লেখা মানে এমন কোড তৈরি করা এবং নির্বাহ করা যা আপনার অ্যাপ্লিকেশনের অন্যান্য কোড ইউনিটের সঠিকতা যাচাই করে। প্রোগ্রামাররা এটি নির্ভরযোগ্যতা নিশ্চিত করতে, বিকাশ চক্রের প্রাথমিক পর্যায়ে বাগ শনাক্ত করতে এবং অনিচ্ছাকৃত পরিণাম ছাড়াই ভবিষ্যতের কোড রিফ্যাক্টরিংকে সহজ করতে করে।

## কীভাবে:
Swift এর XCTest ফ্রেমওয়ার্কের মাধ্যমে টেস্টিং সমর্থন করে, যা Xcode এ সমন্বিত হয়েছে। আপনি আপনার কোডের প্রতিটি অংশ যাচাই করার জন্য ইউনিট টেস্ট লিখতে পারেন, যেমন দুটি সংখ্যা যোগ করা একটি ফাংশন।

```swift
import XCTest
@testable import YourApp

class YourAppTests: XCTestCase {

    func testSum() {
        let result = Calculator().sum(a: 1, b: 2)
        XCTAssertEqual(result, 3, "যোগ ফাংশন প্রত্যাশিত মান ফেরত দেয়নি।")
    }
}
```

এই টেস্টটি চালানোর জন্য, আপনি সাধারণত Xcode এ Command-U চাপবেন। Xcode টেস্ট নেভিগেটরের আউটপুট আপনাকে জানাবে যে টেস্টটি পাস হয়েছে কিনা বা ব্যর্থ হয়েছে।

উদাহরণস্বরূপ, একটি সফল টেস্ট আউটপুট:
```
টেস্ট কেস '-[YourAppTests testSum]' সফল হয়েছে (0.005 সেকেন্ড)।
```

আরও উন্নত টেস্টিং সিনারিওর জন্য, আপনি তৃতীয়-পক্ষের লাইব্রেরিগুলি যেমন Quick/Nimble সম্পর্কে চিন্তা করতে পারেন, যা টেস্ট লেখার জন্য আরও ব্যক্তিগত বাক্যবিন্যাস প্রদান করে।

Quick/Nimble এর সাথে, আপনি একই টেস্টটি এরকম লিখতে পারেন:

```swift
// আপনার Swift প্যাকেজ ম্যানেজারে Quick এবং Nimble যোগ করুন অথবা তাদের ইনস্টল করতে CocoaPods/Carthage ব্যবহার করুন
import Quick
import Nimble
@testable import YourApp

class CalculatorSpec: QuickSpec {
    override func spec() {
        describe("Calculator") {
            context("when summing numbers") {
                it("should return the correct sum") {
                    let calculator = Calculator()
                    expect(calculator.sum(a: 1, b: 2)).to(equal(3))
                }
            }
        }
    }
}
```

এই টেস্টটি চালানো আপনার টেস্ট কনসোল বা CI/CD টুলের লগে সাফল্য বা ব্যর্থতার ইন্ডিকেশনের সাথে একই রকমের আউটপুট দেবে, টেস্ট এবং প্রত্যাশাগুলি বর্ণনার জন্য আরও পঠনযোগ্য ফর্ম্যাট সরবরাহ করে।
