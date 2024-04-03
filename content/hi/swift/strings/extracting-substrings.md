---
date: 2024-01-20 17:47:12.085096-07:00
description: "\u0909\u092A\u0938\u094D\u091F\u094D\u0930\u093F\u0902\u0917 \u0928\u093F\
  \u0915\u093E\u0932\u0928\u093E \u092E\u0924\u0932\u092C \u0939\u0948 \u092C\u0921\
  \u093C\u0940 \u0938\u094D\u091F\u094D\u0930\u093F\u0902\u0917 \u0938\u0947 \u091B\
  \u094B\u091F\u093E \u0939\u093F\u0938\u094D\u0938\u093E \u092C\u093E\u0939\u0930\
  \ \u0916\u0940\u0902\u091A\u0928\u093E\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\
  \u0930\u093E\u092E\u0930\u094D\u0938 \u0910\u0938\u093E \u0921\u0947\u091F\u093E\
  \ \u0915\u094B \u092A\u094D\u0930\u094B\u0938\u0947\u0938 \u0915\u0930\u0928\u0947\
  , \u091C\u093E\u0928\u0915\u093E\u0930\u0940 \u0928\u093F\u0915\u093E\u0932\u0928\
  \u0947 \u092F\u093E \u0938\u094D\u091F\u094D\u0930\u093F\u0902\u0917 \u0915\u0940\
  \ \u092E\u0928\u091A\u093E\u0939\u0940 \u0936\u0947\u092A \u0926\u0947\u0928\u0947\
  \u2026"
lastmod: '2024-03-13T22:44:52.899148-06:00'
model: gpt-4-1106-preview
summary: "\u0909\u092A\u0938\u094D\u091F\u094D\u0930\u093F\u0902\u0917 \u0928\u093F\
  \u0915\u093E\u0932\u0928\u093E \u092E\u0924\u0932\u092C \u0939\u0948 \u092C\u0921\
  \u093C\u0940 \u0938\u094D\u091F\u094D\u0930\u093F\u0902\u0917 \u0938\u0947 \u091B\
  \u094B\u091F\u093E \u0939\u093F\u0938\u094D\u0938\u093E \u092C\u093E\u0939\u0930\
  \ \u0916\u0940\u0902\u091A\u0928\u093E\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\
  \u0930\u093E\u092E\u0930\u094D\u0938 \u0910\u0938\u093E \u0921\u0947\u091F\u093E\
  \ \u0915\u094B \u092A\u094D\u0930\u094B\u0938\u0947\u0938 \u0915\u0930\u0928\u0947\
  , \u091C\u093E\u0928\u0915\u093E\u0930\u0940 \u0928\u093F\u0915\u093E\u0932\u0928\
  \u0947 \u092F\u093E \u0938\u094D\u091F\u094D\u0930\u093F\u0902\u0917 \u0915\u0940\
  \ \u092E\u0928\u091A\u093E\u0939\u0940 \u0936\u0947\u092A \u0926\u0947\u0928\u0947\
  \ \u0915\u0947 \u0932\u093F\u090F \u0915\u0930\u0924\u0947 \u0939\u0948\u0902\u0964\
  ."
title: "\u0938\u092C\u0938\u094D\u091F\u094D\u0930\u093F\u0902\u0917\u094D\u0938 \u0928\
  \u093F\u0915\u093E\u0932\u0928\u093E"
weight: 6
---

## How to: (कैसे करें:)
```Swift
let fullString = "Hello, Swift Programmers!"
let startIndex = fullString.index(fullString.startIndex, offsetBy: 7)
let endIndex = fullString.index(fullString.endIndex, offsetBy: -12)
let range = startIndex..<endIndex

// उपस्ट्रिंग निकालना
let substring = fullString[range]  // "Swift"

// उदाहरण आउटपुट
print(substring)  // "Swift"
```

## Deep Dive (गहराई से जानकारी):
जब हम स्ट्रिंग के पुराने तरीकों में देखते हैं, तो सबस्ट्रिंग्स को निकालने के लिए बहुत सिंपल API उपयोग होते थे, जैसे `substringWithRange:`। स्विफ्ट ने यह बदल दिया है और अब `String.Index` प्रकार का इस्तेमाल होता है, जो कि जटिल लग सकता है लेकिन यह स्ट्रिंग में यूनिकोड स्कैलर वैल्यूज को सही तरीके से हैंडल करता है। इससे मल्टीबाइट यूनिकोड करैक्टर्स के साथ काम करते समय एरर्स से बचा जा सकता है।

विकल्प के रूप में, रेगेक्स (regex) या अन्य बिल्ट-इन स्ट्रिंग फंक्शंस भी हैं जो स्पेसिफिक पैटर्न्स या डिलिमिटर्स के जरिए सबस्ट्रिंग्स निकालने में उपयोगी होते हैं।

## See Also (और जानकारी के लिए:)
- आधिकारिक स्विफ्ट डॉक्यूमेंटेशन: [String and Characters](https://docs.swift.org/swift-book/LanguageGuide/StringsAndCharacters.html)
- Swift में स्ट्रिंग ऑपरेशंस: [Swift String Cheat Sheet](https://www.hackingwithswift.com/example-code/strings)
- यूनिकोड प्रोसेसिंग: [Swift’s String and Character API](https://oleb.net/blog/2017/11/swift-4-strings/)
