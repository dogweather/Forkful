---
date: 2024-01-20 17:38:53.997156-07:00
description: "\u0938\u094D\u091F\u094D\u0930\u093F\u0902\u0917 \u0915\u094B \u0932\
  \u094B\u0905\u0930 \u0915\u0947\u0938 \u092E\u0947\u0902 \u092C\u0926\u0932\u0928\
  \u0947 \u0938\u0947 \u092E\u0924\u0932\u092C \u0939\u0948 \u0939\u0930 \u0905\u0915\
  \u094D\u0937\u0930 \u0915\u094B \u091B\u094B\u091F\u0947 (\u0932\u094B\u0905\u0930\
  \u0915\u0947\u0938) \u0905\u0915\u094D\u0937\u0930\u094B\u0902 \u092E\u0947\u0902\
  \ \u092A\u0930\u093F\u0935\u0930\u094D\u0924\u093F\u0924 \u0915\u0930\u0928\u093E\
  \u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930\u094D\u0938\
  \ \u092F\u0939 \u0907\u0938\u0932\u093F\u090F \u0915\u0930\u0924\u0947 \u0939\u0948\
  \u0902 \u0924\u093E\u0915\u093F \u0938\u094D\u091F\u094D\u0930\u093F\u0902\u0917\
  \ \u092A\u094D\u0930\u094B\u0938\u0947\u0938\u093F\u0902\u0917\u2026"
lastmod: '2024-03-13T22:44:52.822432-06:00'
model: gpt-4-1106-preview
summary: "\u0938\u094D\u091F\u094D\u0930\u093F\u0902\u0917 \u0915\u094B \u0932\u094B\
  \u0905\u0930 \u0915\u0947\u0938 \u092E\u0947\u0902 \u092C\u0926\u0932\u0928\u0947\
  \ \u0938\u0947 \u092E\u0924\u0932\u092C \u0939\u0948 \u0939\u0930 \u0905\u0915\u094D\
  \u0937\u0930 \u0915\u094B \u091B\u094B\u091F\u0947 (\u0932\u094B\u0905\u0930\u0915\
  \u0947\u0938) \u0905\u0915\u094D\u0937\u0930\u094B\u0902 \u092E\u0947\u0902 \u092A\
  \u0930\u093F\u0935\u0930\u094D\u0924\u093F\u0924 \u0915\u0930\u0928\u093E\u0964\
  \ \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930\u094D\u0938 \u092F\
  \u0939 \u0907\u0938\u0932\u093F\u090F \u0915\u0930\u0924\u0947 \u0939\u0948\u0902\
  \ \u0924\u093E\u0915\u093F \u0938\u094D\u091F\u094D\u0930\u093F\u0902\u0917 \u092A\
  \u094D\u0930\u094B\u0938\u0947\u0938\u093F\u0902\u0917 \u092E\u0947\u0902 \u0938\
  \u093E\u092E\u093E\u0928\u094D\u092F\u0940\u0915\u0930\u0923 \u0939\u094B \u0938\
  \u0915\u0947 \u0914\u0930 \u0924\u0941\u0932\u0928\u093E \u0915\u0930\u0928\u093E\
  \ \u0906\u0938\u093E\u0928 \u0939\u094B \u091C\u093E\u090F\u0964."
title: "\u0938\u094D\u091F\u094D\u0930\u093F\u0902\u0917 \u0915\u094B \u091B\u094B\
  \u091F\u0947 \u0905\u0915\u094D\u0937\u0930\u094B\u0902 \u092E\u0947\u0902 \u092A\
  \u0930\u093F\u0935\u0930\u094D\u0924\u093F\u0924 \u0915\u0930\u0928\u093E"
weight: 4
---

## How to: (कैसे करें:)
```C++
#include <iostream>
#include <algorithm>
#include <cctype>

int main() {
    std::string str = "नमस्ते World!";
    std::transform(str.begin(), str.end(), str.begin(), 
    [](unsigned char c){ return std::tolower(c); });
    
    std::cout << str << std::endl;
    return 0;
}
```
उदाहरण का आउटपुट: `नमस्ते world!`

## Deep Dive (गहराई से जानकारी)
पहले के जमाने में स्ट्रिंग को manipulate करने के लिए C-style functions जैसे `tolower()` use होते थे, और स्ट्रिंग्स C arrays की तरह होती थीं। C++ में `std::string` class और algorithms library के आगमन के बाद, स्ट्रिंग ऑपरेशंस को और भी सरल और अधिक शक्तिशाली बनाया गया। `std::transform` एक standard algorithm है जिसका use करके हम आसानी से string characters को इटरेट कर सकते हैं और किसी भी प्रकार का बदलाव कर सकते हैं। इसके अलावा, `boost` और `locale` जैसी libraries भी हैं जो कि विभिन्न भाषाओं और एन्कोडिंग्स के साथ बेहतर काम करती हैं। हालांकि, जब विशेष characters का प्रयोग होता है, तो लोकलाइज़ेशन और एन्कोडिंग अधिक महत्वपूर्ण हो जाते हैं।

## See Also (और जानकारी)
- `std::tolower`: http://www.cplusplus.com/reference/cctype/tolower/
- `std::transform`: http://www.cplusplus.com/reference/algorithm/transform/
- `std::string`: http://www.cplusplus.com/reference/string/string/
