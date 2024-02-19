---
aliases:
- /hi/haskell/comparing-two-dates/
date: 2024-01-20 17:33:28.807651-07:00
description: "\u0924\u093E\u0930\u0940\u0916\u094B\u0902 \u0915\u0940 \u0924\u0941\
  \u0932\u0928\u093E \u0915\u0930\u0928\u0947 \u0915\u093E \u092E\u0924\u0932\u092C\
  \ \u0939\u0948 \u0926\u094B \u0924\u093F\u0925\u093F\u092F\u094B\u0902 \u0915\u094B\
  \ \u0906\u092A\u0938 \u092E\u0947\u0902 \u092E\u093F\u0932\u093E\u0928 \u0915\u0930\
  \u0928\u093E\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930\u094D\
  \u0938 \u092F\u0939 \u0915\u093E\u092E \u0924\u093F\u0925\u093F\u092F\u094B\u0902\
  \ \u0915\u0940 \u0938\u0940\u092E\u093E\u0913\u0902 \u0915\u094B \u091C\u093E\u0928\
  \u0928\u0947, \u0938\u092E\u092F-\u0938\u0940\u092E\u093E \u0915\u0940 \u092A\u0941\
  \u0937\u094D\u091F\u093F \u0915\u0930\u0928\u0947, \u0914\u0930 \u0915\u094D\u0930\
  \u092E\u092C\u0926\u094D\u0927\u2026"
lastmod: 2024-02-18 23:09:03.446080
model: gpt-4-1106-preview
summary: "\u0924\u093E\u0930\u0940\u0916\u094B\u0902 \u0915\u0940 \u0924\u0941\u0932\
  \u0928\u093E \u0915\u0930\u0928\u0947 \u0915\u093E \u092E\u0924\u0932\u092C \u0939\
  \u0948 \u0926\u094B \u0924\u093F\u0925\u093F\u092F\u094B\u0902 \u0915\u094B \u0906\
  \u092A\u0938 \u092E\u0947\u0902 \u092E\u093F\u0932\u093E\u0928 \u0915\u0930\u0928\
  \u093E\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930\u094D\u0938\
  \ \u092F\u0939 \u0915\u093E\u092E \u0924\u093F\u0925\u093F\u092F\u094B\u0902 \u0915\
  \u0940 \u0938\u0940\u092E\u093E\u0913\u0902 \u0915\u094B \u091C\u093E\u0928\u0928\
  \u0947, \u0938\u092E\u092F-\u0938\u0940\u092E\u093E \u0915\u0940 \u092A\u0941\u0937\
  \u094D\u091F\u093F \u0915\u0930\u0928\u0947, \u0914\u0930 \u0915\u094D\u0930\u092E\
  \u092C\u0926\u094D\u0927\u2026"
title: "\u0926\u094B \u0924\u093E\u0930\u0940\u0916\u094B\u0902 \u0915\u0940 \u0924\
  \u0941\u0932\u0928\u093E"
---

{{< edit_this_page >}}

## What & Why? (क्या और क्यों?)
तारीखों की तुलना करने का मतलब है दो तिथियों को आपस में मिलान करना। प्रोग्रामर्स यह काम तिथियों की सीमाओं को जानने, समय-सीमा की पुष्टि करने, और क्रमबद्ध करने के लिए करते हैं।

## How to: (कैसे करें:)
```Haskell
import Data.Time

-- दो तिथियों की तुलना करने का फंक्शन
compareDates :: Day -> Day -> Ordering
compareDates date1 date2 = compare date1 date2

main :: IO ()
main = do
    -- तिथियों का उदाहरण
    let date1 = fromGregorian 2023 1 1 -- 1 जनवरी 2023
    let date2 = fromGregorian 2023 12 31 -- 31 दिसंबर 2023
    
    -- तुलना का परिणाम प्रिंट करना
    print $ compareDates date1 date2
```
आउटपुट:
```Haskell
LT -- 'LT' का मतलब है date1 कम है date2 से (Less Than)
```

## Deep Dive (गहराई से जानकारी):
तिथियों की तुलना ऐतिहासिक रूप से कैलेंडर सिस्टमों के विकास के साथ आई है। Haskell `Data.Time` लाइब्रेरी में इसे कार्यान्वित करने के कई तरीके हैं, जैसे कि `UTCTime`, `ZonedTime`, आदि उपयोग करना। `compareDates` फंक्शन `compare` का इस्तेमाल कर के `Day` टाइप की तिथियों की स्वतः तुलना करता है। आप `before`, `after` जैसे फंक्शन्स का भी इस्तेमाल कर सकते हैं।

## See Also (और जानकारी के लिए):
- Haskell Documentation for `Data.Time` Library: [https://hackage.haskell.org/package/time-1.9.3/docs/Data-Time.html](https://hackage.haskell.org/package/time-1.9.3/docs/Data-Time.html)
