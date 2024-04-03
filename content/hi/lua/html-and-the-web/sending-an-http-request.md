---
date: 2024-01-20 18:00:49.229065-07:00
description: "HTTP \u0905\u0928\u0941\u0930\u094B\u0927 \u092D\u0947\u091C\u0928\u093E\
  \ \u092F\u093E\u0928\u0940 \u0935\u0947\u092C \u0938\u0930\u094D\u0935\u0930 \u0938\
  \u0947 \u0921\u0947\u091F\u093E \u092E\u093E\u0902\u0917\u0928\u093E\u0964 \u092A\
  \u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930 \u0907\u0938\u0947 \u0935\
  \u0947\u092C \u090F\u092A\u0940\u0906\u0908 \u0915\u0947 \u0938\u093E\u0925 \u092C\
  \u093E\u0924\u091A\u0940\u0924, \u0935\u0947\u092C\u0938\u093E\u0907\u091F\u094D\
  \u0938 \u0938\u0947 \u0921\u0947\u091F\u093E \u0939\u093E\u0938\u093F\u0932 \u0915\
  \u0930\u0928\u0947, \u0914\u0930 \u0935\u0947\u092C \u0938\u0947\u0935\u093E\u0913\
  \u0902 \u0915\u094B \u0915\u092E\u093E\u0902\u0921 \u092D\u0947\u091C\u0928\u0947\
  \ \u0915\u0947 \u0932\u093F\u090F\u2026"
lastmod: '2024-03-13T22:44:52.544121-06:00'
model: gpt-4-1106-preview
summary: "HTTP \u0905\u0928\u0941\u0930\u094B\u0927 \u092D\u0947\u091C\u0928\u093E\
  \ \u092F\u093E\u0928\u0940 \u0935\u0947\u092C \u0938\u0930\u094D\u0935\u0930 \u0938\
  \u0947 \u0921\u0947\u091F\u093E \u092E\u093E\u0902\u0917\u0928\u093E\u0964 \u092A\
  \u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930 \u0907\u0938\u0947 \u0935\
  \u0947\u092C \u090F\u092A\u0940\u0906\u0908 \u0915\u0947 \u0938\u093E\u0925 \u092C\
  \u093E\u0924\u091A\u0940\u0924, \u0935\u0947\u092C\u0938\u093E\u0907\u091F\u094D\
  \u0938 \u0938\u0947 \u0921\u0947\u091F\u093E \u0939\u093E\u0938\u093F\u0932 \u0915\
  \u0930\u0928\u0947, \u0914\u0930 \u0935\u0947\u092C \u0938\u0947\u0935\u093E\u0913\
  \u0902 \u0915\u094B \u0915\u092E\u093E\u0902\u0921 \u092D\u0947\u091C\u0928\u0947\
  \ \u0915\u0947 \u0932\u093F\u090F \u0915\u0930\u0924\u0947 \u0939\u0948\u0902\u0964\
  ."
title: "HTTP \u0905\u0928\u0941\u0930\u094B\u0927 \u092D\u0947\u091C\u0928\u093E"
weight: 44
---

## How to: (कैसे करें)
Lua में HTTP अनुरोध भेजने के लिए, 'lua-http' या 'socket.http' जैसे मॉड्यूल का उपयोग होता है। नीचे 'lua-http' का उपयोग करके साधारण GET अनुरोध का उदाहरण है:

```Lua
local http = require('http')

local function fetchUrl(url)
    local response, err = http.request("GET", url)
    if not response then
        print("HTTP अनुरोध में त्रुटि:", err)
        return
    end
    print(response:get_body_as_string())
end

fetchUrl("http://httpbin.org/get")
```

यह कोड एक वेब पेज से कंटेंट को प्रिंट करेगा। अगर त्रुटि आती है, तो वह भी प्रिंट होगी।

## Deep Dive (गहराई से जानकारी)
HTTP (HyperText Transfer Protocol) इंटरनेट पर डेटा संचार का मुख्य माध्यम है। इसकी शुरुआत 1989 में हुई थी। Lua में, हमे सरल HTTP अनुरोध के लिए 'lua-http' या 'LuaSocket' जैसे तीसरे पक्ष के लाइब्रेरीज का सहारा लेना पड़ता है। 'lua-http' अधिक मॉडर्न और फुल-फीचर्ड है, जबकि 'LuaSocket' पुराना पर मजबूत है। 

इन दोनों का विकल्प REST API के संपर्क में आने के लिए, संदेश स्वरूप (JSON या XML) में कन्वर्ट करना, और हेडर्स, पैरामीटर्स, और अथेंटिकेशन जैसे बारीकियाँ संभालना अहम हैं।

## See Also (इसे भी देखें)
- Lua HTTP documentation: [https://github.com/daurnimator/lua-http](https://github.com/daurnimator/lua-http)
- HTTP बिन (टेस्ट HTTP अनुरोध): [http://httpbin.org/](http://httpbin.org/)
