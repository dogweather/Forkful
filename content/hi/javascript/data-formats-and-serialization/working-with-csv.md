---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:21:14.641385-07:00
description: "JavaScript \u092E\u0947\u0902 CSV (Comma-Separated Values) \u0915\u0947\
  \ \u0938\u093E\u0925 \u0915\u093E\u092E \u0915\u0930\u0928\u093E \u0915\u093E \u0905\
  \u0930\u094D\u0925 \u0939\u0948 CSV \u092B\u093E\u0907\u0932\u094B\u0902 \u0915\u094B\
  \ \u092A\u093E\u0930\u094D\u0938 \u0915\u0930\u0928\u093E \u092F\u093E \u0909\u0924\
  \u094D\u092A\u0928\u094D\u0928 \u0915\u0930\u0928\u093E \u0924\u093E\u0915\u093F\
  \ \u092C\u093E\u0939\u0930\u0940 \u0938\u094D\u0930\u094B\u0924\u094B\u0902 \u0938\
  \u0947 \u0924\u093E\u0932\u093F\u0915\u093E \u0921\u0947\u091F\u093E \u092A\u094D\
  \u0930\u093E\u092A\u094D\u0924\u2026"
lastmod: '2024-03-13T22:44:53.028123-06:00'
model: gpt-4-0125-preview
summary: "JavaScript \u092E\u0947\u0902 CSV (Comma-Separated Values) \u0915\u0947\
  \ \u0938\u093E\u0925 \u0915\u093E\u092E \u0915\u0930\u0928\u093E \u0915\u093E \u0905\
  \u0930\u094D\u0925 \u0939\u0948 CSV \u092B\u093E\u0907\u0932\u094B\u0902 \u0915\u094B\
  \ \u092A\u093E\u0930\u094D\u0938 \u0915\u0930\u0928\u093E \u092F\u093E \u0909\u0924\
  \u094D\u092A\u0928\u094D\u0928 \u0915\u0930\u0928\u093E \u0924\u093E\u0915\u093F\
  \ \u092C\u093E\u0939\u0930\u0940 \u0938\u094D\u0930\u094B\u0924\u094B\u0902 \u0938\
  \u0947 \u0924\u093E\u0932\u093F\u0915\u093E \u0921\u0947\u091F\u093E \u092A\u094D\
  \u0930\u093E\u092A\u094D\u0924 \u0915\u093F\u092F\u093E \u091C\u093E \u0938\u0915\
  \u0947 \u092F\u093E \u0905\u0928\u094D\u092F \u092A\u094D\u0930\u094B\u0917\u094D\
  \u0930\u093E\u092E\u094B\u0902 \u092E\u0947\u0902 \u0909\u092A\u092F\u094B\u0917\
  \ \u0915\u0947 \u0932\u093F\u090F \u0921\u0947\u091F\u093E \u0928\u093F\u0930\u094D\
  \u092F\u093E\u0924 \u0915\u093F\u092F\u093E \u091C\u093E \u0938\u0915\u0947\u0964\
  \ \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930 \u0907\u0938\u0947\
  \ \u0907\u0938\u0932\u093F\u090F \u0915\u0930\u0924\u0947 \u0939\u0948\u0902 \u0915\
  \u094D\u092F\u094B\u0902\u0915\u093F \u092F\u0939 \u090F\u092A\u094D\u0932\u0940\
  \u0915\u0947\u0936\u0928\u094B\u0902, \u0921\u093E\u091F\u093E\u092C\u0947\u0938\
  \u094B\u0902, \u0914\u0930 \u0938\u093F\u0938\u094D\u091F\u092E\u094B\u0902 \u0915\
  \u0947 \u092C\u0940\u091A \u0906\u0938\u093E\u0928, \u0939\u0932\u094D\u0915\u0947\
  \ \u0921\u0947\u091F\u093E \u0906\u0926\u093E\u0928-\u092A\u094D\u0930\u0926\u093E\
  \u0928 \u0915\u094B \u0938\u0915\u094D\u0937\u092E \u092C\u0928\u093E\u0924\u093E\
  \ \u0939\u0948 \u091C\u0939\u093E\u0901 JSON \u091C\u0948\u0938\u0947 \u0905\u0927\
  \u093F\u0915 \u091C\u091F\u093F\u0932 \u092A\u094D\u0930\u093E\u0930\u0942\u092A\
  \u094B\u0902 \u0915\u0940 \u0906\u0935\u0936\u094D\u092F\u0915\u0924\u093E \u0928\
  \u0939\u0940\u0902 \u0939\u094B\u0924\u0940 \u0939\u0948\u0964."
title: "CSV \u0915\u0947 \u0938\u093E\u0925 \u0915\u093E\u092E \u0915\u0930\u0928\u093E"
weight: 37
---

## कैसे करें:
JavaScript में बिल्ट-इन CSV पार्सिंग या स्ट्रिंगिफाई करने की कार्यक्षमता नहीं है, जैसा कि इसमें JSON के साथ है। हालांकि, आप या तो कच्ची JavaScript का उपयोग करके सरल कार्यों के लिए या `PapaParse` जैसे शक्तिशाली पुस्तकालयों का लाभ उठाकर जटिल परिदृश्यों के लिए CSV डेटा को आसानी से प्रबंधित कर सकते हैं।

### कच्ची JavaScript के साथ बुनियादी पार्सिंग
एक सरल CSV स्ट्रिंग को ऑब्जेक्ट्स की एक एरे में पार्स करने के लिए:

```javascript
const csv = `name,age,city
John,23,New York
Jane,28,Los Angeles`;

function parseCSV(csv) {
  const lines = csv.split("\n");
  const result = [];
  const headers = lines[0].split(",");

  for (let i = 1; i < lines.length; i++) {
    const obj = {};
    const currentline = lines[i].split(",");
    
    for (let j = 0; j < headers.length; j++) {
      obj[headers[j]] = currentline[j];
    }
    result.push(obj);
  }
  
  return result;
}

console.log(parseCSV(csv));
```
आउटपुट:

```
[
  { name: 'John', age: '23', city: 'New York' },
  { name: 'Jane', age: '28', city: 'Los Angeles' }
]
```

### कच्ची JavaScript के साथ CSV में बुनियादी उत्पादन
ऑब्जेक्ट्स की एक एरे को CSV स्ट्रिंग में परिवर्तित करने के लिए:

```javascript
const data = [
  { name: 'John', age: 23, city: 'New York' },
  { name: 'Jane', age: 28, city: 'Los Angeles' }
];

function arrayToCSV(arr) {
  const csv = arr.map(row => 
    Object.values(row).join(',')
  ).join('\n');
  
  return csv;
}

console.log(arrayToCSV(data));
```

आउटपुट:

```
John,23,New York
Jane,28,Los Angeles
```

### जटिल CSV कार्यों के लिए PapaParse का उपयोग
अधिक जटिल परिदृश्यों के लिए, `PapaParse` एक दृढ़ पुस्तकालय है जो स्ट्रीम्स, वर्कर्स, और विशाल फाइलों को संभालने के विकल्पों के साथ CSV फाइलों को पार्स करने और स्ट्रिंगिफाई करने के लिए उपयुक्त है।

PapaParse के साथ CSV फाइल या स्ट्रिंग को पार्स करना:

```javascript
// अपने प्रोजेक्ट में PapaParse जोड़ने के बाद
const Papa = require('papaparse');
const csv = `name,age,city
John,23,New York
Jane,28,Los Angeles`;

Papa.parse(csv, {
  complete: function(results) {
    console.log("Parsed:", results.data);
  }
});
```

उत्पन्न करता है:

```
Parsed: [
  ["name", "age", "city"],
  ["John", "23", "New York"],
  ["Jane", "28", "Los Angeles"]
]
```

PapaParse के साथ एक एरे को CSV स्ट्रिंग में परिवर्तित करना:

```javascript
const data = [
  { name: 'John', age: 23, city: 'New York' },
  { name: 'Jane', age: 28, city: 'Los Angeles' }
];

console.log(Papa.unparse(data));
```

उत्पन्न करता है:

```
name,age,city
John,23,New York
Jane,28,Los Angeles
```

ये उदाहरण JavaScript में बुनियादी और उन्नत CSV हैंडलिंग को दर्शाते हैं, वेब अप्लिकेशनों और उससे आगे में आसान डेटा एक्सचेंज को सक्षम बनाते हैं।
