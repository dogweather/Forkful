---
date: 2024-01-20 17:41:23.165071-07:00
description: "\u091F\u0947\u092E\u094D\u092A\u0930\u0947\u0930\u0940 \u092B\u093C\u093E\
  \u0907\u0932 \u0935\u0939 \u092B\u093C\u093E\u0907\u0932 \u0939\u094B\u0924\u0940\
  \ \u0939\u0948 \u091C\u093F\u0938\u0947 \u0915\u094B\u0921 \u091A\u0932\u0924\u0947\
  \ \u0935\u0915\u093C\u094D\u0924 \u0905\u0938\u094D\u0925\u093E\u092F\u0940 \u0930\
  \u0942\u092A \u0938\u0947 \u092C\u0928\u093E\u092F\u093E \u091C\u093E\u0924\u093E\
  \ \u0939\u0948\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930\
  \ \u0907\u0938\u0947 \u0921\u0947\u091F\u093E \u092A\u094D\u0930\u094B\u0938\u0947\
  \u0938\u093F\u0902\u0917, \u0932\u0949\u0917\u093F\u0902\u0917, \u092F\u093E \u092C\
  \u0921\u093C\u0947 \u092B\u093C\u093E\u0907\u0932 \u0911\u092A\u0930\u0947\u0936\
  \u0928\u094D\u0938 \u0915\u0947 \u0932\u093F\u090F\u2026"
lastmod: '2024-03-13T22:44:53.023086-06:00'
model: gpt-4-1106-preview
summary: "\u091F\u0947\u092E\u094D\u092A\u0930\u0947\u0930\u0940 \u092B\u093C\u093E\
  \u0907\u0932 \u0935\u0939 \u092B\u093C\u093E\u0907\u0932 \u0939\u094B\u0924\u0940\
  \ \u0939\u0948 \u091C\u093F\u0938\u0947 \u0915\u094B\u0921 \u091A\u0932\u0924\u0947\
  \ \u0935\u0915\u093C\u094D\u0924 \u0905\u0938\u094D\u0925\u093E\u092F\u0940 \u0930\
  \u0942\u092A \u0938\u0947 \u092C\u0928\u093E\u092F\u093E \u091C\u093E\u0924\u093E\
  \ \u0939\u0948\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930\
  \ \u0907\u0938\u0947 \u0921\u0947\u091F\u093E \u092A\u094D\u0930\u094B\u0938\u0947\
  \u0938\u093F\u0902\u0917, \u0932\u0949\u0917\u093F\u0902\u0917, \u092F\u093E \u092C\
  \u0921\u093C\u0947 \u092B\u093C\u093E\u0907\u0932 \u0911\u092A\u0930\u0947\u0936\
  \u0928\u094D\u0938 \u0915\u0947 \u0932\u093F\u090F \u0909\u092A\u092F\u094B\u0917\
  \ \u0915\u0930\u0924\u0947 \u0939\u0948\u0902\u0964."
title: "\u0905\u0938\u094D\u0925\u093E\u092F\u0940 \u092B\u093E\u0907\u0932 \u092C\
  \u0928\u093E\u0928\u093E"
weight: 21
---

## How to: (कैसे करें:)
```javascript
const fs = require('fs');
const os = require('os');
const path = require('path');

// टेम्परेरी फ़ाइल बनाने का फंक्शन
function createTempFile(content) {
  // टेम्परेरी डाइरेक्टरी पथ
  const tempDir = os.tmpdir();
  // टेम्परेरी फ़ाइल पथ बनाएं
  const tempFilePath = path.join(tempDir, `temp-${Date.now()}.txt`);
  // फ़ाइल बनाएं और डेटा लिखें
  fs.writeFileSync(tempFilePath, content);
  // फ़ाइल पथ वापस लौटाएं
  return tempFilePath;
}

// सेंपल कंटेंट
const sampleContent = 'यह एक उदाहरण है।';

// टेम्परेरी फ़ाइल बनाएं और पथ प्रिंट करें
const tempFile = createTempFile(sampleContent);
console.log(`टेम्परेरी फ़ाइल बन गई: ${tempFile}`);

// फ़ाइल पढ़ें
const readContent = fs.readFileSync(tempFile, 'utf8');
console.log(`फ़ाइल में क्या है: ${readContent}`);
```
सेम्पल आउटपुट:
```
टेम्परेरी फ़ाइल बन गई: C:\Users\...\AppData\Local\Temp\temp-1615406596776.txt
फ़ाइल में क्या है: यह एक उदाहरण है।
```

## Deep Dive (गहन जानकारी)
टेम्परेरी फ़ाइलें उस समय से इस्तेमाल हो रही हैं जब से कंप्यूटरों में मल्टीटास्किंग होने लगी। ये फ़ाइलें सिस्टम पर कम से कम समय के लिए डेटा स्टोर करती हैं और परफॉरमेंस बढ़ाने में मदद करती हैं। विकल्प के रूप में, आपके पास डेटाबेस, इन-मेमोरी स्टोरेज, या रिमोट सर्वर स्टोरेज हो सकते हैं। जावास्क्रिप्ट में, `fs` और `os` मॉड्यूल टेम्परेरी फ़ाइल बनाने की कमान संभालते हैं, जहाँ `fs` फाइल सिस्टम ऑपरेशन्स और `os` सिस्टम-लेवल जानकारी देता है।

## See Also (यह भी देखें)
- Node.js `fs` मॉड्यूल डॉक्यूमेंटेशन: [https://nodejs.org/api/fs.html](https://nodejs.org/api/fs.html)
- Node.js `os` मॉड्यूल डॉक्यूमेंटेशन: [https://nodejs.org/api/os.html](https://nodejs.org/api/os.html)
- `path` मॉड्यूल का इस्तेमाल: [https://nodejs.org/api/path.html](https://nodejs.org/api/path.html)
