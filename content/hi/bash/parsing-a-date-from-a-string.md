---
title:                "एक स्ट्रिंग से तारीख पार्स करना"
html_title:           "C++: एक स्ट्रिंग से तारीख पार्स करना"
simple_title:         "एक स्ट्रिंग से तारीख पार्स करना"
programming_language: "Bash"
category:             "Bash"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/bash/parsing-a-date-from-a-string.md"
---

{{< edit_this_page >}}

## क्या और क्यों?

डेट पार्सिंग, अगर सीधे अर्थ में बोले तो, एक दिनांक को एक स्ट्रिंग (वर्णमाला) से निकालने का एक तरीका है। यह तब आवश्यक होता है जब प्रोग्रामर्स को एक डेटा को किसी निश्चित स्वरूप में अवलम्बित करने की आवश्यकता हो, ताकि उसे सही ढंग से प्रोसेस किया जा सकें। 

## कैसे करे:

Bash shell script में तारीख पार्स करने का एक उदाहरण दिया गया है:

```Bash
#!/bin/bash
string="2022-03-01T12:30:45Z"
date -d "$string" 
```

इसका आउटपुट दिखाई देगा कुछ इस प्रकार:

```Bash
Tue Mar 1 12:30:45 UTC 2022
```

## गहराई की जांच

Bash scripting में दिनांक पार्सिंग का इतिहास बहुत ही रोचक और महत्वपूर्ण है, जिसने प्रोग्रामर्स को डेटा मैनिपुलेशन में काफी मदद की है। विचार धारा-date utility का उपयोग करने के बावजूद, आप ऐन्सी (C) लाइब्रेरी के strftime और strptime फंक्शन का उपयोग कर सकते हैं। यह बात ध्यान देने योग्य है कि date utility POSIX स्टैंडर्ड में शामिल नहीं है इसलिए इसका व्यवहार विभिन्न सिस्टमों पर अलग हो सकता है। 

## और भी देखें

अगर आप और अधिक जानकारी प्राप्त करना चाहते हैं, तो देखें - 

1. [Bash Manual](https://www.gnu.org/software/bash/manual/bash.html)
2. [Date Parsing in Bash](https://www.linuxjournal.com/content/working-dates-bash)
  
इन लिंक्स में आपको Bash द्वारा डेट पार्सिंग के बारे में और विस्तार से जानकारी मिलेगी।