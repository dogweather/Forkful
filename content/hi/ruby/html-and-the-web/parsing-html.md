---
aliases:
- /hi/ruby/parsing-html/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:13:38.283551-07:00
description: "HTML \u0915\u093E \u092A\u093E\u0930\u094D\u0938\u093F\u0902\u0917 \u092E\
  \u0924\u0932\u092C HTML \u0915\u094B\u0921 \u0915\u0947 \u090F\u0915 \u091F\u0941\
  \u0915\u0921\u093C\u0947 \u0915\u094B \u0905\u0932\u0917 \u0915\u0930\u0915\u0947\
  \ \u0909\u0938\u0915\u0940 \u0938\u0902\u0930\u091A\u0928\u093E \u0914\u0930 \u0938\
  \u093E\u092E\u0917\u094D\u0930\u0940 \u0915\u094B \u0938\u092E\u091D\u0928\u093E\
  \u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930 \u0907\u0938\
  \u0947 \u0921\u0947\u091F\u093E \u0928\u093F\u0915\u093E\u0932\u0928\u0947, \u0938\
  \u093E\u092E\u0917\u094D\u0930\u0940 \u0915\u094B \u0938\u0902\u0936\u094B\u0927\
  \u093F\u0924 \u0915\u0930\u0928\u0947, \u092F\u093E \u091C\u093E\u0928\u0915\u093E\
  \u0930\u0940\u2026"
lastmod: 2024-02-18 23:09:04.292563
model: gpt-4-0125-preview
summary: "HTML \u0915\u093E \u092A\u093E\u0930\u094D\u0938\u093F\u0902\u0917 \u092E\
  \u0924\u0932\u092C HTML \u0915\u094B\u0921 \u0915\u0947 \u090F\u0915 \u091F\u0941\
  \u0915\u0921\u093C\u0947 \u0915\u094B \u0905\u0932\u0917 \u0915\u0930\u0915\u0947\
  \ \u0909\u0938\u0915\u0940 \u0938\u0902\u0930\u091A\u0928\u093E \u0914\u0930 \u0938\
  \u093E\u092E\u0917\u094D\u0930\u0940 \u0915\u094B \u0938\u092E\u091D\u0928\u093E\
  \u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930 \u0907\u0938\
  \u0947 \u0921\u0947\u091F\u093E \u0928\u093F\u0915\u093E\u0932\u0928\u0947, \u0938\
  \u093E\u092E\u0917\u094D\u0930\u0940 \u0915\u094B \u0938\u0902\u0936\u094B\u0927\
  \u093F\u0924 \u0915\u0930\u0928\u0947, \u092F\u093E \u091C\u093E\u0928\u0915\u093E\
  \u0930\u0940\u2026"
title: "HTML \u0935\u093F\u0936\u094D\u0932\u0947\u0937\u0923"
---

{{< edit_this_page >}}

## क्या और क्यों?
HTML का पार्सिंग मतलब HTML कोड के एक टुकड़े को अलग करके उसकी संरचना और सामग्री को समझना। प्रोग्रामर इसे डेटा निकालने, सामग्री को संशोधित करने, या जानकारी को विभिन्न प्रारूपों और प्रणालियों के बीच स्थानांतरित करने के लिए करते हैं।

## कैसे करें:
रूबी में HTML पार्स करने के लिए, 'Nokogiri' जेम को `gem install nokogiri` के साथ स्थापित करें। Nokogiri रूबी में HTML और XML के साथ काम करने के लिए एक स्विस आर्मी चाकू की तरह है। यहाँ एक त्वरित उदाहरण है:

```ruby
require 'nokogiri'
require 'open-uri'

# एक वेबसाइट से HTML सामग्री लोड करें
html_content = URI.open('http://example.com').read

# HTML का पार्सिंग करें
doc = Nokogiri::HTML(html_content)

# शीर्षक निकालें
title = doc.xpath('//title').text
puts "पृष्ठ का शीर्षक है: #{title}"
```

इससे कुछ ऐसा निकलता है: `पृष्ठ का शीर्षक है: Example Domain`.

## गहराई में जानकारी
पुराने रूबी दिनों में, HTML का पार्सिंग के लिए विकल्प सीमित थे। REXML बिल्ट-इन था लेकिन धीमा था। फिर Hpricot आया, लेकिन वह गायब हो गया। Nokogiri 2008 में प्रस्तुत हुआ, Hpricot की आसानी के साथ libxml की गति और शक्ति को मिलाकर, जो कि एक सिद्ध XML टूलकिट है।

पार्सिंग दुनिया में, हमेशा विकल्प होते हैं। कुछ 'rexml' लाइब्रेरी या 'oga', रूबी के लिए एक और XML/HTML पार्सर पर कसम खाते हैं। लेकिन Nokogiri अपनी मजबूती और गति के लिए, ना केवल अपनी विशाल सुविधाओं की सरणी के कारण, एक पसंदीदा बना हुआ है।

भीतर से, Nokogiri HTML को एक दस्तावेज़ वस्तु मॉडल (DOM)—एक वृक्ष संरचना में परिवर्तित करता है। यह तत्वों को नेविगेट और संशोधित करना आसान बनाता है। XPath और CSS सेलेक्टर्स का उपयोग करके, आप जरूरत की किसी भी जानकारी को पिनपॉइंट कर सकते हैं।

## देखें भी
- Nokogiri जेम: [https://nokogiri.org/](https://nokogiri.org/)
- रूबी का rexml दस्तावेज़ीकरण: [https://ruby-doc.org/stdlib-2.6.3/libdoc/rexml/rdoc/REXML/Document.html](https://ruby-doc.org/stdlib-2.6.3/libdoc/rexml/rdoc/REXML/Document.html)
- विकल्प पार्सर 'oga': [https://github.com/YorickPeterse/oga](https://github.com/YorickPeterse/oga)
- XPath के बारे में जानें: [https://www.w3schools.com/xml/xpath_intro.asp](https://www.w3schools.com/xml/xpath_intro.asp)
