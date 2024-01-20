---
title:                "सबस्ट्रिंग्स निकालना"
html_title:           "Clojure: सबस्ट्रिंग्स निकालना"
simple_title:         "सबस्ट्रिंग्स निकालना"
programming_language: "Lua"
category:             "Lua"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/lua/extracting-substrings.md"
---

{{< edit_this_page >}}

## क्या और क्यों?

सबस्ट्रिंग निकालना (substring extraction) एक स्ट्रिंग के भीतर से एक छोटी स्ट्रिंग का चयन होता है। प्रोग्रामर्स इसे करते हैं ताकि वे विशिष्ट डेटा, जैसे की यूजर नाम या ईमेल डोमेन, को स्पष्ट रूप में प्रस्तुत कर सकें।

## कैसे करें (How to:)

```Lua
s = "Hello, World!"
print(s:sub(1, 5))   -- "Hello"
print(s:sub(8, 12))  -- "World"
```

यहां, हमने `sub` मेथड का उपयोग किया है स्ट्रिंग `s` में से दो सबस्ट्रिंग्स निकालने के लिए।

## गहरी डुबकी (Deep Dive)

Lua में सबस्ट्रिंग निकालना बहुत सरल है, लेकिन उनके पिछे की टेक्नोलॉजी और व्यावसायिक है। Lua पहली बार 1993 में विकसित हुई थी और यह आपको विशेष आवश्यकताओं के विशेष कोड ब्लॉक को निकालने में मदद करने का एक शक्तिशाली तरीका प्रदान करती है।

वैकल्पिक रूप से, चरित्रों की संख्या का ज्ञान होने पर आप `string.char` फ़ंक्शन का उपयोग कर सकते हैं।

```Lua
print(string.char(72, 101, 108, 108, 111))  -- "Hello"
```

अपने कोड में सबस्ट्रिंग निकालने के तरीके से संबंधित जरूरी विवरण यथास्थान जाहिर होते हैं। Lua इसे स्थानीय बली निर्धारण (locality of reference) के माध्यम से सहयोग देता है, जो यह सुनिश्चित करता है कि उपयोग में आने वाला मेमोरी क्षेत्र कम से कम प्रचारित हो।

## अधिक देखें (See Also)

विस्तार से जानने के लिए, आप निम्नलिखित लिंक्स देख सकते हैं:

- [Lua 5.4 Reference Manual: string.sub](https://www.lua.org/manual/5.4/manual.html#6.4.1)
- [Wikibooks: Lua Programming - Strings](https://en.wikibooks.org/wiki/Lua_Programming/strings)
- [Learn Lua: Substrings](http://www.learn-lua.org/basics/strings.html)