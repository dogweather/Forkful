---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:31:33.715107-06:00
description: "XML (eXtensible Markup Language) \u09B9\u09B2\u09CB \u09A1\u09C7\u099F\
  \u09BE \u09B8\u0982\u0997\u09A0\u09BF\u09A4 \u0995\u09B0\u09BE\u09B0 \u098F\u0995\
  \u099F\u09BF \u09AA\u09A6\u09CD\u09A7\u09A4\u09BF \u09AF\u09BE \u09AA\u09BE\u09A0\
  \u09AF\u09CB\u0997\u09CD\u09AF \u09AB\u09B0\u09AE\u09CD\u09AF\u09BE\u099F\u09C7\
  \ \u09A1\u09C7\u099F\u09BE \u09AA\u09B0\u09BF\u099A\u09BE\u09B2\u09A8\u09BE \u0995\
  \u09B0\u09C7\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\
  \u09B0\u09BE \u0995\u09A8\u09AB\u09BF\u0997\u09BE\u09B0\u09C7\u09B6\u09A8, \u0985\
  \u09CD\u09AF\u09BE\u09AA\u09C7\u09B0 \u09AE\u09A7\u09CD\u09AF\u09C7 \u09A1\u09C7\
  \u099F\u09BE\u2026"
lastmod: '2024-03-17T18:47:44.063070-06:00'
model: gpt-4-0125-preview
summary: "XML (eXtensible Markup Language) \u09B9\u09B2\u09CB \u09A1\u09C7\u099F\u09BE\
  \ \u09B8\u0982\u0997\u09A0\u09BF\u09A4 \u0995\u09B0\u09BE\u09B0 \u098F\u0995\u099F\
  \u09BF \u09AA\u09A6\u09CD\u09A7\u09A4\u09BF \u09AF\u09BE \u09AA\u09BE\u09A0\u09AF\
  \u09CB\u0997\u09CD\u09AF \u09AB\u09B0\u09AE\u09CD\u09AF\u09BE\u099F\u09C7 \u09A1\
  \u09C7\u099F\u09BE \u09AA\u09B0\u09BF\u099A\u09BE\u09B2\u09A8\u09BE \u0995\u09B0\
  \u09C7\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\
  \u09BE \u0995\u09A8\u09AB\u09BF\u0997\u09BE\u09B0\u09C7\u09B6\u09A8, \u0985\u09CD\
  \u09AF\u09BE\u09AA\u09C7\u09B0 \u09AE\u09A7\u09CD\u09AF\u09C7 \u09A1\u09C7\u099F\
  \u09BE\u2026"
title: "XML \u09A8\u09BF\u09AF\u09BC\u09C7 \u0995\u09BE\u099C \u0995\u09B0\u09BE"
---

{{< edit_this_page >}}

## কি এবং কেন?

XML (eXtensible Markup Language) হলো ডেটা সংগঠিত করার একটি পদ্ধতি যা পাঠযোগ্য ফরম্যাটে ডেটা পরিচালনা করে। প্রোগ্রামাররা কনফিগারেশন, অ্যাপের মধ্যে ডেটা বিনিময়, এবং যে স্পেসিফিকেশনগুলি এটি চায় সেগুলোর জন্য XML নিয়ে কাজ করে—যেমন SOAP অথবা ওয়েব API-তে চিন্তা করুন।

## কিভাবে:
```C#
using System;
using System.Xml;
using System.Xml.Linq;

class Program
{
     static void Main()
     {
        var xmlString = @"<bookstore>
                            <book>
                              <title lang=""en"">Head First C#</title>
                              <price>39.99</price>
                            </book>
                          </bookstore>";

        // স্ট্রিংকে XDocument-এ পার্স করুন
        XDocument doc = XDocument.Parse(xmlString);

        // একটি নতুন বই যোগ করুন
        doc.Element("bookstore").Add(
            new XElement("book",
                new XElement("title", "Learning XML", new XAttribute("lang", "en")),
                new XElement("price", 29.99)
            )
        );

        // XML-টি কনসোলে লিখুন
        Console.WriteLine(doc);

        // ডকুমেন্ট লোড করুন
        XmlDocument xmlDoc = new XmlDocument();
        xmlDoc.LoadXml(xmlString);

        // সমস্ত মূল্য উদ্ধার করুন
        XmlNodeList prices = xmlDoc.GetElementsByTagName("price");
        foreach (XmlNode price in prices)
        {
            Console.WriteLine(price.InnerText);
        }
     }
}

// স্যাম্পল আউটপুট:
// <bookstore>
//  <book>
//    <title lang="en">Head First C#</title>
//    <price>39.99</price>
//  </book>
//  <book>
//    <title lang="en">Learning XML</title>
//    <price>29.99</price>
//  </book>
// </bookstore>
// 39.99
// 29.99
```

## গভীরভাবে দেখা
প্রযুক্তির বছরে XML উদ্ভাবিত হয়েছিল নব্বইয়ের দশকে, যা এটিকে প্রযুক্তির দুনিয়ায় একজন দাদা বানিয়ে দেয়। এটি ডেটা পোর্টেবিলিটি এবং মানব পঠনের সুবিধার জন্য উদ্ভাবিত হয়েছিল। এর বিকল্প যেমন JSON এখন এর পায়ে টিপে দাঁড়িয়ে আছে, বিশেষ করে ওয়েব কন্টেক্সটে, কারণ এটি হালকা এবং অনেকের কাছে সহজে পরিচালনার যোগ্য। কিন্তু XML অনেক পুরাতন সিস্টেম এবং নির্দিষ্ট যোগাযোগ প্রটোকলে এখনও তার স্থান ধরে রেখেছে। XML-এর মাধ্যমে, আপনি আপনার কাঠামো যাচাই করার জন্য একটি স্কিমা এবং ট্যাগ সংঘাত এড়ানোর জন্য নামস্থান পান—বৈশিষ্ট্যগুলো এর প্রতিষ্ঠান-প্রস্তুত পরিণতির কথা বলে।

C# এ, `System.Xml.Linq` এবং `System.Xml` নেমস্পেসগুলি XML নিয়ে কাজ করার জন্য দুইটি বড় অস্ত্র। LINQ to XML (`XDocument`, `XElement`) আরও আধুনিক এবং আরও মনোরম—আপনি উদাহরণে এর জাদু দেখেছেন। `XmlDocument` আপনাকে DOM (Document Object Model) পদ্ধতি দেয়—একটু পুরানো স্কুল, কিন্তু কিছু লোক এর শক্তির কথা শপথ করে।

## আরো দেখুন
- [MSDN – LINQ to XML ওভারভিউ](https://docs.microsoft.com/dotnet/standard/linq/linq-xml-overview)
- [MSDN – XML Document Object Model (DOM)](https://docs.microsoft.com/dotnet/standard/data/xml/)
- [W3Schools – XML শিখুন](https://www.w3schools.com/xml/)
- [XML vs. JSON](https://www.json.org/xml.html)
