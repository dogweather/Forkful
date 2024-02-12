---
title:                "JSON के साथ काम करना"
aliases:
- hi/c/working-with-json.md
date:                  2024-02-03T18:13:14.569558-07:00
model:                 gpt-4-0125-preview
simple_title:         "JSON के साथ काम करना"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/c/working-with-json.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## क्या और क्यों?

C में JSON (JavaScript Object Notation) के साथ काम करना इसके डेटा संरचनाओं को पार्स करने, उत्पन्न करने, और संशोधित करने से संबंधित है। प्रोग्रामर ऐसा वेब सेवाओं के साथ संवाद स्थापित करने, डेटा संग्रहण, या हल्के और मानव-पठनीय प्रारूप में कॉन्फिग फाइल्स के लिए यह काम करते हैं।

## कैसे करें:

C में JSON के साथ काम करने के लिए, आप आमतौर पर `jansson` या `json-c` जैसी लाइब्रेरी का उपयोग करेंगे क्योंकि C में JSON के लिए निर्मित समर्थन का अभाव है। यहाँ, हम `jansson` पर ध्यान केंद्रित करेंगे इसकी उपयोग में आसानी और सक्रिय रख-रखाव के कारण। पहले, लाइब्रेरी को स्थापित करें (उदाहरण के लिए, Ubuntu पर `apt` जैसे पैकेज मैनेजर का उपयोग करके: `sudo apt-get install libjansson-dev`).

आइए एक JSON स्ट्रिंग को पार्स करना और उसकी सामग्री तक पहुँचना शुरू करें:

```c
#include <jansson.h>
#include <stdio.h>

int main() {
    const char *json_string = "{\"name\":\"John Doe\",\"age\":30}";
    json_error_t error;
    json_t *root = json_loads(json_string, 0, &error);
    
    if(!root) {
        fprintf(stderr, "error: on line %d: %s\n", error.line, error.text);
        return 1;
    }
    
    const char *name;
    int age;
    json_unpack(root, "{s:s, s:i}", "name", &name, "age", &age);
    
    printf("Name: %s\nAge: %d\n", name, age);
    
    json_decref(root);
    return 0;
}
```

नमूना आउटपुट:
```
Name: John Doe
Age: 30
```

आगे, एक JSON ऑब्जेक्ट बनाना और उसे आउटपुट करना:

```c
#include <jansson.h>
#include <stdio.h>

int main() {
    json_t *root = json_object();
    json_object_set_new(root, "name", json_string("Jane Doe"));
    json_object_set_new(root, "age", json_integer(25));
    
    char *json_dump = json_dumps(root, JSON_ENCODE_ANY);
    printf("%s\n", json_dump);
    
    free(json_dump);
    json_decref(root);
    return 0;
}
```

नमूना आउटपुट:
```
{"name": "Jane Doe", "age": 25}
```

ये उदाहरण एक JSON स्ट्रिंग को लोड करने, इसके मूल्यों को अनपैक करने, एक नया JSON ऑब्जेक्ट बनाने, और फिर इसे स्ट्रिंग के रूप में आउटपुट करने की मूल बातों का प्रदर्शन करते हैं।

## गहराई में

C में JSON के साथ काम करने की आवश्यकता वेब के JSON को डेटा इंटरचेंज के लिए प्राथमिक प्रारूप के रूप में अपनाने से उत्पन्न हुई है। JSON की सादगी और कार्यक्षमता ने इसे XML को जल्दी से प्रतिस्थापित कर दिया, भले ही C में शुरू में JSON संचालन के लिए सीधा समर्थन न हो। प्रारंभिक समाधानों में मैनुअल स्ट्रिंग मैनिपुलेशन शामिल था - जो की त्रुटि-प्रवण और अकुशल था। `jansson` और `json-c` जैसी लाइब्रेरी इस अंतराल को भरने के लिए सामने आईं, JSON पार्सिंग, निर्माण और सीरियलाइज़ेशन के लिए मजबूत APIs प्रदान करती हैं।

`jansson` जहां आसानी और उपयोग में सादगी प्रदान करता है, `json-c` उन लोगों के लिए अपील कर सकता है जो व्यापक फीचर सेट की तलाश में हैं। फिर भी, C++ में पार्सिंग लाइब्रेरीज जैसे विकल्प अधिक परिष्कृत अमूर्तताएं प्रदान करते हैं, धन्यवाद उस भाषा की अधिक जटिल डेटा संरचनाओं और मानक पुस्तकालय समर्थन के लिए। हालाँकि, जब ऐसे वातावरण में काम किया जाता है जहाँ C पसंदीदा या आवश्यक भाषा होती है - जैसे कि एम्बेडेड सिस्टम्स में या मौजूदा C लाइब्रेरीज के साथ इंटरफेसिंग करते समय - `jansson` या `json-c` का उपयोग अनिवार्य हो जाता है।

यह भी उल्लेखनीय है कि C में JSON के साथ काम करना स्मृति प्रबंधन की एक गहरी समझ में शामिल है, क्योंकि ये लाइब्रेरी अक्सर गतिशील रूप से आवंटित ऑब्जेक्ट्स को लौटाती हैं जिन्हें स्पष्ट रूप से मुक्त करने की आवश्यकता होती है। यह प्रोग्रामरों को स्मृति रिसाव को रोकने की महत्वपूर्ण आवश्यकता के साथ सुविधा के संतुलन बनाने की चुनौती देता है, C कोड तैयार करने का एक महत्वपूर्ण पहलू है।
