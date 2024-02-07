---
title:                "पैटर्न से मेल खाते अक्षरों को हटाना"
date:                  2024-01-20T17:42:04.814908-07:00
model:                 gpt-4-1106-preview
simple_title:         "पैटर्न से मेल खाते अक्षरों को हटाना"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/clojure/deleting-characters-matching-a-pattern.md"
---

{{< edit_this_page >}}

## What & Why? (क्या और क्यों?)
पैटर्न से मिलते चरित्रों को हटाना एक प्रक्रिया है जहाँ हम एक निश्चित पैटर्न के अनुरूप आने वाले चरित्रों को एक स्ट्रिंग से निकाल देते हैं। प्रोग्रामर्स इसे डाटा सफाई, फॉर्मेटिंग, या अनवांटेड डाटा को हटाने के लिए करते हैं।

## How to: (कैसे करें:)

Clojure में, हम `re-seq`, `re-find`, `clojure.string/replace` जैसे फंक्शंस का उपयोग कर पैटर्न से मिलते चरित्रों को आसानी से हटा सकते हैं।

```clojure
; संख्याओं को हटाना
(clojure.string/replace "Clojure123" #"\d+" "")
; Output: "Clojure"

; विशेष चरित्रों को हटाना
(clojure.string/replace "Hello, World!" #"[^\w\s]" "")
; Output: "Hello World"

; बड़े / छोटे अक्षरों को हटाना
(clojure.string/replace "Clojure Programming" #"[A-Z]" "")
; Output: "lojure rogramming"
```

## Deep Dive (गहराई में जानकारी):

चरित्र हटाने के लिए RegEx (Regular Expressions) का इस्तेमाल पुराने समय से ही हो रहा है। Clojure भी JVM (Java Virtual Machine) आधारित होने के कारण Java के RegEx इंजन का उपयोग करता है।

1. Historical context: RegEx प्रोसेसिंग अन्य प्रोग्रामिंग भाषाओं में भी मिलती है, और यह टेक्स्ट प्रोसेसिंग के सबसे शक्तिशाली टूल्स में से एक है।
2. Alternatives: कुछ केसेस में `string/split`, `filter`, या `remove` जैसे कोर फंक्शंस से भी पैटर्न हटाना संभव है, लेकिन वे RegEx की तुलना में कम लचीले होते हैं।
3. Implementation details: Clojure में `re-pattern` फंक्शन का प्रयोग कर कस्टम RegEx पैटर्न्स बनाए जा सकते हैं, और `re-matcher`, `re-matches`, `re-groups` जैसे फंक्शंस के साथ काम किया जा सकता है।

## See Also (इसे भी देखें):

- Clojure के आधिकारिक डाक्यूमेंटेशन में [Regular Expressions](https://clojure.org/guides/learn/functions#_regular_expressions) सेक्शन
- [ClojureDocs](https://clojuredocs.org/) पर `clojure.string/replace`
- [Brave Clojure](https://www.braveclojure.com/) पर RegEx पर अधिकः जानकारी
