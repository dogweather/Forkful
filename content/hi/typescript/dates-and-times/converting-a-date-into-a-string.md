---
date: 2024-01-20 17:38:27.732154-07:00
description: "\u0921\u0947\u091F \u0915\u094B \u0938\u094D\u091F\u094D\u0930\u093F\
  \u0902\u0917 \u092E\u0947\u0902 \u092C\u0926\u0932\u0928\u093E \u092E\u0924\u0932\
  \u092C \u0939\u0948, \u090F\u0915 \u0924\u093E\u0930\u0940\u0916 \u0915\u094B \u092A\
  \u0922\u093C\u0928\u0947 \u092F\u094B\u0917\u094D\u092F \u092B\u0949\u0930\u094D\
  \u092E\u0947\u091F \u092E\u0947\u0902 \u092C\u0926\u0932\u0928\u093E\u0964 \u092A\
  \u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930 \u0907\u0938\u0947 \u0907\
  \u0938\u0932\u093F\u090F \u0915\u0930\u0924\u0947 \u0939\u0948\u0902 \u0915\u094D\
  \u092F\u094B\u0902\u0915\u093F \u092F\u0939 \u0924\u093E\u0930\u0940\u0916\u094B\
  \u0902 \u0915\u094B \u0932\u0949\u0917 \u0915\u0930\u0928\u0947, \u0926\u093F\u0916\
  \u093E\u0928\u0947 \u092F\u093E \u0905\u0928\u094D\u092F\u2026"
lastmod: '2024-03-13T22:44:51.909054-06:00'
model: gpt-4-1106-preview
summary: "\u0921\u0947\u091F \u0915\u094B \u0938\u094D\u091F\u094D\u0930\u093F\u0902\
  \u0917 \u092E\u0947\u0902 \u092C\u0926\u0932\u0928\u093E \u092E\u0924\u0932\u092C\
  \ \u0939\u0948, \u090F\u0915 \u0924\u093E\u0930\u0940\u0916 \u0915\u094B \u092A\u0922\
  \u093C\u0928\u0947 \u092F\u094B\u0917\u094D\u092F \u092B\u0949\u0930\u094D\u092E\
  \u0947\u091F \u092E\u0947\u0902 \u092C\u0926\u0932\u0928\u093E\u0964 \u092A\u094D\
  \u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930 \u0907\u0938\u0947 \u0907\u0938\
  \u0932\u093F\u090F \u0915\u0930\u0924\u0947 \u0939\u0948\u0902 \u0915\u094D\u092F\
  \u094B\u0902\u0915\u093F \u092F\u0939 \u0924\u093E\u0930\u0940\u0916\u094B\u0902\
  \ \u0915\u094B \u0932\u0949\u0917 \u0915\u0930\u0928\u0947, \u0926\u093F\u0916\u093E\
  \u0928\u0947 \u092F\u093E \u0905\u0928\u094D\u092F \u0938\u093F\u0938\u094D\u091F\
  \u092E\u094D\u0938 \u0915\u0947 \u0938\u093E\u0925 \u0938\u093E\u091D\u093E \u0915\
  \u0930\u0928\u0947 \u092E\u0947\u0902 \u0906\u0938\u093E\u0928\u0940 \u092A\u094D\
  \u0930\u0926\u093E\u0928 \u0915\u0930\u0924\u093E \u0939\u0948\u0964."
title: "\u0924\u093E\u0930\u0940\u0916 \u0915\u094B \u0938\u094D\u091F\u094D\u0930\
  \u093F\u0902\u0917 \u092E\u0947\u0902 \u092C\u0926\u0932\u0928\u093E"
weight: 28
---

## How to: (कैसे करें:)
```TypeScript
let currentDate: Date = new Date();
let dateString: string = currentDate.toISOString();
console.log(dateString); // "2023-05-21T14:00:00.000Z" जैसा आउटपुट देगा

// एक विशिष्ट फॉर्मेट में तारीख प्रारूपण
const options: Intl.DateTimeFormatOptions = {
  year: 'numeric',
  month: 'long',
  day: 'numeric',
  hour: '2-digit',
  minute: '2-digit',
  second: '2-digit',
  timeZoneName: 'short'
};

let formattedDate: string = new Intl.DateTimeFormat('en-US', options).format(currentDate);
console.log(formattedDate); // "May 21, 2023, 02:00:00 PM GMT+5" जैसा आउटपुट देगा
```

## Deep Dive (गहराई में):
तारीख को स्ट्रिंग में बदलने की प्रक्रिया हमेशा से कंप्यूटर प्रोग्रामिंग का हिस्सा रही है क्योंकि हमेशा नए तरीके और मानक आते रहे हैं। ISO 8601 फॉर्मेट एक अंतरराष्ट्रीय मानक है जो विभिन्न सिस्टम्स के बीच साझा करने में मदद करता है। `Date.prototype.toISOString` जैसे मेथड इसी स्टैंडर्ड को सपोर्ट करते हैं। 

हालांकि, जब एक निश्चित फॉर्मेट की आवश्यकता होती है, `Intl.DateTimeFormat` का इस्तेमाल किया जाता है। यह एपीआई लोकेल और ऑप्शन्स पर आधारित तारीख को प्रारूपित करता है।

इसके अलावा `Date.prototype.toLocaleString` या तृतीय-पक्ष लाइब्रेरीज़ जैसे `moment.js`, `date-fns` भी उपलब्ध हैं, जिनसे अधिक रिच तारीख प्रारूपण विकल्प मिलते हैं।

## See Also (यह भी देखें):
- [ECMAScript Internationalization API Specification](https://tc39.es/ecma402/)
- [`moment.js` library](https://momentjs.com/)
- [`date-fns` library](https://date-fns.org/)
