---
title:                "एक अस्थायी फ़ाइल बनाना"
html_title:           "Arduino: एक अस्थायी फ़ाइल बनाना"
simple_title:         "एक अस्थायी फ़ाइल बनाना"
programming_language: "Javascript"
category:             "Javascript"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/javascript/creating-a-temporary-file.md"
---

{{< edit_this_page >}}

## क्या और क्यों?

अस्थायी फ़ाइल बनाना एक प्रोग्रामिंग कार्रवाई है जिसे हम तब करते हैं जब हमें कोई डेटा स्थायी रूप से संग्रहित करने की जरूरत नहीं होती, लेकिन हमें उसे अस्थायी रूप से संग्रहित या बचा कर रखने की आवश्यकता होती है। यह डेटा को अस्थायी रूप से संग्रहित करने वाला एक सुरक्षित तरीका होता है। 

## कैसे करें: 

आइए देखें कि कैसे हम कोई अस्थायी फ़ाइल JavaScript में बना सकते हैं।

```Javascript
const fs = require('fs');

fs.mkdtemp('/tmp/foo-', (err, folder) => {
    if (err) throw err;
    console.log('Folder:', folder);
});
```

इस कोड का उत्पादन `/tmp/foo-RANDOM` जैसा दिखाई देगा, यहाँ RANDOM किसी अद्वितीय संख्या होती है।

## गहरी डाइव:

- इतिहासिक प्रक्षेपण: अस्थायी फ़ाइलें UNIX सिस्टम में पहली बार पेश की गईं। इसे सभी प्रमुख मॉडर्न ऑपरेटिंग सिस्टम्स जैसे Windows, Linux और MacOS द्वारा समर्थित किया गया है। 
- विकल्प: अगर आपको केवल डेटा को अस्थायी रूप से बचाने की आवश्यकता है, तो आपके पास ऑप्शन हैं जैसे रैमडिस्क या RAM डिस्क, जिसे एक "वर्चुअल" या "RAM" ड्राइव के रूप में भी जाना जाता है।
- कार्यान्वयन विवरण: `fs.mkdtemp` एक अस्थायी डायरेक्टरी बनाता है जिसे एक सुरक्षित तरीके से बनाया गया है। यह क्योंकि यह फ़ंक्शन ठीक उस समय डायरेक्टरी बनाता है जब यह अपने नाम की खोज करता है, जिससे रेस कंडिशन से बचा जाता है।

## देखें भी:

- अधिक जानकारी के लिए, आप [Node.js fs.mkdtemp() डॉक्युमेंटेशन](https://nodejs.org/api/fs.html#fs_fs_mkdtemp_prefix_options_callback) को देख सकते हैं।
- एक विस्तृत तुलनात्मक मार्गदर्शन के लिए, [Ramdisk vs Temporary File](https://www.novell.com/coolsolutions/appnote/19386.html) पढ़ें।