---
aliases:
- /hi/swift/converting-a-date-into-a-string/
date: 2024-01-20 17:37:58.061310-07:00
description: "\u0921\u0947\u091F \u0915\u094B \u0938\u094D\u091F\u094D\u0930\u093F\
  \u0902\u0917 \u092E\u0947\u0902 \u092C\u0926\u0932\u0928\u093E \u092E\u0924\u0932\
  \u092C \u0939\u0948 \u0924\u093E\u0930\u0940\u0916 \u0914\u0930 \u0938\u092E\u092F\
  \ \u0915\u094B \u092A\u0920\u0928\u0940\u092F \u092B\u0949\u0930\u094D\u092E\u0947\
  \u091F \u092E\u0947\u0902 \u092A\u0930\u093F\u0935\u0930\u094D\u0924\u093F\u0924\
  \ \u0915\u0930\u0928\u093E\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\
  \u092E\u0930\u094D\u0938 \u0907\u0938\u0947 \u0907\u0938\u0932\u093F\u090F \u0915\
  \u0930\u0924\u0947 \u0939\u0948\u0902 \u0924\u093E\u0915\u093F \u090F\u092A\u094D\
  \u0932\u093F\u0915\u0947\u0936\u0928 \u092F\u0942\u091C\u0930\u094D\u0938 \u0906\
  \u0938\u093E\u0928\u0940 \u0938\u0947 \u0924\u093E\u0930\u0940\u0916\u2026"
lastmod: 2024-02-18 23:09:03.988594
model: gpt-4-1106-preview
summary: "\u0921\u0947\u091F \u0915\u094B \u0938\u094D\u091F\u094D\u0930\u093F\u0902\
  \u0917 \u092E\u0947\u0902 \u092C\u0926\u0932\u0928\u093E \u092E\u0924\u0932\u092C\
  \ \u0939\u0948 \u0924\u093E\u0930\u0940\u0916 \u0914\u0930 \u0938\u092E\u092F \u0915\
  \u094B \u092A\u0920\u0928\u0940\u092F \u092B\u0949\u0930\u094D\u092E\u0947\u091F\
  \ \u092E\u0947\u0902 \u092A\u0930\u093F\u0935\u0930\u094D\u0924\u093F\u0924 \u0915\
  \u0930\u0928\u093E\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930\
  \u094D\u0938 \u0907\u0938\u0947 \u0907\u0938\u0932\u093F\u090F \u0915\u0930\u0924\
  \u0947 \u0939\u0948\u0902 \u0924\u093E\u0915\u093F \u090F\u092A\u094D\u0932\u093F\
  \u0915\u0947\u0936\u0928 \u092F\u0942\u091C\u0930\u094D\u0938 \u0906\u0938\u093E\
  \u0928\u0940 \u0938\u0947 \u0924\u093E\u0930\u0940\u0916\u2026"
title: "\u0924\u093E\u0930\u0940\u0916 \u0915\u094B \u0938\u094D\u091F\u094D\u0930\
  \u093F\u0902\u0917 \u092E\u0947\u0902 \u092C\u0926\u0932\u0928\u093E"
---

{{< edit_this_page >}}

## क्या और क्यों?

डेट को स्ट्रिंग में बदलना मतलब है तारीख और समय को पठनीय फॉर्मेट में परिवर्तित करना। प्रोग्रामर्स इसे इसलिए करते हैं ताकि एप्लिकेशन यूजर्स आसानी से तारीख और समय को समझ सकें और स्क्रीन पर सही तरीके से प्रदर्शित हो।

## कैसे करें:

Swift में `DateFormatter` का इस्तेमाल करते हुए डेट को स्ट्रिंग में बदल सकते हैं। नीचे कोड दिया गया है:

```Swift
import Foundation

let currentDate = Date()

let formatter = DateFormatter()
formatter.dateFormat = "dd/MM/yyyy"

let dateString = formatter.string(from: currentDate)
print(dateString)
```

अगर आज 12 अप्रैल 2023 है, आउटपुट होगा: 
```
12/04/2023
```

## गहराई में जानकारी:

`DateFormatter` में `dateFormat` का इस्तेमाल करके डेट को विभिन्न प्रकार के स्ट्रिंग फॉर्मेट्स में प्रदर्शित किया जा सकता है। `DateFormatter` कौन्सेप्ट 1980s से है, जब आईबीएम के सिस्टम/३८ में समान उपकरण थे। वैकल्पिक रूप से, `ISO8601DateFormatter` का उपयोग करके ISO-8601 मानक तारीखें बनाई जा सकती हैं। Swift में `Date` और `String` के बीच परिवर्तन कई तरीकों से किया जा सकता है, जिसमें `.timeIntervalSince1970` या कस्टम पैर्टन्स जैसे `"EEEE, MMM d, yyyy"` भी शामिल हैं।

## संबंधित सूत्रों की जानकारी:

- [Apple's Date Formatting Guide](https://developer.apple.com/documentation/foundation/dateformatter)
- [Swift Documentation: DateFormatter](https://developer.apple.com/documentation/foundation/dateformatter)
