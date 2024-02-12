---
title:                "डायरेक्टरी मौजूद है या नहीं जाँचना"
aliases:
- /hi/typescript/checking-if-a-directory-exists/
date:                  2024-02-03T19:09:27.689764-07:00
model:                 gpt-4-0125-preview
simple_title:         "डायरेक्टरी मौजूद है या नहीं जाँचना"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/typescript/checking-if-a-directory-exists.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## क्या और क्यों?
TypeScript में यह जांचना कि कोई निर्देशिका मौजूद है या नहीं, फ़ाइल प्रबंधन कार्यों जैसे कि फ़ाइलों से पढ़ना या उनमें डेटा लिखना, के लिए आवश्यक है, यह सुनिश्चित करता है कि कार्यवाहियाँ केवल वैध निर्देशिकाओं पर ही की जाती हैं। यह क्रिया मौजूद न होने वाली निर्देशिकाओं को एक्सेस या मैनिप्युलेट करने का प्रयास करते समय उत्पन्न होने वाली त्रुटियों से बचने के लिए महत्वपूर्ण है।

## कैसे करें:

TypeScript को जब Node.js वातावरण में चलाया जाता है, तब यह आपको `fs` मॉड्यूल का उपयोग करके यह जांचने की अनुमति देता है कि कोई निर्देशिका मौजूद है या नहीं, जो `existsSync()` फंक्शन या एसिंक्रोनस `access()` फंक्शन को `constants.F_OK` के साथ संयुक्त करके प्रदान करता है।

### `fs.existsSync()` का उपयोग करते हुए:

```typescript
import { existsSync } from 'fs';

const directoryPath = './path/to/directory';

if (existsSync(directoryPath)) {
  console.log('निर्देशिका मौजूद है।');
} else {
  console.log('निर्देशिका मौजूद नहीं है।');
}
```

### `fs.access()` का उपयोग `fs.constants.F_OK` के साथ करते हुए:

```typescript
import { access, constants } from 'fs';

const directoryPath = './path/to/directory';

access(directoryPath, constants.F_OK, (err) => {
  if (err) {
    console.log('निर्देशिका मौजूद नहीं है।');
    return;
  }
  console.log('निर्देशिका मौजूद है।');
});
```

**दोनों तरीकों के लिए नमूना आउटपुट**, यह मानते हुए कि निर्देशिका मौजूद है:
```
निर्देशिका मौजूद है।
```

और अगर नहीं है तो:
```
निर्देशिका मौजूद नहीं है।
```

### तीसरे पक्ष की लाइब्रेरी - `fs-extra` का उपयोग करते हुए:

`fs-extra` एक लोकप्रिय तीसरे पक्ष की लाइब्रेरी है जो निर्मित `fs` मॉड्यूल को बढ़ाती है और अधिक सुविधाजनक फंक्शन्स प्रदान करती है।

```typescript
import { pathExists } from 'fs-extra';

const directoryPath = './path/to/directory';

pathExists(directoryPath).then(exists => {
  console.log(`निर्देशिका मौजूद है: ${exists}`);
});
```

**नमूना आउटपुट** जब निर्देशिका मौजूद होती है:
```
निर्देशिका मौजूद है: सही
```

और अगर नहीं है तो:
```
निर्देशिका मौजूद नहीं है: गलत
```
