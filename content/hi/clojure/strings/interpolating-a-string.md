---
date: 2024-01-20 17:50:38.283930-07:00
description: "\u0938\u094D\u091F\u094D\u0930\u093F\u0902\u0917 \u0907\u0902\u091F\u0930\
  \u092A\u094B\u0932\u0947\u0936\u0928 \u0938\u0947 \u0906\u0936\u092F \u0935\u0947\
  \u0930\u093F\u090F\u092C\u0932\u094D\u0938 \u0914\u0930 \u090F\u0915\u094D\u0938\
  \u092A\u094D\u0930\u0947\u0936\u0928\u094D\u0938 \u0915\u094B \u0938\u094D\u091F\
  \u094D\u0930\u093F\u0902\u0917 \u0915\u0947 \u0905\u0902\u0926\u0930 \u0938\u0940\
  \u0927\u0947 \u0921\u093E\u0932\u0928\u0947 \u0938\u0947 \u0939\u0948. \u092F\u0947\
  \ \u0924\u0915\u0928\u0940\u0915 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\
  \u092E\u0930\u094D\u0938 \u0915\u094B \u0915\u094B\u0921 \u0915\u094B \u0914\u0930\
  \ \u092A\u0920\u0928\u0940\u092F \u0914\u0930 \u092E\u0947\u0902\u091F\u0947\u0928\
  \ \u0915\u0930\u0928\u0947 \u092E\u0947\u0902\u2026"
lastmod: '2024-03-13T22:44:51.639217-06:00'
model: gpt-4-1106-preview
summary: "\u0938\u094D\u091F\u094D\u0930\u093F\u0902\u0917 \u0907\u0902\u091F\u0930\
  \u092A\u094B\u0932\u0947\u0936\u0928 \u0938\u0947 \u0906\u0936\u092F \u0935\u0947\
  \u0930\u093F\u090F\u092C\u0932\u094D\u0938 \u0914\u0930 \u090F\u0915\u094D\u0938\
  \u092A\u094D\u0930\u0947\u0936\u0928\u094D\u0938 \u0915\u094B \u0938\u094D\u091F\
  \u094D\u0930\u093F\u0902\u0917 \u0915\u0947 \u0905\u0902\u0926\u0930 \u0938\u0940\
  \u0927\u0947 \u0921\u093E\u0932\u0928\u0947 \u0938\u0947 \u0939\u0948."
title: "\u0938\u094D\u091F\u094D\u0930\u093F\u0902\u0917 \u0907\u0902\u091F\u0930\u092A\
  \u094B\u0932\u0947\u0936\u0928"
weight: 8
---

## How to: (कैसे करें)
```Clojure
;; स्ट्रिंग इंटरपोलेशन का उपयोग कैसे करें

;; clojure.core/str का उपयोग करके
(def name "विश्वजीत")
(def message (str "Hello, " name "! कैसे हैं आप?"))
(println message) ; आउटपुट: Hello, विश्वजीत! कैसे हैं आप?

;; format फंक्शन का उपयोग करके
(def message (format "Hello, %s! कैसे हैं आप?" name))
(println message) ; आउटपुट: Hello, विश्वजीत! कैसे हैं आप?
```

## Deep Dive (गहराई से जानकारी)
स्ट्रिंग इंटरपोलेशन का विचार नया नहीं है; यह कई प्रोग्रामिंग भाषाओं में सदियों से उपयोग हो रहा है. इसके विपरीत, Clojure में अन्य भाषाओं की तरह बिल्ट-इन स्ट्रिंग इंटरपोलेशन नहीं होता है. हम clojure.core/str या format जैसे फंक्शन्स का उपयोग करके इसे हासिल कर सकते हैं.

Clojure में एक और विकल्प `clojure.pprint/cl-format` होता है, जो अधिक जटिल फॉर्मेटिंग ऑपरेशन्स को सपोर्ट करता है, लेकिन यह शुरुआती के लिए कठिन हो सकता है.

कई क्लोजर लाइब्रेरीज जैसे कि `hiccup` वेब टेम्प्लेटिंग में स्ट्रिंग इंटरपोलेशन का उपयोग करती हैं.

## See Also (और देखें)
- Clojure `str` documentation: [str | Clojure Docs](https://clojuredocs.org/clojure.core/str)
- Clojure `format` documentation: [format | Clojure Docs](https://clojuredocs.org/clojure.core/format)
- `clojure.pprint/cl-format` for advanced formatting: [cl-format | Clojure Pretty Print](https://clojuredocs.org/clojure.pprint/cl-format)
