---
title:                "टेस्ट लिखना"
aliases:
- hi/javascript/writing-tests.md
date:                  2024-02-03T19:32:26.951046-07:00
model:                 gpt-4-0125-preview
simple_title:         "टेस्ट लिखना"
tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/javascript/writing-tests.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## क्या और क्यों?

जावास्क्रिप्ट में परीक्षण लिखना स्वचालित स्क्रिप्ट्स तैयार करने की प्रक्रिया को दर्शाता है जो आपके कोड को चलाती हैं ताकि यह सुनिश्चित हो सके कि यह अपेक्षित के अनुसार व्यवहार करता है, जो आपकी एप्लिकेशन्स की विश्वसनीयता और रख-रखाव में काफी सुधार कर सकती है। प्रोग्रामर ऐसा शुरूआती चरण में बग को पकड़ने, कोड रिफैक्टरिंग को सुगम बनाने, और नई सुविधाओं को मौजूदा कार्यक्षमता को टूटने से रोकने के लिए करते हैं।

## कैसे करें:

### नेटिव दृष्टिकोण (जेस्ट का उपयोग करके)

जेस्ट एक लोकप्रिय परीक्षण ढांचा है जो जावास्क्रिप्ट में यूनिट परीक्षण लिखने के लिए एक मैत्रीपूर्ण API प्रदान करता है। इसे न्यूनतम कॉन्फ़िगरेशन की आवश्यकता होती है और यह मॉक फंक्शन्स, टाइमर्स, और स्नैपशॉट परीक्षण जैसी सुविधाओं के साथ आता है।

1. **इंस्टॉलेशन**:

```bash
npm install --save-dev jest
```

2. **एक साधारण परीक्षण लिखना**:

`sum.test.js` नामक फाइल बनाएँ:

```javascript
const sum = require('./sum'); // मान लें कि यह फ़ंक्शन सिर्फ दो नंबर जोड़ता है

test('adds 1 + 2 to equal 3', () => {
  expect(sum(1, 2)).toBe(3);
});
```

3. **अपने परीक्षण को चलाना**:

```bash
npx jest
```

**नमूना आउटपुट:**

```plaintext
PASS  ./sum.test.js
✓ adds 1 + 2 to equal 3 (5ms)
```

### असिंक्रोनस कोड का परीक्षण

जेस्ट वादे और async/await सिंटैक्स का परीक्षण करना आसान बनाता है:

```javascript
// asyncSum.js
async function asyncSum(a, b) {
  return Promise.resolve(a + b);
}

// asyncSum.test.js
test('async addition works', async () => {
  await expect(asyncSum(1, 2)).resolves.toBe(3);
});

```

### तृतीय-पक्ष पुस्तकालयों का उपयोग (मोचा और चाई)

मोचा एक और लोकप्रिय परीक्षण ढांचा है, अधिक सकारात्मक परीक्षणों के लिए चाई अस्सेर्शन पुस्तकालय के साथ अक्सर इस्तेमाल किया जाता है।

1. **इंस्टॉलेशन**:

```bash
npm install --save-dev mocha chai
```

2. **मोचा और चाई के साथ एक परीक्षण लिखना**:

`calculate.test.js` बनाएँ:

```javascript
const chai = require('chai');
const expect = chai.expect;

const calculate = require('./calculate'); // एक साधारण गणना मॉड्यूल

describe('Calculate', function() {
  it('should sum two values', function() {
    expect(calculate.sum(5, 2)).to.equal(7);
  });
});
```

3. **मोचा के साथ अपने परीक्षणों को चलाना**:

अपने `package.json` में एक स्क्रिप्ट जोड़ें:

```json
"scripts": {
  "test": "mocha"
}
```

फिर निष्पादित करें:

```bash
npm test
```

**नमूना आउटपुट:**

```plaintext
  Calculate
    ✓ should sum two values


  1 passing (8ms)
```

ये उदाहरण जावास्क्रिप्ट में बुनियादी परीक्षण लेखन और निष्पादन का प्रतिनिधित्व करते हैं। जेस्ट या मोचा के साथ चाई का एक परीक्षण ढांचा अपनाना मजबूत एप्लिकेशन परीक्षण के लिए एक मजबूत आधार प्रदान कर सकता है, यह सुनिश्चित करने में मदद करता है कि आपके कोड का कार्य अपडेट्स और रिफैक्टरिंग्स में इरादे के अनुसार हो।
