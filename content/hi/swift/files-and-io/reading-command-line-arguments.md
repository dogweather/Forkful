---
aliases:
- /hi/swift/reading-command-line-arguments/
date: 2024-01-20 17:57:11.512780-07:00
description: "\u0915\u092E\u093E\u0902\u0921 \u0932\u093E\u0907\u0928 \u0905\u0930\
  \u094D\u0917\u094D\u092F\u0942\u092E\u0947\u0902\u091F\u094D\u0938 \u092A\u095D\u0928\
  \u093E \u092F\u093E\u0928\u0940 \u092F\u0942\u091C\u0930 \u0938\u0947 \u0938\u0940\
  \u0927\u0947 \u0907\u0928\u092A\u0941\u091F \u0932\u0947\u0928\u093E \u0939\u094B\
  \u0924\u093E \u0939\u0948 \u091C\u092C \u092A\u094D\u0930\u094B\u0917\u094D\u0930\
  \u093E\u092E \u091A\u0932 \u0930\u0939\u093E \u0939\u094B\u0964 \u092A\u094D\u0930\
  \u094B\u0917\u094D\u0930\u093E\u092E\u0930\u094D\u0938 \u092F\u0939 \u0915\u0930\
  \u0924\u0947 \u0939\u0948\u0902 \u0924\u093E\u0915\u093F \u0909\u0928\u0915\u0947\
  \ \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E \u092B\u094D\u0932\u0947\
  \u0915\u094D\u0938\u093F\u092C\u0932 \u0914\u0930\u2026"
lastmod: 2024-02-18 23:09:03.995965
model: gpt-4-1106-preview
summary: "\u0915\u092E\u093E\u0902\u0921 \u0932\u093E\u0907\u0928 \u0905\u0930\u094D\
  \u0917\u094D\u092F\u0942\u092E\u0947\u0902\u091F\u094D\u0938 \u092A\u095D\u0928\u093E\
  \ \u092F\u093E\u0928\u0940 \u092F\u0942\u091C\u0930 \u0938\u0947 \u0938\u0940\u0927\
  \u0947 \u0907\u0928\u092A\u0941\u091F \u0932\u0947\u0928\u093E \u0939\u094B\u0924\
  \u093E \u0939\u0948 \u091C\u092C \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\
  \u092E \u091A\u0932 \u0930\u0939\u093E \u0939\u094B\u0964 \u092A\u094D\u0930\u094B\
  \u0917\u094D\u0930\u093E\u092E\u0930\u094D\u0938 \u092F\u0939 \u0915\u0930\u0924\
  \u0947 \u0939\u0948\u0902 \u0924\u093E\u0915\u093F \u0909\u0928\u0915\u0947 \u092A\
  \u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E \u092B\u094D\u0932\u0947\u0915\u094D\
  \u0938\u093F\u092C\u0932 \u0914\u0930\u2026"
title: "\u0915\u092E\u093E\u0902\u0921 \u0932\u093E\u0907\u0928 \u0906\u0930\u094D\
  \u0917\u0941\u092E\u0947\u0902\u091F\u094D\u0938 \u092A\u0922\u093C\u0928\u093E"
---

{{< edit_this_page >}}

## What & Why? (क्या और क्यों?)
कमांड लाइन अर्ग्यूमेंट्स पढ़ना यानी यूजर से सीधे इनपुट लेना होता है जब प्रोग्राम चल रहा हो। प्रोग्रामर्स यह करते हैं ताकि उनके प्रोग्राम फ्लेक्सिबल और इंटरैक्टिव हों।

## How to: (कैसे करें:)
```Swift
// main.swift
// सिम्पल कोड जो कमांड लाइन अर्ग्यूमेंट्स डिस्प्ले करता है

// CommandLine.arguments में सभी अर्ग्यूमेंट्स स्टोर होते हैं
for argument in CommandLine.arguments {
    print(argument)
}

// सैंपल आउटपुट:
// प्रोग्राम ./myProgram को चलाएं जिसके साथ कुछ अर्ग्यूमेंट्स दें: 
// ./myProgram Hello World!
// आउटपुट होगा:
// ./myProgram
// Hello 
// World!
```

## Deep Dive (गहराई में जानकारी):
कमांड लाइन अर्ग्यूमेंट्स का इस्तेमाल 1960s के शुरुआती कम्प्यूटर इंटरफेस से हो रहा है। Swift में `CommandLine` की एक बिल्ट-इन क्लास है, जो इसमें सहायता करती है। इसके बदले में, आप Swift Argument Parser लाइब्रेरी का भी इस्तेमाल कर सकते हो, जिससे कोड और भी स्ट्रक्चर्ड और आसान हो जाता है। Command Line Arguments को पढ़ते समय इम्प्लीमेंटेशन डिटेल्स जैसे कि इनपुट वैलिडेशन, इंडेक्सिंग एरर्स और सिक्योरिटी कॉन्सिडरेशन्स ध्यान में रखने जरूरी होते हैं।

## See Also (सम्बंधित स्रोत):
- [Swift.org Command Line Tool Documentation](https://swift.org/package-manager/#example-usage)
- [GitHub Swift Argument Parser](https://github.com/apple/swift-argument-parser)
- [Ray Wenderlich CommandLine Tutorial](https://www.raywenderlich.com/511-command-line-programs-on-macos-tutorial)
