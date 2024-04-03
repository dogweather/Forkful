---
date: 2024-01-20 17:54:29.021279-07:00
description: "\u092A\u093E\u0920 \u092B\u093C\u093E\u0907\u0932 \u0915\u094B \u092A\
  \u0922\u093C\u0928\u093E \u092F\u093E\u0928\u093F \u092B\u093C\u093E\u0907\u0932\
  \ \u0938\u0947 \u0921\u0947\u091F\u093E \u090F\u0915\u0924\u094D\u0930 \u0915\u0930\
  \u0928\u093E \u0939\u094B\u0924\u093E \u0939\u0948\u0964 \u092A\u094D\u0930\u094B\
  \u0917\u094D\u0930\u093E\u092E\u0930\u094D\u0938 \u092F\u0939 \u0905\u0915\u0938\
  \u0930 \u090F\u092A\u094D\u0932\u093F\u0915\u0947\u0936\u0928 \u0915\u094B \u091C\
  \u0930\u0941\u0930\u0940 \u0938\u0942\u091A\u0928\u093E\u090F\u0902 \u0926\u0947\
  \u0928\u0947 \u092F\u093E \u0932\u0949\u0917\u094D\u0938 \u0915\u094B \u092A\u094D\
  \u0930\u094B\u0938\u0947\u0938 \u0915\u0930\u0928\u0947 \u0915\u0947 \u0932\u093F\
  \u090F \u0915\u0930\u0924\u0947 \u0939\u0948\u0902\u0964"
lastmod: '2024-03-13T22:44:52.434891-06:00'
model: gpt-4-1106-preview
summary: "\u092A\u093E\u0920 \u092B\u093C\u093E\u0907\u0932 \u0915\u094B \u092A\u0922\
  \u093C\u0928\u093E \u092F\u093E\u0928\u093F \u092B\u093C\u093E\u0907\u0932 \u0938\
  \u0947 \u0921\u0947\u091F\u093E \u090F\u0915\u0924\u094D\u0930 \u0915\u0930\u0928\
  \u093E \u0939\u094B\u0924\u093E \u0939\u0948\u0964 \u092A\u094D\u0930\u094B\u0917\
  \u094D\u0930\u093E\u092E\u0930\u094D\u0938 \u092F\u0939 \u0905\u0915\u0938\u0930\
  \ \u090F\u092A\u094D\u0932\u093F\u0915\u0947\u0936\u0928 \u0915\u094B \u091C\u0930\
  \u0941\u0930\u0940 \u0938\u0942\u091A\u0928\u093E\u090F\u0902 \u0926\u0947\u0928\
  \u0947 \u092F\u093E \u0932\u0949\u0917\u094D\u0938 \u0915\u094B \u092A\u094D\u0930\
  \u094B\u0938\u0947\u0938 \u0915\u0930\u0928\u0947 \u0915\u0947 \u0932\u093F\u090F\
  \ \u0915\u0930\u0924\u0947 \u0939\u0948\u0902\u0964."
title: "\u091F\u0947\u0915\u094D\u0938\u094D\u091F \u092B\u093C\u093E\u0907\u0932\
  \ \u092A\u0922\u093C\u0928\u093E"
weight: 22
---

## How to: (कैसे:)
Haskell में पाठ फ़ाइल पढ़ना सीधा है:

```Haskell
import System.IO

main :: IO ()
main = do
    contents <- readFile "hello.txt"
    putStrLn contents
```

जब `hello.txt` में `"Hello, Haskell!"` होगा, आउटपुट होगा:

```
Hello, Haskell!
```

## Deep Dive (गहराई से जानकारी)
पाठ फ़ाइलों को पढ़ना आरंभिक कंप्यूटिंग युग से है। Haskell में, `readFile` एक लेज़ी फंक्शन है जो फ़ाइल को धीरे-धीरे पढ़ता है जब जरुरत होती है। वैकल्पिक तरीके में `Data.ByteString` लाइब्रेरी फ़ाइल को बाइनरी फॉर्म में पढ़ती है, जो बड़े डेटा के लिए उपयुक्त हो सकती है।

सावधानी: `readFile` को `System.IO` मॉड्यूल से इम्पोर्ट करना जरुरी है, और फ़ाइल की पाठ्य सामग्री को संभालने में ठीक एरर हैंडलिंग की आवश्यकता होती है।

## See Also (अधिक जानकारी के लिए)
- Haskell डॉक्स: [System.IO Module](https://hackage.haskell.org/package/base-4.16.1.0/docs/System-IO.html)
- Learn You a Haskell गाइड: [Input and Output chapter](http://learnyouahaskell.com/input-and-output)
- Real World Haskell पुस्तक: [Working with Files and Streams](http://book.realworldhaskell.org/read/io.html)
