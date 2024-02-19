---
aliases:
- /hi/typescript/calculating-a-date-in-the-future-or-past/
date: 2024-01-20 17:32:13.363763-07:00
description: "\u0915\u093F\u0938\u0940 \u092D\u0935\u093F\u0937\u094D\u092F \u092F\
  \u093E \u0905\u0924\u0940\u0924 \u0915\u0940 \u0924\u093E\u0930\u0940\u0916 \u0915\
  \u0940 \u0917\u0923\u0928\u093E \u0938\u0947 \u092E\u0924\u0932\u092C \u0939\u0948\
  \ \u0915\u093F \u0939\u092E \u090F\u0915 \u0928\u093F\u0936\u094D\u091A\u093F\u0924\
  \ \u0924\u093E\u0930\u0940\u0916 \u0938\u0947 \u092A\u0939\u0932\u0947 \u092F\u093E\
  \ \u092C\u093E\u0926 \u0915\u0940 \u0924\u093E\u0930\u0940\u0916 \u0915\u094B \u0928\
  \u093F\u0915\u093E\u0932\u0947\u0902\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\
  \u093E\u092E\u0930\u094D\u0938 \u0907\u0938\u0915\u093E \u0907\u0938\u094D\u0924\
  \u0947\u092E\u093E\u0932 \u0915\u093F\u0938\u0940 \u0907\u0935\u0947\u0902\u091F\
  \u094D\u0938,\u2026"
lastmod: 2024-02-18 23:09:02.903925
model: gpt-4-1106-preview
summary: "\u0915\u093F\u0938\u0940 \u092D\u0935\u093F\u0937\u094D\u092F \u092F\u093E\
  \ \u0905\u0924\u0940\u0924 \u0915\u0940 \u0924\u093E\u0930\u0940\u0916 \u0915\u0940\
  \ \u0917\u0923\u0928\u093E \u0938\u0947 \u092E\u0924\u0932\u092C \u0939\u0948 \u0915\
  \u093F \u0939\u092E \u090F\u0915 \u0928\u093F\u0936\u094D\u091A\u093F\u0924 \u0924\
  \u093E\u0930\u0940\u0916 \u0938\u0947 \u092A\u0939\u0932\u0947 \u092F\u093E \u092C\
  \u093E\u0926 \u0915\u0940 \u0924\u093E\u0930\u0940\u0916 \u0915\u094B \u0928\u093F\
  \u0915\u093E\u0932\u0947\u0902\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\
  \u092E\u0930\u094D\u0938 \u0907\u0938\u0915\u093E \u0907\u0938\u094D\u0924\u0947\
  \u092E\u093E\u0932 \u0915\u093F\u0938\u0940 \u0907\u0935\u0947\u0902\u091F\u094D\
  \u0938,\u2026"
title: "\u092D\u0935\u093F\u0937\u094D\u092F \u092F\u093E \u0905\u0924\u0940\u0924\
  \ \u092E\u0947\u0902 \u0924\u093E\u0930\u0940\u0916 \u0915\u0940 \u0917\u0923\u0928\
  \u093E"
---

{{< edit_this_page >}}

## क्या और क्यों?

किसी भविष्य या अतीत की तारीख की गणना से मतलब है कि हम एक निश्चित तारीख से पहले या बाद की तारीख को निकालें। प्रोग्रामर्स इसका इस्तेमाल किसी इवेंट्स, डेडलाइंस, या अन्य महत्वपूर्ण समय-संबंधी गणनाओं के लिए करते हैं।

## कैसे करें:

```typescript
// आज की तारीख को प्राप्त करें
const today: Date = new Date();

// 10 दिन बाद की तारीख कैलकुलेट करें
const tenDaysLater: Date = new Date(today);
tenDaysLater.setDate(today.getDate() + 10);

console.log(`10 दिन बाद की तारीख: ${tenDaysLater.toLocaleDateString()}`);

// 5 वर्ष पहले की तारीख कैलकुलेट करें
const fiveYearsEarlier: Date = new Date(today);
fiveYearsEarlier.setFullYear(today.getFullYear() - 5);

console.log(`5 वर्ष पहले की तारीख: ${fiveYearsEarlier.toLocaleDateString()}`);
```

## गहराई से जानकारी:

तारीखों की गणना JavaScript के प्राचीन समय से होती आ रही है और यह TypeScript में भी समान है, क्योंकि TypeScript JavaScript का ही एक सुधारित रूप है। आप `Date` ऑब्जेक्ट का इस्तेमाल करके तारीखों को मैनेज कर सकते हैं। एक अल्टरनेटिव `moment.js` लाइब्रेरी है, पर `Date` हल्का और बिना किसी अतिरिक्त डिपेंडेंसी के होता है। हालांकि, टाइमजोन और लीप ईयर्स जैसी जटिलताओं को हैंडल करते समय, आपको इन जटिलताओं को समझने की जरूरत हो सकती है।

## संबंधित सूत्र:

- मोमेंट जेएस के डॉक्यूमेंटेशन: [Moment.js Docs](https://momentjs.com/docs/)
- MDN Web Docs, JavaScript Date ऑब्जेक्ट पर: [MDN JavaScript Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)
