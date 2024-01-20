---
title:                "एक तारीख को स्ट्रिंग में परिवर्तित करना"
html_title:           "Java: एक तारीख को स्ट्रिंग में परिवर्तित करना"
simple_title:         "एक तारीख को स्ट्रिंग में परिवर्तित करना"
programming_language: "Lua"
category:             "Lua"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/lua/converting-a-date-into-a-string.md"
---

{{< edit_this_page >}}

## क्या और क्यों ? (What & Why?)

तारीख को स्ट्रिंग में परिवर्तित करने से अभिप्रेत होता है की हम एक तारीख को स्वरूप दे सकते हैं जिसे हम मशीन से बेहतर तरीके से समझ सकते हैं। प्रोग्रामर्स इसे इसलिए करते हैं ताकि वे विशिष्ट डेटा स्वरूपों में तारीख को संदर्भित कर सकें।

## कैसे करें : (How to:)

अब हम देखेंगे की Lua में किस प्रकार तारीख को स्ट्रिंग में परिवर्तित किया जाता है। साधारणतया, हम os.date फ़ंक्शन का उपयोग करते हैं।

```Lua
date = os.date("*t")  -- वर्तमान तिथि और समय लेने के लिए
date_string = os.date("%A, %B %d, %Y", os.time(date)) -- तिथि को आवश्यक स्वरूप में बदलने के लिए
print(date_string) -- तारीख की स्ट्रिंग प्रिंट करने के लिए
```

यहां "%A, %B %d, %Y" एक फॉर्मैट स्ट्रिंग है जिसे os.date फंक्शन ने उपयोग किया।

## गहराई में (Deep Dive)

Lua में तारीख को स्ट्रिंग में परिवर्तित करने की प्रक्रिया उसकी कोर लाइब्रेरी का हिस्सा है, जो कि उसके Standard C Library का हिस्सा है। os.date इसे C में परिभाषित strftime फंक्शन का उपयोग करके करता है।

os.date के विकल्प में, आप "date" इंतजार में नहीं होंगे, इसे nil होते हुए भी छोड़ सकते हैं। इससे वैध स्थानीय समय और दिनांक के आवश्यक स्वरूप पेश किए जाएंगे।

## यदि देखना हो (See Also)

1. [Lua तारीख और समय](https://www.tutorialspoint.com/lua/lua_date_and_time.htm)
2. [Lua os.date](https://www.lua.org/pil/22.1.html)
3. [Lua: कैसे करें सीरीज](https://luatut.com/crash-course.html)