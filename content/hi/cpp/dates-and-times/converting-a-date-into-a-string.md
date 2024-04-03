---
date: 2024-01-20 17:36:43.142494-07:00
description: "\u0921\u0947\u091F \u0915\u094B \u0938\u094D\u091F\u094D\u0930\u093F\
  \u0902\u0917 \u092E\u0947\u0902 \u0915\u0928\u094D\u0935\u0930\u094D\u091F \u0915\
  \u0930\u0928\u093E \u092E\u0924\u0932\u092C \u0939\u0948 \u0915\u0948\u0932\u0947\
  \u0902\u0921\u0930 \u0921\u0947\u091F \u0915\u094B \u091F\u0947\u0915\u094D\u0938\
  \u094D\u091F \u092B\u0949\u0930\u094D\u092E\u0947\u091F \u092E\u0947\u0902 \u092C\
  \u0926\u0932\u0928\u093E\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\
  \u0930\u094D\u0938 \u092F\u0939 \u0907\u0938\u0932\u093F\u090F \u0915\u0930\u0924\
  \u0947 \u0939\u0948\u0902 \u0924\u093E\u0915\u093F \u0921\u0947\u091F\u094D\u0938\
  \ \u0915\u094B \u0906\u0938\u093E\u0928\u0940 \u0938\u0947 \u092A\u0922\u093C\u093E\
  \ \u0914\u0930 \u0938\u094D\u091F\u094B\u0930\u2026"
lastmod: '2024-03-13T22:44:52.864793-06:00'
model: gpt-4-1106-preview
summary: "\u0921\u0947\u091F \u0915\u094B \u0938\u094D\u091F\u094D\u0930\u093F\u0902\
  \u0917 \u092E\u0947\u0902 \u0915\u0928\u094D\u0935\u0930\u094D\u091F \u0915\u0930\
  \u0928\u093E \u092E\u0924\u0932\u092C \u0939\u0948 \u0915\u0948\u0932\u0947\u0902\
  \u0921\u0930 \u0921\u0947\u091F \u0915\u094B \u091F\u0947\u0915\u094D\u0938\u094D\
  \u091F \u092B\u0949\u0930\u094D\u092E\u0947\u091F \u092E\u0947\u0902 \u092C\u0926\
  \u0932\u0928\u093E\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930\
  \u094D\u0938 \u092F\u0939 \u0907\u0938\u0932\u093F\u090F \u0915\u0930\u0924\u0947\
  \ \u0939\u0948\u0902 \u0924\u093E\u0915\u093F \u0921\u0947\u091F\u094D\u0938 \u0915\
  \u094B \u0906\u0938\u093E\u0928\u0940 \u0938\u0947 \u092A\u0922\u093C\u093E \u0914\
  \u0930 \u0938\u094D\u091F\u094B\u0930 \u0915\u093F\u092F\u093E \u091C\u093E \u0938\
  \u0915\u0947\u0964."
title: "\u0924\u093E\u0930\u0940\u0916 \u0915\u094B \u0938\u094D\u091F\u094D\u0930\
  \u093F\u0902\u0917 \u092E\u0947\u0902 \u092C\u0926\u0932\u0928\u093E"
weight: 28
---

## How to: (कैसे करें:)
```c++
#include <iostream>
#include <iomanip>
#include <sstream>
#include <ctime>

std::string convertDateToString(const tm &date) {
    std::ostringstream stream;
    stream << std::put_time(&date, "%d-%m-%Y");
    return stream.str();
}

int main() {
    std::time_t t = std::time(nullptr);
    std::tm *datePtr = std::localtime(&t);
    
    std::string dateString = convertDateToString(*datePtr);
    std::cout << "आज की तारीख (स्ट्रिंग में): " << dateString << std::endl;
    
    return 0;
}
```

सैंपल आउटपुट:
```
आज की तारीख (स्ट्रिंग में): 31-12-2023
```

## Deep Dive (गहराई से जानकारी):
पहले कंप्यूटर सिस्टम्स में डेट और टाइम हैंडलिंग बहुत बेसिक थी। C++ में `<ctime>` हेडर फ़ाइल से डेट और टाइम का प्रबंधन किया जाता है, वहीं `<iomanip>` डेटा को फॉर्मेट करने के काम आती है। `std::put_time` एक मॉडर्न C++ फ़ंक्शन है जो `std::ostringstream` के साथ मिलकर डेट को चुनिंदा फॉर्मेट में स्ट्रिंग बनाने में सक्षम बनाता है। विकल्प के रूप में, बूस्ट लाइब्रेरी और C++20 से `std::format` जैसे अधिक आधुनिक समाधान भी मौजूद हैं, पर ये सभी कंपाइलर पर उपलब्ध नहीं हो सकते।

`std::put_time` और `strftime` फ़ंक्शन दशकों पुराने C फ़ंक्शन्स के मॉडर्न विकल्प हैं। सही फॉर्मेट स्पेसिफ़ायर ("`%d`", "`%m`", "`%Y`", इत्यादि) चुनना महत्वपूर्ण है, क्योंकि वे तारीख, महीने, साल को विभिन्न तरीकों में प्रस्तुत करने का काम करते हैं।

## See Also (और भी जानकारी):
- C++ `<ctime>` लाइब्रेरी डॉक्युमेंटेशन: https://en.cppreference.com/w/cpp/header/ctime
- C++ `<iomanip>` लाइब्रेरी डॉक्युमेंटेशन: https://en.cppreference.com/w/cpp/header/iomanip
- `std::put_time` के बारे में जानकारी: https://en.cppreference.com/w/cpp/io/manip/put_time
- C++20 `std::format`: https://en.cppreference.com/w/cpp/utility/format
