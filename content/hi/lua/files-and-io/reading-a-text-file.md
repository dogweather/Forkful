---
title:                "टेक्स्ट फ़ाइल पढ़ना"
aliases:
- hi/lua/reading-a-text-file.md
date:                  2024-01-20T17:55:27.142041-07:00
model:                 gpt-4-1106-preview
simple_title:         "टेक्स्ट फ़ाइल पढ़ना"

tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/lua/reading-a-text-file.md"
---

{{< edit_this_page >}}

## What & Why? (क्या और क्यों?)
पाठ्य फ़ाइल पढ़ने का मतलब उसमें दिए गए डेटा को पढ़ना और उसे समझना है। प्रोग्रामर्स आम तौर पर यूजर डेटा, कॉन्फिगरेशन्स, या लॉग्स को प्रोसेस करने के लिए पाठ्य फ़ाइल पढ़ते हैं।

## How to: (कैसे करें:)
चलिए Lua में एक साधारण पाठ्य फाइल कैसे पढ़ी जाती है, ये देखें:

```Lua
-- फ़ाइल खोलना
local file = io.open("example.txt", "r")

-- फ़ाइल की सामग्री पढ़ना
if file then
    local content = file:read("*a")  -- पूरी फाइल पढ़ें
    print(content)                   -- सामग्री प्रिंट करें
    file:close()                     -- फ़ाइल बंद करें
else
    print("नहीं खुल सकती फ़ाइल।")
end
```

अगर `example.txt` में "Hello, Lua!" लिखा है, तो आउटपुट होगा:
```
Hello, Lua!
```

## Deep Dive (गहराई से जानिए)
पुराने ज़माने में, डेटा बड़े-बड़े कम्प्यूटर टेप्स पर सेव होता था। वक्त के साथ, सिम्पल टेक्स्ट फ़ाइलें कॉमन हो गईं, क्योंकि वे आसान थीं पढ़ने और लिखने के लिए। Lua में `io` लाइब्रेरी फ़ाइल I/O (input/output) ऑपरेशंस के लिए है। `io.open()` फ़ाइल खोलने के लिए है; इसके बाद `read()` से हम सामग्री पढ़ सकते हैं। "*a" पूरी फ़ाइल पढ़ने का पैरामीटर है।

वैकल्पिक रूप में, `io.lines()` से एक-एक करके लाइन पढ़ सकते हैं, या नेटवर्क स्ट्रीम से डेटा पढ़ने के लिए `socket` लाइब्रेरीज़ का उपयोग कर सकते हैं।

फ़ाइल पढ़ते समय याद रखें, फ़ाइल पढ़ने की प्रक्रिया धीमी हो सकती है, खासकर बड़ी फ़ाइल्स के लिए। कोड लिखते समय इसका ध्यान रखें।

## See Also (और देखिए)
1. Lua 5.4 Reference Manual: https://www.lua.org/manual/5.4/
2. Programming in Lua (first edition): http://www.lua.org/pil/1.html
3. Lua-Users Wiki: http://lua-users.org/wiki/IoLibraryTutorial

नोट: Lua के ऑनलाइन संसाधन अंग्रेजी में हो सकते हैं, लेकिन वे Lua को सीखने और माहिर बनने के लिए महत्वपूर्ण हैं।
