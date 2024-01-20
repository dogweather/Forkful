---
title:                "यादृच्छिक संख्याओं का निर्माण"
html_title:           "Clojure: यादृच्छिक संख्याओं का निर्माण"
simple_title:         "यादृच्छिक संख्याओं का निर्माण"
programming_language: "Elixir"
category:             "Elixir"
tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/elixir/generating-random-numbers.md"
---

{{< edit_this_page >}}

## क्या और क्यों? 

यादृच्छिक संख्याएं उत्पन्न करना का अर्थ है किसी आकड़े को बिना किसी पूर्वग्रह के चुनना। प्रोग्रामर इसे करते हैं क्योंकि इससे परीक्षण, गेम डिजाइन और आईवीए की सहायता मिलती है।

## कैसे करें:

यहां यादृच्चिक संख्या उत्पन्न करने का उदाहरण है:

```elixir
Enum.random(1..6) 
```

इसकी आउटपुट 1 से 6 के बीच की कोई भी यादृच्चिक संख्या हो सकती है।

```elixir
Enum.random([:spades, :clubs, :hearts, :diamonds])
```

इसकी आउटपुट चार रंगों में से कोई एक होगा।

## गहन जानकारी:

लेखनिक डॉक्टर जॉन वॉन न्यूमैन ने 1946 में सबसे पहला यादृच्छिक संख्या उत्पन्न करने वाला एल्गोरिदम विकसित किया था। इलिक्सिर में रैंडम मॉड्यूल इसे सरल बनाता है, लेकिन इसके अलावा भी तरीके हैं। कई बार हम यदि संख्या दोहरानी हो तो `StreamData` मॉड्यूल का उपयोग कर सकते हैं। यह पूर्णतया उत्पन्न संख्याओं पर विशेषता प्रदर्शित करता है। 

## आगे देखें:

अधिक जानकारी के लिए, निम्नलिखित स्रोतों का अन्वेषण करें:

- [इलिक्सिर प्रलेखन](https://hexdocs.pm/elixir/Enum.html#random/1) 
- [Random number generation (संख्या उत्पन्न करने की क्रिया)](https://en.wikipedia.org/wiki/Random_number_generation)
- [StreamData डॉक्यूमेंटेशन](https://github.com/elixir-lang/stream_data)