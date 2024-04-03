---
date: 2024-01-20 17:41:40.221134-07:00
description: "\u0938\u094D\u0935\u093F\u092B\u094D\u091F \u092E\u0947\u0902 \u0905\
  \u0938\u094D\u0925\u093E\u092F\u0940 \u092B\u093E\u0907\u0932 \u092C\u0928\u093E\
  \u0928\u0947 \u0915\u093E \u092E\u0924\u0932\u092C \u0939\u0948 \u0915\u093F \u0906\
  \u092A \u0921\u0947\u091F\u093E \u0915\u094B \u090F\u0915 \u092B\u093E\u0907\u0932\
  \ \u092E\u0947\u0902 \u0938\u094D\u091F\u094B\u0930 \u0915\u0930\u0924\u0947 \u0939\
  \u0948\u0902 \u091C\u094B \u0915\u0941\u091B \u0938\u092E\u092F \u0915\u0947 \u0932\
  \u093F\u090F \u091C\u0930\u0942\u0930\u0940 \u0939\u094B\u0924\u0940 \u0939\u0948\
  \u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930\u094D\u0938\
  \ \u0907\u0938\u0947 \u0921\u0947\u091F\u093E \u0938\u0902\u0938\u093E\u0927\u0928\
  ,\u2026"
lastmod: '2024-03-13T22:44:52.951729-06:00'
model: gpt-4-1106-preview
summary: "\u0938\u094D\u0935\u093F\u092B\u094D\u091F \u092E\u0947\u0902 \u0905\u0938\
  \u094D\u0925\u093E\u092F\u0940 \u092B\u093E\u0907\u0932 \u092C\u0928\u093E\u0928\
  \u0947 \u0915\u093E \u092E\u0924\u0932\u092C \u0939\u0948 \u0915\u093F \u0906\u092A\
  \ \u0921\u0947\u091F\u093E \u0915\u094B \u090F\u0915 \u092B\u093E\u0907\u0932 \u092E\
  \u0947\u0902 \u0938\u094D\u091F\u094B\u0930 \u0915\u0930\u0924\u0947 \u0939\u0948\
  \u0902 \u091C\u094B \u0915\u0941\u091B \u0938\u092E\u092F \u0915\u0947 \u0932\u093F\
  \u090F \u091C\u0930\u0942\u0930\u0940 \u0939\u094B\u0924\u0940 \u0939\u0948\u0964\
  \ \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930\u094D\u0938 \u0907\
  \u0938\u0947 \u0921\u0947\u091F\u093E \u0938\u0902\u0938\u093E\u0927\u0928, \u091F\
  \u0947\u0938\u094D\u091F\u093F\u0902\u0917, \u092F\u093E \u0905\u0938\u094D\u0925\
  \u093E\u092F\u0940 \u0938\u0902\u0917\u094D\u0930\u0939 \u0915\u0947 \u0932\u093F\
  \u090F \u0915\u0930\u0924\u0947 \u0939\u0948\u0902\u0964."
title: "\u0905\u0938\u094D\u0925\u093E\u092F\u0940 \u092B\u093E\u0907\u0932 \u092C\
  \u0928\u093E\u0928\u093E"
weight: 21
---

## How to: (कैसे करें:)
```Swift
import Foundation

// अस्थायी डायरेक्टरी प्राप्त करना
let tempDirectory = NSTemporaryDirectory()

// अद्वितीय फाइल नाम जनरेट करना
let fileName = UUID().uuidString
let tempFilePath = (tempDirectory as NSString).appendingPathComponent(fileName)

// फाइल में डेटा लिखना
let sampleText = "यह एक अस्थायी फाइल है।"
do {
    try sampleText.write(toFile: tempFilePath, atomically: true, encoding: .utf8)
    print("फाइल सफलतापूर्वक बनाई गई: \(tempFilePath)")
} catch {
    print("फाइल बनाने में त्रुटि: \(error.localizedDescription)")
}

```

## Deep Dive (गहन अध्ययन):
समय के साथ, अस्थायी फाइलों की आवश्यकता बढ़ी है। पहले, सिस्टम्स टेंप डायरेक्टरीज़ नहीं होती थीं या बहुत बुनियादी होती थीं। अब, प्लैटफॉर्म्स जैसे कि iOS और macOS प्रोग्रामर्स को NSTemporaryDirectory() जैसे मेथड्स देते हैं।

अल्टरनेटिव्स में रैम-डिस्क, in-memory स्टोरेज, या custom-cacheing सोल्यूशंस हैं। Implement करने में, फाइल नाम की uniqueness महत्वपूर्ण है – UUIDs या timestamps का उपयोग करें। याद रखें, temporary files को सिस्टम की cleanup process में अपने आप हटा दिया जा सकता है।

## See Also (यह भी देखें):
- [FileManager Class Reference](https://developer.apple.com/documentation/foundation/filemanager)
- [UUID Class Reference](https://developer.apple.com/documentation/foundation/uuid)
