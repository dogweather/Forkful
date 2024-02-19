---
aliases:
- /hi/ruby/downloading-a-web-page/
date: 2024-01-20 17:45:28.936517-07:00
description: "\u0935\u0947\u092C \u092A\u0947\u091C \u0915\u094B \u0921\u093E\u0909\
  \u0928\u0932\u094B\u0921 \u0915\u0930\u0928\u093E \u092E\u0924\u0932\u092C \u0909\
  \u0938\u0915\u093E HTML \u0915\u094B\u0921 \u0905\u092A\u0928\u0947 \u0915\u0902\
  \u092A\u094D\u092F\u0942\u091F\u0930 \u092A\u0930 \u0938\u0947\u0935 \u0915\u0930\
  \u0928\u093E \u0939\u0948\u0964 \u0915\u094B\u0921\u0930\u094D\u0938 \u092F\u0939\
  \ \u0907\u0938\u0932\u093F\u090F \u0915\u0930\u0924\u0947 \u0939\u0948\u0902 \u0924\
  \u093E\u0915\u093F \u0935\u0947\u092C \u0921\u093E\u091F\u093E \u0915\u0947 \u0938\
  \u093E\u0925 \u0911\u092B\u0932\u093E\u0907\u0928 \u0915\u093E\u092E \u0915\u0930\
  \ \u0938\u0915\u0947\u0902, \u091C\u0948\u0938\u0947 \u0915\u0940 \u0921\u093E\u091F\
  \u093E\u2026"
lastmod: 2024-02-18 23:09:04.294343
model: gpt-4-1106-preview
summary: "\u0935\u0947\u092C \u092A\u0947\u091C \u0915\u094B \u0921\u093E\u0909\u0928\
  \u0932\u094B\u0921 \u0915\u0930\u0928\u093E \u092E\u0924\u0932\u092C \u0909\u0938\
  \u0915\u093E HTML \u0915\u094B\u0921 \u0905\u092A\u0928\u0947 \u0915\u0902\u092A\
  \u094D\u092F\u0942\u091F\u0930 \u092A\u0930 \u0938\u0947\u0935 \u0915\u0930\u0928\
  \u093E \u0939\u0948\u0964 \u0915\u094B\u0921\u0930\u094D\u0938 \u092F\u0939 \u0907\
  \u0938\u0932\u093F\u090F \u0915\u0930\u0924\u0947 \u0939\u0948\u0902 \u0924\u093E\
  \u0915\u093F \u0935\u0947\u092C \u0921\u093E\u091F\u093E \u0915\u0947 \u0938\u093E\
  \u0925 \u0911\u092B\u0932\u093E\u0907\u0928 \u0915\u093E\u092E \u0915\u0930 \u0938\
  \u0915\u0947\u0902, \u091C\u0948\u0938\u0947 \u0915\u0940 \u0921\u093E\u091F\u093E\
  \u2026"
title: "\u0935\u0947\u092C \u092A\u0947\u091C \u0921\u093E\u0909\u0928\u0932\u094B\
  \u0921 \u0915\u0930\u0928\u093E"
---

{{< edit_this_page >}}

## What & Why? (क्या और क्यों?)
वेब पेज को डाउनलोड करना मतलब उसका HTML कोड अपने कंप्यूटर पर सेव करना है। कोडर्स यह इसलिए करते हैं ताकि वेब डाटा के साथ ऑफलाइन काम कर सकें, जैसे की डाटा पार्सिंग और वेब स्क्रेपिंग।

## How to: (कैसे करें:)
Ruby में वेब पेज डाउनलोड करने के लिए `net/http` लाइब्रेरी का इस्तेमाल होता है। नीचे कोड में देखिए:

```ruby
require 'net/http'
require 'uri'

url = URI.parse('http://www.example.com/index.html')
response = Net::HTTP.get_response(url)

if response.is_a?(Net::HTTPSuccess)
  File.write('downloaded_page.html', response.body)
  puts "Web page downloaded successfully!"
else
  puts "Error downloading web page."
end
```

अगर सफल रहा, तो आउटपुट होगा:

```
Web page downloaded successfully!
```

## Deep Dive (गहराई से जानकारी):
Ruby में किसी वेब पेज को डाउनलोड करने का काम `net/http` लाइब्रेरी से शुरु हुआ, जो कि HTTP प्रोटोकॉल्स को संभालती है। ये प्रोटोकॉल HTML और दूसरे वेब रिसोर्सेज को ट्रांसफर करने के लिए इंटरनेट पर मानक तरीका है। बदलते समय के साथ, कई अन्य लाइब्रेरीज जैसे कि `open-uri` और `mechanize` भी आई हैं, जो कुछ ज्यादा फंक्शनलिटी प्रोवाइड करती हैं।

इन लाइब्रेरीज के इस्तेमाल से आप कोड में बस कुछ ही पंक्तियों का इस्तेमाल करके वेब पेज के डाटा को प्रोसेस कर सकते हैं, जिससे कि टाइम और एफर्ट की बचत होती है।

## See Also (देखें ये भी):
- [Ruby डॉक्यूमेंटेशन Net::HTTP](https://ruby-doc.org/stdlib-3.0.0/libdoc/net/http/rdoc/Net/HTTP.html)
- [Open-URI](https://ruby-doc.org/stdlib-3.0.0/libdoc/open-uri/rdoc/OpenURI.html)
- [Nokogiri जेम (HTML/XML डाटा को पार्स करने के लिए)](https://nokogiri.org/)
- [Mechanize जेम (एक ऑटोमेशन लाइब्रेरी जो वेब इंटरैक्शन को सिम्पलीफाई करती है)](https://github.com/sparklemotion/mechanize)
