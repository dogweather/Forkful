---
aliases:
- /hi/clojure/working-with-yaml/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:25:29.782610-07:00
description: "YAML, \u091C\u093F\u0938\u0915\u093E \u092A\u0942\u0930\u093E \u0928\
  \u093E\u092E \"YAML Ain't Markup Language\" \u0939\u0948, \u090F\u0915 \u092E\u093E\
  \u0928\u0935-\u092A\u0920\u0928\u0940\u092F \u0921\u0947\u091F\u093E \u0938\u0940\
  \u0930\u093F\u092F\u0932\u093E\u0907\u091C\u0947\u0936\u0928 \u092A\u094D\u0930\u093E\
  \u0930\u0942\u092A \u0939\u0948 \u091C\u093F\u0938\u0915\u093E \u0909\u092A\u092F\
  \u094B\u0917 \u0915\u0949\u0928\u094D\u092B\u093C\u093F\u0917\u0930\u0947\u0936\u0928\
  \ \u092B\u093C\u093E\u0907\u0932\u094B\u0902 \u0914\u0930 \u092D\u093F\u0928\u094D\
  \u0928 \u0921\u0947\u091F\u093E \u0938\u0902\u0930\u091A\u0928\u093E\u2026"
lastmod: 2024-02-18 23:09:02.762616
model: gpt-4-0125-preview
summary: "YAML, \u091C\u093F\u0938\u0915\u093E \u092A\u0942\u0930\u093E \u0928\u093E\
  \u092E \"YAML Ain't Markup Language\" \u0939\u0948, \u090F\u0915 \u092E\u093E\u0928\
  \u0935-\u092A\u0920\u0928\u0940\u092F \u0921\u0947\u091F\u093E \u0938\u0940\u0930\
  \u093F\u092F\u0932\u093E\u0907\u091C\u0947\u0936\u0928 \u092A\u094D\u0930\u093E\u0930\
  \u0942\u092A \u0939\u0948 \u091C\u093F\u0938\u0915\u093E \u0909\u092A\u092F\u094B\
  \u0917 \u0915\u0949\u0928\u094D\u092B\u093C\u093F\u0917\u0930\u0947\u0936\u0928\
  \ \u092B\u093C\u093E\u0907\u0932\u094B\u0902 \u0914\u0930 \u092D\u093F\u0928\u094D\
  \u0928 \u0921\u0947\u091F\u093E \u0938\u0902\u0930\u091A\u0928\u093E\u2026"
title: "YAML \u0915\u0947 \u0938\u093E\u0925 \u0915\u093E\u092E \u0915\u0930\u0928\
  \u093E"
---

{{< edit_this_page >}}

## क्या और क्यों?

YAML, जिसका पूरा नाम "YAML Ain't Markup Language" है, एक मानव-पठनीय डेटा सीरियलाइजेशन प्रारूप है जिसका उपयोग कॉन्फ़िगरेशन फ़ाइलों और भिन्न डेटा संरचना वाली भाषाओं के बीच डेटा आदान-प्रदान के लिए किया जाता है। प्रोग्रामर YAML का उपयोग इसकी सादगी और पठनीयता के कारण करते हैं, जिससे यह एप्लिकेशन को कॉन्फ़िगर करने और पॉलीग्लॉट प्रोग्रामिंग वातावरणों में डेटा आदान-प्रदान की सुविधा देने के लिए एक आदर्श विकल्प बनता है।

## कैसे:

Clojure में YAML के लिए बनाई गई सहायता शामिल नहीं है, लेकिन आप `clj-yaml` जैसी तीसरे पक्ष की लाइब्रेरीज का उपयोग करके YAML डेटा का पार्सिंग और जेनरेशन कर सकते हैं। सबसे पहले, अपनी परियोजना निर्भरताओं में लाइब्रेरी जोड़ें:

```clojure
;; इसे अपनी project.clj निर्भरताओं में जोड़ें
[clj-yaml "0.7.0"]
```

यहाँ बताया गया है कि आप YAML का पार्सिंग कैसे कर सकते हैं और Clojure मैप्स को YAML में कैसे बदल सकते हैं।

### YAML पार्सिंग:

```clojure
(require '[clj-yaml.core :as yaml])

;; एक YAML स्ट्रिंग का पार्सिंग
(let [yaml-str "name: John Doe\nage: 30\nlanguages:\n  - Clojure\n  - Python"]
  (yaml/parse-string yaml-str))
;; आउटपुट:
;; => {"name" "John Doe", "age" 30, "languages" ["Clojure" "Python"]}
```

### Clojure से YAML जेनरेट करना:

```clojure
(require '[clj-yaml.core :as yaml])

;; एक Clojure मैप को YAML स्ट्रिंग में बदलना
(let [data-map {:name "Jane Doe" :age 28 :languages ["Java" "Ruby"]}]
  (yaml/generate-string data-map))
;; आउटपुट:
; "age: 28\nlanguages:\n- Java\n- Ruby\nname: Jane Doe\n"
```

`clj-yaml` के साथ ये साधारण कार्यवाहियाँ Clojure एप्लिकेशंस में एकीकृत की जा सकती हैं ताकि कॉन्फ़िगरेशन फ़ाइलों को संभाला जा सके या उन सेवाओं या घटकों के साथ डेटा आदान-प्रदान की सुविधा हो सके जो YAML का उपयोग करते हैं।
