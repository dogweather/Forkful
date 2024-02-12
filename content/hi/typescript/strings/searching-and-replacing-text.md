---
title:                "पाठ खोजना और बदलना"
date:                  2024-01-20T17:59:23.069675-07:00
model:                 gpt-4-1106-preview
simple_title:         "पाठ खोजना और बदलना"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/typescript/searching-and-replacing-text.md"
---

{{< edit_this_page >}}

## What & Why? (क्या और क्यों?)
टेक्स्ट सर्च करना और बदलना मतलब है किसी स्ट्रिंग में विशेष शब्द या पैटर्न को ढूंढना और उसे नई स्ट्रिंग से रिप्लेस करना। प्रोग्रामर्स इसे डाटा संशोधन, यूज़र इनपुट्स की जांच, और सॉफ्टवेयर इंटरनल्स में एडिटिंग करने के लिए करते हैं।

## How to: (कैसे करें:)
```typescript
// साधारण स्ट्रिंग रिप्लेसमेंट
let quote = "जीवन एक यात्रा है।";
let updatedQuote = quote.replace("यात्रा", "सफ़र");
console.log(updatedQuote); // "जीवन एक सफ़र है।"

// ग्लोबल रिप्लेसमेंट रेगेक्स का इस्तेमाल करते हुए
let essay = "बारिश शांत है। बारिश सुंदर है।";
let updatedEssay = essay.replace(/बारिश/g, "सावन");
console.log(updatedEssay); // "सावन शांत है। सावन सुंदर है।"

// केस-इनसेंसिटिव रिप्लेसमेंट
let message = "TypeScript ज्ञान है। TYPESCRIPT शक्ति है।";
let updatedMessage = message.replace(/typescript/ig, "TypeScript");
console.log(updatedMessage); // "TypeScript ज्ञान है। TypeScript शक्ति है।"
```

## Deep Dive (गहराई में):
टेक्स्ट सर्चिंग और रिप्लेसमेंट की जरूरत 1950s में शुरू हुई, जब एडिटिंग टूल्स और प्रोग्रामिंग लैंग्वेजेज की शुरूआत हुई। जैसे-जैसे टेक्नोलॉजी आगे बढ़ी, रेगुलर एक्सप्रेशन्स (regex) का आविष्कार हुआ, जो जटिल पैटर्न्स की सर्चिंग और रिप्लेसिंग को सरल बनाते हैं। इन कार्यों को आज के प्रोग्रामिंग टूल्स में और अधिक कुशलता से इंटीग्रेट किया गया है। जैसे कि TypeScript में, `String.prototype.replace` फंक्शन हमारी मदद करता है विभिन्न फ्लेग्स (`g` for global, `i` for case-insensitive) को यूज़ करते हुए पूरी वर्सेटिलिटी के साथ।

## See Also (और भी जानें):
- MDN Web Docs पर JavaScript String replace(): https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace
- RegExr - Regex टेस्टिंग और लर्निंग टूल: https://regexr.com/
- TypeScript डॉक्यूमेंटेशन: https://www.typescriptlang.org/docs/
