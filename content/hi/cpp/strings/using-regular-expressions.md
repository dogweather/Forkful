---
aliases:
- /hi/cpp/using-regular-expressions/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:16:58.240463-07:00
description: "C++ \u092E\u0947\u0902 \u0928\u093F\u092F\u092E\u093F\u0924 \u0905\u092D\
  \u093F\u0935\u094D\u092F\u0915\u094D\u0924\u093F\u092F\u093E\u0901 \u0935\u0947\
  \ \u0935\u0930\u094D\u0923\u094B\u0902 \u0915\u0947 \u0905\u0928\u0941\u0915\u094D\
  \u0930\u092E \u0939\u094B\u0924\u0947 \u0939\u0948\u0902 \u091C\u094B \u090F\u0915\
  \ \u0916\u094B\u091C \u092A\u0948\u091F\u0930\u094D\u0928 \u0915\u094B \u092A\u0930\
  \u093F\u092D\u093E\u0937\u093F\u0924 \u0915\u0930\u0924\u0947 \u0939\u0948\u0902\
  , \u091C\u093F\u0928\u0915\u093E \u0909\u092A\u092F\u094B\u0917 \u0938\u094D\u091F\
  \u094D\u0930\u093F\u0902\u0917 \u092E\u093F\u0932\u093E\u0928 \u092F\u093E \u0939\
  \u0947\u0930\u092B\u0947\u0930 \u0915\u0947 \u0932\u093F\u090F \u0915\u093F\u092F\
  \u093E \u091C\u093E\u0924\u093E\u2026"
lastmod: 2024-02-18 23:09:03.871155
model: gpt-4-0125-preview
summary: "C++ \u092E\u0947\u0902 \u0928\u093F\u092F\u092E\u093F\u0924 \u0905\u092D\
  \u093F\u0935\u094D\u092F\u0915\u094D\u0924\u093F\u092F\u093E\u0901 \u0935\u0947\
  \ \u0935\u0930\u094D\u0923\u094B\u0902 \u0915\u0947 \u0905\u0928\u0941\u0915\u094D\
  \u0930\u092E \u0939\u094B\u0924\u0947 \u0939\u0948\u0902 \u091C\u094B \u090F\u0915\
  \ \u0916\u094B\u091C \u092A\u0948\u091F\u0930\u094D\u0928 \u0915\u094B \u092A\u0930\
  \u093F\u092D\u093E\u0937\u093F\u0924 \u0915\u0930\u0924\u0947 \u0939\u0948\u0902\
  , \u091C\u093F\u0928\u0915\u093E \u0909\u092A\u092F\u094B\u0917 \u0938\u094D\u091F\
  \u094D\u0930\u093F\u0902\u0917 \u092E\u093F\u0932\u093E\u0928 \u092F\u093E \u0939\
  \u0947\u0930\u092B\u0947\u0930 \u0915\u0947 \u0932\u093F\u090F \u0915\u093F\u092F\
  \u093E \u091C\u093E\u0924\u093E\u2026"
title: "\u0930\u0947\u0917\u0941\u0932\u0930 \u090F\u0915\u094D\u0938\u092A\u094D\u0930\
  \u0947\u0936\u0928\u094D\u0938 \u0915\u093E \u0909\u092A\u092F\u094B\u0917 \u0915\
  \u0930\u0928\u093E"
---

{{< edit_this_page >}}

## क्या और क्यों?
C++ में नियमित अभिव्यक्तियाँ वे वर्णों के अनुक्रम होते हैं जो एक खोज पैटर्न को परिभाषित करते हैं, जिनका उपयोग स्ट्रिंग मिलान या हेरफेर के लिए किया जाता है। प्रोग्रामर इनका उपयोग इनपुट की वैधता सत्यापित करने, स्ट्रिंग्स के भीतर घटनाओं की खोज, या स्ट्रिंग्स को टोकन में विभाजित करने जैसे कार्यों के लिए करते हैं, जिससे ये पाठ संसाधन के लिए एक अनिवार्य उपकरण बनते हैं।

## कैसे करें:
C++11 में मानक पुस्तकालय, `<regex>`, में नियमित अभिव्यक्तियों के लिए समर्थन पेश किया गया, जो स्ट्रिंग खोज और हेरफेर के लिए एक मजबूत ढांचा प्रदान करता है। यहाँ एक बुनियादी उदाहरण है जो एक स्ट्रिंग में एक पैटर्न की खोज के लिए नियमित अभिव्यक्तियों का उपयोग करता है:

```cpp
#include <iostream>
#include <regex>

int main() {
    std::string target = "Hello, my email is example@example.com";
    std::regex email_pattern(R"(\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}\b)");

    if (std::regex_search(target, email_pattern)) {
        std::cout << "Email found!" << std::endl;
    } else {
        std::cout << "No email found." << std::endl;
    }

    return 0;
}
```
**नमूना आउटपुट**
```
Email found!
```

अधिक जटिल हेरफेर के लिए, जैसे कि स्ट्रिंग्स के भीतर पैटर्न को बदलना, C++ की नियमित अभिव्यक्तियाँ बहुत सहायक हो सकती हैं:

```cpp
#include <iostream>
#include <regex>

int main() {
    std::string text = "The rain in Spain falls mainly in the plain.";
    std::regex vowel_regex("([aeiou])");

    std::string replaced_text = std::regex_replace(text, vowel_regex, "*");
    std::cout << replaced_text << std::endl;

    return 0;
}
```
**नमूना आउटपुट**
```
Th* r**n *n Sp**n f*lls m**nly *n th* pl**n.
```

मानक पुस्तकालय से आगे तलाशने वाले प्रोग्रामरों के लिए, बूस्ट रेगेक्स पुस्तकालय (`boost/regex.hpp`) एक लोकप्रिय तृतीय-पक्ष विकल्प है जो जटिल पैटर्न या व्यापक डेटा प्रसंस्करण के लिए उन्नत रेगेक्स क्षमताओं और प्रदर्शन अनुकूलन प्रदान करता है:

```cpp
#include <iostream>
#include <boost/regex.hpp>

int main() {
    std::string s = "Boost libraries are fun!";
    boost::regex expr("(\\w+)\\s(libraries)"); // "Boost libraries" से मिलान
    std::string fmt("GNU \\1"); // "GNU Boost" से बदलें

    std::string result = boost::regex_replace(s, expr, fmt);
    std::cout << result << std::endl;

    return 0;
}
```
**नमूना आउटपुट**
```
GNU Boost are fun!
```

ये उदाहरण C++ की नियमित अभिव्यक्तियों के साथ क्षमताओं की सतह को खुरचते हैं, जो मानक पुस्तकालय का उपयोग करके या बूस्ट की शक्तिशाली रेगेक्स कार्यान्वयन द्वारा प्रबलित, बुनियादी खोजों, पैटर्न मिलान, और प्रतिस्थापनों का प्रदर्शन करते हैं।
