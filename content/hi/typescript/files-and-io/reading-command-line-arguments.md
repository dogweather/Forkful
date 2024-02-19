---
aliases:
- /hi/typescript/reading-command-line-arguments/
date: 2024-01-20 17:57:35.680899-07:00
description: "\u0915\u092E\u093E\u0902\u0921 \u0932\u093E\u0907\u0928 \u0906\u0930\
  \u094D\u0917\u094D\u092F\u0942\u092E\u0947\u0902\u091F \u092A\u0922\u093C\u0928\u093E\
  \ \u092F\u093E\u0928\u0940 \u0915\u092E\u093E\u0902\u0921 \u0932\u093E\u0907\u0928\
  \ \u0938\u0947 \u0907\u0928\u092A\u0941\u091F \u0932\u0947\u0928\u093E\u0964 \u092A\
  \u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930\u094D\u0938 \u0907\u0938\u0947\
  \ \u0907\u0938\u0932\u093F\u090F \u0915\u0930\u0924\u0947 \u0939\u0948\u0902, \u0915\
  \u094D\u092F\u094B\u0902\u0915\u093F \u092F\u0939 \u091C\u093C\u0930\u0942\u0930\
  \u0940 \u0939\u094B\u0924\u093E \u0939\u0948 \u0915\u093E\u0930\u094D\u092F\u0915\
  \u094D\u0930\u092E \u0915\u094B \u092B\u094D\u0932\u0947\u0915\u094D\u0938\u093F\
  \u092C\u0932 \u092C\u0928\u093E\u0928\u0947 \u0915\u0947\u2026"
lastmod: 2024-02-18 23:09:02.907611
model: gpt-4-1106-preview
summary: "\u0915\u092E\u093E\u0902\u0921 \u0932\u093E\u0907\u0928 \u0906\u0930\u094D\
  \u0917\u094D\u092F\u0942\u092E\u0947\u0902\u091F \u092A\u0922\u093C\u0928\u093E\
  \ \u092F\u093E\u0928\u0940 \u0915\u092E\u093E\u0902\u0921 \u0932\u093E\u0907\u0928\
  \ \u0938\u0947 \u0907\u0928\u092A\u0941\u091F \u0932\u0947\u0928\u093E\u0964 \u092A\
  \u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930\u094D\u0938 \u0907\u0938\u0947\
  \ \u0907\u0938\u0932\u093F\u090F \u0915\u0930\u0924\u0947 \u0939\u0948\u0902, \u0915\
  \u094D\u092F\u094B\u0902\u0915\u093F \u092F\u0939 \u091C\u093C\u0930\u0942\u0930\
  \u0940 \u0939\u094B\u0924\u093E \u0939\u0948 \u0915\u093E\u0930\u094D\u092F\u0915\
  \u094D\u0930\u092E \u0915\u094B \u092B\u094D\u0932\u0947\u0915\u094D\u0938\u093F\
  \u092C\u0932 \u092C\u0928\u093E\u0928\u0947 \u0915\u0947\u2026"
title: "\u0915\u092E\u093E\u0902\u0921 \u0932\u093E\u0907\u0928 \u0906\u0930\u094D\
  \u0917\u0941\u092E\u0947\u0902\u091F\u094D\u0938 \u092A\u0922\u093C\u0928\u093E"
---

{{< edit_this_page >}}

## What & Why? (क्या और क्यों?)
कमांड लाइन आर्ग्यूमेंट पढ़ना यानी कमांड लाइन से इनपुट लेना। प्रोग्रामर्स इसे इसलिए करते हैं, क्योंकि यह ज़रूरी होता है कार्यक्रम को फ्लेक्सिबल बनाने के लिए।

## How to: (कैसे करें:)
TypeScript में कमांड लाइन आर्ग्यूमेंट पढ़ने के लिए `process.argv` एरे का इस्तेमाल करते हैं। ये बेसिक उदाहरण दिखाता है:

```TypeScript
// filename: greet.ts
const args = process.argv.slice(2); // पहले दो एलीमेंट्स को हटाता हैं
console.log(`नमस्ते ${args[0]}!`);
```

कमांड लाइन से इसे ऐसे चलाएं:

```bash
$ tsc greet.ts
$ node greet.js John
नमस्ते John!
```

## Deep Dive (गहराई से जानकारी)
पहले लोग बहुत सारे टूल्स इस्तेमाल करते थे, पर `process.argv` डायरेक्ट Node.js से आ रहा है।

बेहतर समझ और एरर हैंडलिंग के लिए `yargs` या `commander` जैसे लाइब्रेरीज का भी इस्तेमाल होता है।

TypeScript में interface या class के साथ types को डिफाइन करके आर्ग्यूमेंट्स की वैलिडीटी चेक कर सकते हैं। जैसे:

```TypeScript
interface CommandLineOptions {
  name: string;
  // आप और भी ऑप्शन्स ऐड कर सकते हैं।
}

// ...कोड के बाकी हिस्से में आप चेक कर सकते हैं कि 'CommandLineOptions' के तहत वैल्यूज सही हैं या नहीं।
```

## See Also (देखने के लिए)
- Node.js `process.argv` documentation: [Node.js Docs](https://nodejs.org/docs/latest/api/process.html#process_process_argv)
- `yargs` library: [yargs GitHub](https://github.com/yargs/yargs)
- `commander` library: [Commander GitHub](https://github.com/tj/commander.js)

प्रोग्रामिंग की दुनिया में और सीखने के लिए इन लिंक्स को चेक करते रहें।
