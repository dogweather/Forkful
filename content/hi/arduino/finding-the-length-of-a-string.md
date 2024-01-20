---
title:                "स्ट्रिंग की लंबाई पता करना"
html_title:           "C++: स्ट्रिंग की लंबाई पता करना"
simple_title:         "स्ट्रिंग की लंबाई पता करना"
programming_language: "Arduino"
category:             "Arduino"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/arduino/finding-the-length-of-a-string.md"
---

{{< edit_this_page >}}

## क्या और क्यों?

`StringLength` एक ऐसी प्रक्रिया है, जिसमें हम एक विचारधारा (string) में कितने अक्षर हैं, यह जानते हैं। यह प्रोग्रामर्स के लिए उपयोगी होता है, क्योंकि यह अक्सर यह निर्धारित करने में आवश्यक होता है कि क्या कुछ विचारधाराएं (strings) एक समान हैं, या फिर इनकी लंबाई में अंतर है।

## कैसे:

इसे समझने के लिए, आप `length()` फ़ंक्शन का उपयोग कर सकते हैं।

```Arduino
void setup() {
  Serial.begin(9600);
  String myString = "अरुडिनो सीखना मजेदार है!";
  Serial.println(myString.length());
}
```
यह प्रोग्राम `"अरुडिनो सीखना मजेदार है!"` वाली स्ट्रिंग की लंबाई के संख्यात्मक मान को प्रिंट करेगा।


## गहरी डाइव:

अरुडिनो में स्ट्रिंग की लंबाई निर्धारित करने के लिए `length()` फ़ंक्शन का इतना बड़ा प्रयोग हो रहा है क्योंकि यह बहुत प्रभावी और सरल है। फ़ंक्शन यथासंभव समय के भीतर स्ट्रिंग की लंबाई को वापस करते हैं, जो कि बहुत आवश्यक हो सकता है जब आपको त्वरित निर्णय लेना हो।

इसके विकल्प में स्ट्रिंग संरचना को मैन्युअल रूप से पढ़ने का कार्य शामिल है, लेकिन यह काफी कम निर्दिष्ट हो सकता है और इसमें अतिरिक्त समय लगता है।

`length()` फ़ंक्शन, अन्य मेथड्स की तुलना में,तात्कालिक संख्या प्रदान कर सकता है जिसे प्रोग्राम को आसानी से प्रयोग करने में काम में लिया जा सकता है।

## देखे भी:

- [Arduino String Reference](https://www.arduino.cc/reference/en/language/variables/data-types/string/functions/length/)
- [Arduino String Functions](https://www.arduino.cc/reference/en/language/variables/data-types/string/functions/)