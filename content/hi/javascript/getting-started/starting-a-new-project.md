---
date: 2024-01-20 18:04:21.191578-07:00
description: "\u0928\u092F\u093E \u092A\u094D\u0930\u094B\u091C\u0947\u0915\u094D\u091F\
  \ \u0936\u0941\u0930\u0942 \u0915\u0930\u0928\u093E \u092E\u0924\u0932\u092C \u0915\
  \u094B\u0921 \u0915\u0940 \u090F\u0915 \u0928\u0908 \u0926\u0941\u0928\u093F\u092F\
  \u093E \u092C\u0928\u093E\u0928\u093E\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\
  \u0930\u093E\u092E\u0930 \u0907\u0938\u0947 \u0928\u090F \u0906\u0907\u0921\u093F\
  \u092F\u093E \u091F\u0947\u0938\u094D\u091F \u0915\u0930\u0928\u0947, \u0938\u094D\
  \u0915\u093F\u0932\u094D\u0938 \u0938\u0941\u0927\u093E\u0930\u0928\u0947, \u092F\
  \u093E \u0915\u0941\u091B \u0909\u092A\u092F\u094B\u0917\u0940 \u092C\u0928\u093E\
  \u0928\u0947 \u0915\u0947 \u0932\u093F\u090F \u0915\u0930\u0924\u0947 \u0939\u0948\
  \u0902\u0964"
lastmod: '2024-03-13T22:44:52.990648-06:00'
model: gpt-4-1106-preview
summary: "\u0928\u092F\u093E \u092A\u094D\u0930\u094B\u091C\u0947\u0915\u094D\u091F\
  \ \u0936\u0941\u0930\u0942 \u0915\u0930\u0928\u093E \u092E\u0924\u0932\u092C \u0915\
  \u094B\u0921 \u0915\u0940 \u090F\u0915 \u0928\u0908 \u0926\u0941\u0928\u093F\u092F\
  \u093E \u092C\u0928\u093E\u0928\u093E\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\
  \u0930\u093E\u092E\u0930 \u0907\u0938\u0947 \u0928\u090F \u0906\u0907\u0921\u093F\
  \u092F\u093E \u091F\u0947\u0938\u094D\u091F \u0915\u0930\u0928\u0947, \u0938\u094D\
  \u0915\u093F\u0932\u094D\u0938 \u0938\u0941\u0927\u093E\u0930\u0928\u0947, \u092F\
  \u093E \u0915\u0941\u091B \u0909\u092A\u092F\u094B\u0917\u0940 \u092C\u0928\u093E\
  \u0928\u0947 \u0915\u0947 \u0932\u093F\u090F \u0915\u0930\u0924\u0947 \u0939\u0948\
  \u0902\u0964."
title: "\u0928\u0908 \u092A\u0930\u093F\u092F\u094B\u091C\u0928\u093E \u0936\u0941\
  \u0930\u0942 \u0915\u0930\u0928\u093E"
weight: 1
---

## How to (कैसे करें):
```javascript
// Node.js पर नया प्रोजेक्ट बनाने के लिए:
const fs = require('fs');
const projectName = 'NewProject';

fs.mkdir(projectName, { recursive: true }, (err) => {
  if (err) throw err;
  console.log(`${projectName} directory created!`);
});

// package.json फाइल बनाएँ:
const packageJson = {
  name: projectName,
  version: '1.0.0',
  description: '',
  main: 'index.js',
  scripts: {
    test: 'echo "Error: no test specified" && exit 1'
  },
  author: '',
  license: 'ISC'
};

fs.writeFile(`${projectName}/package.json`, JSON.stringify(packageJson, null, 2), (err) => {
  if (err) throw err;
  console.log('package.json file created!');
});
```

## Deep Dive (गहराई से जानकारी):
नया JavaScript प्रोजेक्ट शुरू करते समय आपको कुछ बातों का ध्यान रखना होता है - कोड की स्ट्रक्चर, डिपेंडेंसी मैनेजमेंट, और प्रोजेक्ट की टेस्टिंग। पहले, सभी को अपने-अपने हिसाब से सेटअप करना पड़ता था, लेकिन आजकल टूल्स जैसे कि `npm` और `yarn` इस प्रक्रिया को बहुत आसान बना देते हैं। इनके साथ, आप मात्र कुछ कमांड्स के साथ एक स्टैंडर्ड प्रोजेक्ट तैयार कर सकते हैं और विभिन्न पैकेजेस जल्दी से इंस्टॉल कर सकते हैं।

डिपेंडेंसी मैनेजमेंट के लिए `package.json` का इस्तेमाल होता है, जोकि प्रोजेक्ट की जानकारी और इस्तेमाल किए गए पैकेजेस को ट्रैक करती है। इसमें उन पैकेजेस के वर्ज़न भी शामिल होते हैं जो प्रोजेक्ट के साथ काम करते हैं, और इसे `npm install` जैसे कमांड्स के जरिए मैनेज किया जाता है।

एक बार जब आपकी बेसिक सेटअप तैयार हो जाती है, तो आप अपना कोड लिखना शुरू कर सकते हैं। फिर स्क्रिप्ट्स लिखें, पैकेजेस इंस्टॉल करें, और आपका प्रोजेक्ट शेप लेने लगेगा।

## See Also (और भी जानकारी):
- [npm documentation](https://docs.npmjs.com/)
- [GitHub Guides](https://guides.github.com/)
- [JavaScript Info](https://javascript.info/)
