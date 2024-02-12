---
title:                "स्ट्रिंग से उद्धरण चिह्न हटाना"
aliases:
- hi/typescript/removing-quotes-from-a-string.md
date:                  2024-01-26T03:43:44.291668-07:00
model:                 gpt-4-0125-preview
simple_title:         "स्ट्रिंग से उद्धरण चिह्न हटाना"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/typescript/removing-quotes-from-a-string.md"
---

{{< edit_this_page >}}

## क्या और क्यों?
स्ट्रिंग से उद्धरण हटाने का मतलब है कोड में स्ट्रिंग लिटरल्स को परिभाषित करने वाले एकल (`'`) या दोहरे (`"`) उद्धरण वर्णों को हटाना। प्रोग्रामर इसे कई कारणों से करते हैं, जैसे कि आउटपुट को फॉर्मेट करना, उपयोगकर्ता इनपुट से सुरक्षित करना या पार्सिंग या स्टोरेज के लिए स्ट्रिंग्स तैयार करना जहां उद्धरण अनावश्यक हों या त्रुटियों का कारण बन सकते हैं।

## कैसे करें:
यहां आपके TypeScript में स्ट्रिंग्स से उन कष्टप्रद उद्धरण चिह्नों को अलग करने का सरल मार्गदर्शिका है।

```typescript
// विकल्प A: रेगेक्स का उपयोग करते हुए एकल या दोहरे उद्धरणों को बदलें
function removeQuotes(input: string): string {
  return input.replace(/^["']|["']$/g, '');
}

console.log(removeQuotes(`"Quoted string"`)); // Quoted string
console.log(removeQuotes(`'Another one'`)); // Another one

// विकल्प B: ऐसे स्ट्रिंग्स से निपटना जो अलग-अलग उद्धरणों के साथ शुरू और समाप्त होते हैं
function removeMismatchedQuotes(input: string): string {
  return input.replace(/^(['"])(.*?)(?<!\1)\1$/, '$2');
}

console.log(removeMismatchedQuotes(`"Mismatched'`)); // "Mismatched'

// विकल्प C: विभिन्न प्रकार के उद्धरणों को ट्रिम करना
function removeAllQuotes(input: string): string {
  return input.replace(/['"]+/g, '');
}

console.log(removeAllQuotes(`"'Mix'n'Match'"`)); // Mix'n'Match
```

## गहराई में जाओ
बहुत पहले, जब TypeScript भी एक बात नहीं थी, जावास्क्रिप्ट कोडर्स पहले से ही उद्धरण की चालबाजियों से निपट रहे थे, और TypeScript के लिए कहानी लगभग वैसी ही है। समय के साथ बदलते ही, हम स्ट्रिंग्स को कैसे काटते हैं, इसमें भी बदलाव होता है। आजकल, रेगेक्स की शक्ति के साथ, हम क्लंकी स्ट्रिंग स्लाइसिंग या अन्य थकाऊ तरीकों का उपयोग करने को एक तरफ धकेल देते हैं।

जबकि ऊपर दिए गए उदाहरण आपकी अधिकांश जरूरतों को कवर करना चाहिए, ध्यान रहे, उद्धरण पेचीदा हो सकते हैं। नेस्टेड, मिसमैच्ड, और एस्केप्ड उद्धरण वे चतुराई लुढ़काने वाले हैं जो आपको गिराने की प्रतीक्षा कर रहे हैं। इनके लिए, आपको अधिक सोफिस्टिकेटेड पैटर्न या यहां तक कि पार्सर्स की आवश्यकता हो सकती है जो हर जटिल मामले को संभाल सकते हो। 

विकल्प? कुछ लोग `trim` और `trimStart` / `trimEnd` जैसे मेथड्स के साथ lodash जैसी लाइब्रेरीज का उपयोग करना पसंद करते हैं, जिन्हें आप उन वर्णों को सेट करके उद्धरणों को काटने के लिए अनुकूलित कर सकते हैं।

और TypeScript के उत्साही लोगों के लिए, चलिए प्रकारों के बारे में न भूलें। जबकि हम यहां मुख्य रूप से स्ट्रिंग्स के साथ काम कर रहे हैं, जब आप उपयोगकर्ता इनपुट या पार्सिंग के साथ काम कर रहे होते हैं, तो कुछ प्रकार के गार्ड्स या यहां तक कि जेनेरिक्स को शामिल करने से आपके कोड को सुरक्षित रखने में मदद मिल सकती है जैसे आपके उद्धरण ट्रिम किए जाते हैं।

## देखें भी
और जानकारी के लिए इन वर्चुअल हॉटस्पॉट्स को देखें:

- MDN वेब डॉक्स पर रेगेक्स (https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions)
- TypeScript आधिकारिक दस्तावेज़ीकरण (https://www.typescriptlang.org/docs/)
- You Don't Need Lodash/Underscore – स्ट्रिंग हेल्पर्स (https://github.com/you-dont-need/You-Dont-Need-Lodash-Underscore#strings)
- Stack Overflow: उन ट्रेंचों को पार करें जहाँ अनगिनत devs ने उद्धरण आपदाओं से लड़ाई लड़ी है (https://stackoverflow.com/)
