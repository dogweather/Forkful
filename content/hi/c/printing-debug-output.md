---
title:                "डीबग आउटपुट प्रिंट करना"
html_title:           "Gleam: डीबग आउटपुट प्रिंट करना"
simple_title:         "डीबग आउटपुट प्रिंट करना"
programming_language: "C"
category:             "C"
tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/c/printing-debug-output.md"
---

{{< edit_this_page >}}

# डिबग आउटपुट प्रिंट करना: एक विस्तृत मार्गदर्शन

## क्या और क्यों?
डिबग आउटपुट प्रिंट करना मतलब है कि हमारे कोड के विभिन्न हिस्सों से जानकारी प्राप्त करना। प्रोग्रामर निर्धारित त्रुटियों के निवारण और प्रदर्शन मुद्दों का पता लगाने के लिए इसका उपयोग करते हैं।

## कैसे करें:
```C
#include<stdio.h>

int main() {
   int i = 5; 
   printf("Debug: i = %d\n", i); // Printing debug output
   return 0;
}
```
उपरोक्त कोड चलाने से निम्नलिखित आउटपुट मिलेगा:

```C
Debug: i = 5
```
इस प्रकार, आप अपने कोड में डिबग संदेश प्रिंट कर सकते हैं।

## गहराई में:
HISTORY: डिबग की तकनीक तब से मौजूद है जब से कंप्यूटर कोडिंग की शुरुआत हुई थी। यह एक महत्वपूर्ण उपकरण है जो विकासकर्ताओं को बग्स को शनाई करने में मदद करता है। 

ALTERNATIVES: `printf` इस्तेमाल करने के अलावा, आप लोग फ़ाइलों और अन्य डिबग उपकरण का भी उपयोग कर सकते हैं। 

IMPLEMENTATION: डिबग संदेशों को प्रिंट करने के लिए, `printf` फ़ंक्शन हमें `%d`, `%s`, इत्यादि जैसे फॉर्मैट्स की अनुमति देता है जिससे हम भिन्न भिन्न प्रकार की जानकारी प्रिंट कर सकते हैं। 

## अधिक देखें:
1. [The Debugging Process](https://www.gnu.org/software/libc/manual/html_node/The-Debugging-Process.html)
2. [What are debugging skills and do you have them?](https://www.bmc.com/blogs/debugging-programming/)
3. [Debugging in C programming](https://beginnersbook.com/2014/01/debugging-in-c-programming)