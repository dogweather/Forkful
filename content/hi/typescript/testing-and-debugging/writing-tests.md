---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:33:26.941499-07:00
description: "TypeScript \u092E\u0947\u0902 \u092A\u0930\u0940\u0915\u094D\u0937\u0923\
  \ \u0932\u093F\u0916\u0928\u093E \u0906\u092A\u0915\u0947 \u0915\u094B\u0921 \u0915\
  \u0940 \u0915\u093E\u0930\u094D\u092F\u0915\u094D\u0937\u092E\u0924\u093E \u0914\
  \u0930 \u0938\u0939\u0940\u0924\u093E \u0915\u0940 \u091C\u093E\u0902\u091A \u0915\
  \u0947 \u0932\u093F\u090F \u0938\u094D\u0935\u091A\u093E\u0932\u093F\u0924 \u0938\
  \u094D\u0915\u094D\u0930\u093F\u092A\u094D\u091F\u094D\u0938 \u092C\u0928\u093E\u0928\
  \u0947 \u0915\u093E \u0915\u093E\u092E \u0936\u093E\u092E\u093F\u0932 \u0939\u0948\
  \u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930 \u0907\u0938\
  \u0947 \u0935\u093F\u0936\u094D\u0935\u0938\u0928\u0940\u092F\u0924\u093E\u2026"
lastmod: '2024-03-13T22:44:51.895205-06:00'
model: gpt-4-0125-preview
summary: "TypeScript \u092E\u0947\u0902 \u092A\u0930\u0940\u0915\u094D\u0937\u0923\
  \ \u0932\u093F\u0916\u0928\u093E \u0906\u092A\u0915\u0947 \u0915\u094B\u0921 \u0915\
  \u0940 \u0915\u093E\u0930\u094D\u092F\u0915\u094D\u0937\u092E\u0924\u093E \u0914\
  \u0930 \u0938\u0939\u0940\u0924\u093E \u0915\u0940 \u091C\u093E\u0902\u091A \u0915\
  \u0947 \u0932\u093F\u090F \u0938\u094D\u0935\u091A\u093E\u0932\u093F\u0924 \u0938\
  \u094D\u0915\u094D\u0930\u093F\u092A\u094D\u091F\u094D\u0938 \u092C\u0928\u093E\u0928\
  \u0947 \u0915\u093E \u0915\u093E\u092E \u0936\u093E\u092E\u093F\u0932 \u0939\u0948\
  \u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930 \u0907\u0938\
  \u0947 \u0935\u093F\u0936\u094D\u0935\u0938\u0928\u0940\u092F\u0924\u093E \u0938\
  \u0941\u0928\u093F\u0936\u094D\u091A\u093F\u0924 \u0915\u0930\u0928\u0947, \u091C\
  \u0932\u094D\u0926\u0940 \u0938\u0947 \u092C\u0917\u094D\u0938 \u092A\u0915\u0921\
  \u093C\u0928\u0947, \u0914\u0930 \u0930\u0916\u0930\u0916\u093E\u0935 \u092F\u094B\
  \u0917\u094D\u092F \u0915\u094B\u0921 \u0935\u0943\u0926\u094D\u0927\u093F \u0915\
  \u094B \u0938\u0941\u0935\u093F\u0927\u093E \u092A\u094D\u0930\u0926\u093E\u0928\
  \ \u0915\u0930\u0928\u0947 \u0915\u0947 \u0932\u093F\u090F \u0915\u0930\u0924\u0947\
  \ \u0939\u0948\u0902, \u0915\u094D\u092F\u094B\u0902\u0915\u093F TypeScript \u0915\
  \u0940 \u0938\u094D\u091F\u0948\u091F\u093F\u0915 \u091F\u093E\u0907\u092A\u093F\
  \u0902\u0917 JavaScript \u092A\u0930\u0940\u0915\u094D\u0937\u0923 \u0915\u0947\
  \ \u0932\u093F\u090F \u090F\u0915 \u0938\u094D\u0924\u0930 \u0915\u0940 \u092A\u0942\
  \u0930\u094D\u0935\u093E\u0939\u094D\u0928\u0924\u093E \u091C\u094B\u0921\u093C\u0924\
  \u0940 \u0939\u0948\u0964."
title: "\u091F\u0947\u0938\u094D\u091F \u0932\u093F\u0916\u0928\u093E"
weight: 36
---

## कैसे:
TypeScript अधिकांश JavaScript परीक्षण ढांचों के साथ सुगमतापूर्वक काम करता है। प्रदर्शन के लिए, हम Jest, एक लोकप्रिय परीक्षण फ्रेमवर्क का उपयोग करेंगे, इसकी TypeScript प्रोजेक्ट्स के लिए शून्य-कॉन्फ़िगरेशन सेटअप के कारण।

सबसे पहले, सुनिश्चित करें कि आपके पास Jest और आवश्यक TypeScript प्रकार स्थापित हों:

```bash
npm install --save-dev jest typescript ts-jest @types/jest
```

अगला, Jest को TypeScript के साथ काम करने के लिए सेटअप करें, `jest.config.js` को संशोधित करके या अगर एक नया बना रहे हैं तो:

```javascript
module.exports = {
  preset: 'ts-jest',
  testEnvironment: 'node',
};
```

अब, एक सरल फ़ंक्शन और इसके लिए एक परीक्षण लिखें। `sum.ts` फ़ाइल के साथ निम्नलिखित फ़ंक्शन पर विचार करें:

```typescript
// sum.ts
export function sum(a: number, b: number): number {
  return a + b;
}
```

`sum.test.ts` नामक एक परीक्षण फ़ाइल बनाएँ:

```typescript
// sum.test.ts
import { sum } from './sum';

test('adds 1 + 2 to equal 3', () => {
  expect(sum(1, 2)).toBe(3);
});
```

अपने परीक्षणों को इसके साथ चलाएँ:

```bash
npx jest
```

संकेत-सारणी कि एक परीक्षण पास हो गया है कुछ इस तरह दिखाई देना चाहिए:

```plaintext
 PASS  ./sum.test.ts
  ✓ adds 1 + 2 to equal 3 (2 ms)
```

असिंक्रोनस कोड के लिए, Jest `async/await` के साथ सम्मिलित करता है। मान लीजिए कि आपके पास एक असिंक्रोनस `fetchData` फ़ंक्शन है:

```typescript
// asyncFunctions.ts
export async function fetchData(): Promise<string> {
  return "data";
}
```

असिंक्रोनस फ़ंक्शन्स का उपयोग करते हुए आपका परीक्षण:

```typescript
// asyncFunctions.test.ts
import { fetchData } from './asyncFunctions';

test('fetches data successfully', async () => {
  expect(await fetchData()).toBe('data');
});
```

अपने परीक्षण चलाते समय, Jest प्रॉमिस के हल होने की प्रतीक्षा करेगा, सही ढंग से असिंक्रोनस ऑपरेशनों का परीक्षण करेगा।

याद रखें, प्रभावी परीक्षण में विभिन्न परिदृश्यों, सहित एज केसों के लिए कई परीक्षण लिखना शामिल है, ताकि यह सुनिश्चित किया जा सके कि आपका TypeScript कोड अपेक्षित रूप से व्यवहार करे।
