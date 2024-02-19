---
aliases:
- /hi/swift/calculating-a-date-in-the-future-or-past/
date: 2024-01-20 17:32:37.427767-07:00
description: "\u092D\u0935\u093F\u0937\u094D\u092F \u092F\u093E \u0905\u0924\u0940\
  \u0924 \u092E\u0947\u0902 \u0924\u093E\u0930\u0940\u0916 \u0915\u0940 \u0917\u0923\
  \u0928\u093E \u0915\u093E \u092E\u0924\u0932\u092C \u0939\u0948 \u0906\u091C \u0915\
  \u0940 \u0924\u093E\u0930\u0940\u0916 \u0938\u0947 \u0915\u0941\u091B \u0926\u093F\
  \u0928, \u092E\u0939\u0940\u0928\u0947 \u092F\u093E \u0938\u093E\u0932 \u092C\u0922\
  \u093C\u093E\u0928\u093E \u092F\u093E \u0918\u091F\u093E\u0928\u093E\u0964 \u092A\
  \u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930 \u0907\u0938\u0915\u093E\
  \ \u0909\u092A\u092F\u094B\u0917 \u0907\u0935\u0947\u0902\u091F\u094D\u0938, \u0930\
  \u093F\u092E\u093E\u0907\u0902\u0921\u0930\u094D\u0938, \u0914\u0930 \u0921\u0947\
  \u091F\u093E\u2026"
lastmod: 2024-02-18 23:09:03.992211
model: gpt-4-1106-preview
summary: "\u092D\u0935\u093F\u0937\u094D\u092F \u092F\u093E \u0905\u0924\u0940\u0924\
  \ \u092E\u0947\u0902 \u0924\u093E\u0930\u0940\u0916 \u0915\u0940 \u0917\u0923\u0928\
  \u093E \u0915\u093E \u092E\u0924\u0932\u092C \u0939\u0948 \u0906\u091C \u0915\u0940\
  \ \u0924\u093E\u0930\u0940\u0916 \u0938\u0947 \u0915\u0941\u091B \u0926\u093F\u0928\
  , \u092E\u0939\u0940\u0928\u0947 \u092F\u093E \u0938\u093E\u0932 \u092C\u0922\u093C\
  \u093E\u0928\u093E \u092F\u093E \u0918\u091F\u093E\u0928\u093E\u0964 \u092A\u094D\
  \u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930 \u0907\u0938\u0915\u093E \u0909\
  \u092A\u092F\u094B\u0917 \u0907\u0935\u0947\u0902\u091F\u094D\u0938, \u0930\u093F\
  \u092E\u093E\u0907\u0902\u0921\u0930\u094D\u0938, \u0914\u0930 \u0921\u0947\u091F\
  \u093E\u2026"
title: "\u092D\u0935\u093F\u0937\u094D\u092F \u092F\u093E \u0905\u0924\u0940\u0924\
  \ \u092E\u0947\u0902 \u0924\u093E\u0930\u0940\u0916 \u0915\u0940 \u0917\u0923\u0928\
  \u093E"
---

{{< edit_this_page >}}

## क्या और क्यों?

भविष्य या अतीत में तारीख की गणना का मतलब है आज की तारीख से कुछ दिन, महीने या साल बढ़ाना या घटाना। प्रोग्रामर इसका उपयोग इवेंट्स, रिमाइंडर्स, और डेटा एनालिसिस के लिए करते हैं।

## कैसे करें:

Swift में हम `Date` और `Calendar` का उपयोग करके डेट को मैनिपुलेट कर सकते हैं। ये रहे कोड उदाहरण:

```Swift
import Foundation

// वर्तमान तारीख
let today = Date()

// कैलेंडर इनिशियलाइज़ करना
let calendar = Calendar.current

// भविष्य में एक सप्ताह जोड़ना
if let nextWeek = calendar.date(byAdding: .day, value: 7, to: today) {
    print("अगला सप्ताह: \(nextWeek)")
}

// अतीत में एक महीना घटाना
if let lastMonth = calendar.date(byAdding: .month, value: -1, to: today) {
    print("पिछला महीना: \(lastMonth)")
}
```

सैंपल आउटपुट:

```
अगला सप्ताह: <भविष्य की तारीख>
पिछला महीना: <अतीत की तारीख>
```

## गहराई से जानकारी:

स्विफ्ट में तारीख की गणना Foundation फ्रेमवर्क की `Date` और `Calendar` क्लासेज की मदद से की जाती है। `Date` विशिष्ट टाइमस्टैम्प को रिप्रेज़ेंट करता है, जबकि `Calendar` में समय और तारीख संबंधित गणनाएँ और मैनिपुलेशन होते हैं। इतिहास में, प्रोग्रामर्स ने मैन्युअली सेकंड्स जोड़कर तारीख की गणना की थी, जो लीप ईयर्स और विभिन्न महीनों के दिनों को देखते हुए जटिल हो सकता था। Swift ने इसे `Calendar` मेथड्स के साथ सरल बनाया है। 

विकल्पों के रूप में, DateComponents का उपयोग करके भी डेट मैनिपुलेशन संभव है, और थर्ड-पार्टी लाइब्रेरीज जैसे कि SwiftDate और DateTools भी हैं, जो और भी ज्यादा सुविधाएँ प्रदान करती हैं।

## देखें भी:

- [Apple Developer Documentation: Date](https://developer.apple.com/documentation/foundation/date)
- [Apple Developer Documentation: Calendar](https://developer.apple.com/documentation/foundation/calendar)
- [SwiftDate GitHub Repository](https://github.com/malcommac/SwiftDate)
- [DateTools GitHub Repository](https://github.com/MatthewYork/DateTools)
