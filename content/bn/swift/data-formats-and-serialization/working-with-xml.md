---
changelog:
- 2024-03-17, gpt-4-0125-preview, translated from English
date: 2024-03-17 18:35:56.120095-06:00
description: "Swift-\u098F XML-\u098F\u09B0 \u09B8\u09BE\u09A5\u09C7 \u0995\u09BE\u099C\
  \ \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\u09C7 XML \u09A1\u09C7\u099F\u09BE \u09AA\
  \u09BE\u09B0\u09CD\u09B8 \u0995\u09B0\u09BE \u098F\u09AC\u0982 \u099C\u09C7\u09A8\
  \u09BE\u09B0\u09C7\u099F \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\
  \u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u098F\u099F\u09BE \u09A1\u09C7\
  \u099F\u09BE \u0986\u09A6\u09BE\u09A8-\u09AA\u09CD\u09B0\u09A6\u09BE\u09A8\u09C7\
  \u09B0 \u099C\u09A8\u09CD\u09AF \u0995\u09B0\u09C7, \u09AC\u09BF\u09B6\u09C7\u09B7\
  \ \u0995\u09B0\u09C7 \u09AF\u0996\u09A8 \u09A4\u09BE\u09B0\u09BE \u09B8\u09C7\u0987\
  \ \u09B8\u09BF\u09B8\u09CD\u099F\u09C7\u09AE\u09C7\u09B0 \u09B8\u09BE\u09A5\u09C7\
  \u2026"
lastmod: '2024-03-17T18:47:44.434383-06:00'
model: gpt-4-0125-preview
summary: "Swift-\u098F XML-\u098F\u09B0 \u09B8\u09BE\u09A5\u09C7 \u0995\u09BE\u099C\
  \ \u0995\u09B0\u09BE \u09AE\u09BE\u09A8\u09C7 XML \u09A1\u09C7\u099F\u09BE \u09AA\
  \u09BE\u09B0\u09CD\u09B8 \u0995\u09B0\u09BE \u098F\u09AC\u0982 \u099C\u09C7\u09A8\
  \u09BE\u09B0\u09C7\u099F \u0995\u09B0\u09BE\u0964 \u09AA\u09CD\u09B0\u09CB\u0997\
  \u09CD\u09B0\u09BE\u09AE\u09BE\u09B0\u09B0\u09BE \u098F\u099F\u09BE \u09A1\u09C7\
  \u099F\u09BE \u0986\u09A6\u09BE\u09A8-\u09AA\u09CD\u09B0\u09A6\u09BE\u09A8\u09C7\
  \u09B0 \u099C\u09A8\u09CD\u09AF \u0995\u09B0\u09C7, \u09AC\u09BF\u09B6\u09C7\u09B7\
  \ \u0995\u09B0\u09C7 \u09AF\u0996\u09A8 \u09A4\u09BE\u09B0\u09BE \u09B8\u09C7\u0987\
  \ \u09B8\u09BF\u09B8\u09CD\u099F\u09C7\u09AE\u09C7\u09B0 \u09B8\u09BE\u09A5\u09C7\
  \ \u0987\u09A8\u09CD\u099F\u09BF\u0997\u09CD\u09B0\u09C7\u099F \u0995\u09B0\u09C7\
  \ \u09AF\u09C7\u0996\u09BE\u09A8\u09C7 XML \u09B8\u09CD\u099F\u09CD\u09AF\u09BE\u09A8\
  \u09CD\u09A1\u09BE\u09B0\u09CD\u09A1 \u09AB\u09B0\u09AE\u09CD\u09AF\u09BE\u099F\u0964\
  ."
title: "XML \u098F\u09B0 \u09B8\u09BE\u09A5\u09C7 \u0995\u09BE\u099C \u0995\u09B0\u09BE"
weight: 40
---

## কিভাবে:
Swift XML ডেটা পার্স করার জন্য `XMLParser` এবং `XMLDocument` প্রদান করে। এখানে একটি সন্নিবেশ রয়েছে যা একটি সিম্পল XML string পার্স করে:

```swift
import Foundation

let xmlString = """
<?xml version="1.0" encoding="UTF-8"?>
<note>
    <to>Tove</to>
    <from>Jani</from>
    <heading>Reminder</heading>
    <body>Don't forget the party on Friday!</body>
</note>
"""

if let xmlData = xmlString.data(using: .utf8) {
    let parser = XMLParser(data: xmlData)
    parser.delegate = someParserDelegate // আপনার XMLParserDelegate
    parser.parse()
}
```

আপনি `XMLDocument` ব্যবহার করে XML জেনারেটও করতে পারেন:

```swift
import Foundation

let note = XMLElement(name: "note")
let to = XMLElement(name: "to", stringValue: "Tove")
note.addChild(to)
let xmlDoc = XMLDocument(rootElement: note)

print(xmlDoc.xmlString(options: .nodePrettyPrint))
```

নমুনা আউটপুট:

```xml
<note>
  <to>Tove</to>
</note>
```

## গভীরে যাওয়া
XML, বা Extensible Markup Language, '90-এর দশকের শেষ থেকে আছে। এটি বৃবৎ কিন্তু মানব-পাঠ্যযোগ্য, যা এটিকে জটিল ডেটা কাঠামোর জন্য উপযোগী করে তোলে। Swift-এর XML পারসিং ক্ষমতা Python-এর ElementTree বা Java-এর JAXB এর মত বিস্তৃত না হলেও, বেসিক প্রয়োজনের জন্য তা কাজ করে।

নতুন সিস্টেমে JSON মত বিকল্পগুলি তাদের লাইটওয়েট এবং কম জটিল পারসারের জন্য প্রায়ই প্রাধান্য পায়, কিন্তু XML অনেক এন্টারপ্রাইজ এবং লেগাসি সিস্টেমে এখনো প্রমিনেন্ট।

Swift-এ XML-এর সাথে কাজ করার সময়, `XMLParser` একটি স্ট্রিম-ভিত্তিক পার্সার যার মানে এটি XML ডকুমেন্টের মাধ্যমে ক্রমান্বয়ভাবে পড়ে। বড় XML ফাইলগুলির জন্য, এটি মেমরি-দক্ষ। তবে, যদি আপনি সাধারণতা খুঁজছেন এবং আপনার XML ডেটা যুক্তিসঙ্গত ছোট হয়, তাহলে `XMLDocument` ব্যবহার করা আরও সোজা হতে পারে।

## আরও দেখুন
- [Apple-এর XML Parsing Guide](https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/XMLParsing/XMLParsing.html)
- [W3Schools XML টিউটোরিয়াল](https://www.w3schools.com/xml/)
