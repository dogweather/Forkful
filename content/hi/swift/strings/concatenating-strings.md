---
aliases:
- /hi/swift/concatenating-strings/
date: 2024-01-20 17:36:25.560326-07:00
description: "\u0938\u094D\u091F\u094D\u0930\u093F\u0902\u0917\u094D\u0938 \u0915\u093E\
  \ \u091C\u094B\u0921\u093C Concatenating strings \u0939\u094B\u0924\u093E \u0939\
  \u0948 \u091C\u092C \u0939\u092E \u0926\u094B \u092F\u093E \u0909\u0938\u0938\u0947\
  \ \u091C\u094D\u092F\u093E\u0926\u093E \u091F\u0947\u0915\u094D\u0938\u094D\u091F\
  \ \u092A\u0940\u0938\u0947\u091C \u0915\u094B \u090F\u0915 \u0938\u093E\u0925 \u091C\
  \u094B\u0921\u093C\u0924\u0947 \u0939\u0948\u0902\u0964 \u092A\u094D\u0930\u094B\
  \u0917\u094D\u0930\u093E\u092E\u0930\u094D\u0938 \u092F\u0939 \u0907\u0938\u0932\
  \u093F\u090F \u0915\u0930\u0924\u0947 \u0939\u0948\u0902 \u0924\u093E\u0915\u093F\
  \ \u0935\u0947\u2026"
lastmod: 2024-02-18 23:09:03.952571
model: gpt-4-1106-preview
summary: "\u0938\u094D\u091F\u094D\u0930\u093F\u0902\u0917\u094D\u0938 \u0915\u093E\
  \ \u091C\u094B\u0921\u093C Concatenating strings \u0939\u094B\u0924\u093E \u0939\
  \u0948 \u091C\u092C \u0939\u092E \u0926\u094B \u092F\u093E \u0909\u0938\u0938\u0947\
  \ \u091C\u094D\u092F\u093E\u0926\u093E \u091F\u0947\u0915\u094D\u0938\u094D\u091F\
  \ \u092A\u0940\u0938\u0947\u091C \u0915\u094B \u090F\u0915 \u0938\u093E\u0925 \u091C\
  \u094B\u0921\u093C\u0924\u0947 \u0939\u0948\u0902\u0964 \u092A\u094D\u0930\u094B\
  \u0917\u094D\u0930\u093E\u092E\u0930\u094D\u0938 \u092F\u0939 \u0907\u0938\u0932\
  \u093F\u090F \u0915\u0930\u0924\u0947 \u0939\u0948\u0902 \u0924\u093E\u0915\u093F\
  \ \u0935\u0947\u2026"
title: "\u0938\u094D\u091F\u094D\u0930\u093F\u0902\u0917 \u0915\u094B \u091C\u094B\
  \u0921\u093C\u0928\u093E"
---

{{< edit_this_page >}}

## What & Why? (क्या और क्यों?)
स्ट्रिंग्स का जोड़ Concatenating strings होता है जब हम दो या उससे ज्यादा टेक्स्ट पीसेज को एक साथ जोड़ते हैं। प्रोग्रामर्स यह इसलिए करते हैं ताकि वे वेरिएबल्स, यूज़र इनपुट, और स्टेटिक टेक्स्ट को एक सिंगल स्ट्रिंग में मर्ज कर सकें।

## How to (कैसे करें):
Swift में स्ट्रिंग्स जोड़ते वक़्त आप `+` ओपरेटर या `\()` सिंटेक्स का इस्तेमाल कर सकते हैं। उदाहरण देखिए:

```Swift
// स्ट्रिंग्स को '+' ओपरेटर से जोड़ना
let greeting = "नमस्ते, "
let name = "विवेक!"
let welcomeMessage = greeting + name
print(welcomeMessage) // आउटपुट: नमस्ते, विवेक!

// String interpolation का इस्तेमाल करते हुए
let age = 30
let introduction = "मेरा नाम \(name) है और मेरी उम्र \(age) साल है।"
print(introduction) // आउटपुट: मेरा नाम विवेक! है और मेरी उम्र 30 साल है।
```

## Deep Dive (गहन जानकारी):
पुराने दिनों में, स्ट्रिंग्स जोड़ना ज्यादा जटिल होता था और परफॉर्मेंस के मुद्दे होते थे। Swift के आ जाने के बाद, स्ट्रिंग हैंडलिंग सुधर गई और और भी आसान बन गई। 

स्ट्रिंग Concatenation के अलावा, आप `append()` का इस्तेमाल कर सकते हैं जो मौजूदा स्ट्रिंग में एक और स्ट्रिंग जोड़ देता है। पर, जब बड़े डेटा सेट के साथ काम करते हैं, तब `joined()` या `StringBuilder` जैसी क्लासेज ज्यादा परफॉर्मेंट होती हैं। स्ट्रिंग्स को जोड़ते समय मेमोरी आवंटन को ठीक से मैनेज करना जरूरी होता है। 

## See Also (और जानें):
- [Swift Documentation on Strings and Characters](https://docs.swift.org/swift-book/LanguageGuide/StringsAndCharacters.html)
- [Swift API Reference for String](https://developer.apple.com/documentation/swift/string)
- [Ray Wenderlich String Concatenation in Swift](https://www.raywenderlich.com/)
  
इन लिंक्स पर जाकर आप स्ट्रिंग्स के बारे में और गहराई से जान सकते हैं, उनके मेथड्स के बारे में पढ़ सकते हैं, और प्रैक्टिकल एक्जाम्पल के जरिए सीख सकते हैं।
