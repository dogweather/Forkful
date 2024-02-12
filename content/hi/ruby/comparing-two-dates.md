---
title:                "दो तारीखों की तुलना"
aliases:
- hi/ruby/comparing-two-dates.md
date:                  2024-01-20T17:34:04.119584-07:00
model:                 gpt-4-1106-preview
simple_title:         "दो तारीखों की तुलना"

tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/ruby/comparing-two-dates.md"
---

{{< edit_this_page >}}

## What & Why? (क्या और क्यों?)
  
तारीखों की तुलना का मतलब है कि जांचना कि कोई एक तारीख दूसरी तारीख से पहले, बाद या एक समान है या नहीं। प्रोग्रामर्स इसे डेटाबेस क्वेरी, समय-सीमा प्रबंधन, और ईवेंट स्केड्यूलिंग जैसे कामों के लिए करते हैं।

## How to: (कैसे करें:)

```ruby
require 'date'

# दो तारीखें बनाएं
date1 = Date.new(2023, 3, 14)
date2 = Date.new(2023, 4, 18)

# तारीखें तुलना करें
puts date1 < date2    # => true
puts date1 == date2   # => false
puts date1 > date2    # => false

# आज की तारीख के साथ तुलना
today = Date.today
puts today > date1    # यह आपके सिस्टम की तारीख पर निर्भर करेगा
```

## Deep Dive (गहराई से जानकारी):

तारीखों की तुलना करना प्रोग्रामिंग में एक सामान्य कार्य है, जिसका उपयोग सॉफ्टवेयर के प्रारंभिक दिनों से हो रहा है। `Date` वर्ग Ruby में शुरू से ही है और यह Time वर्ग की तुलना में सिर्फ तारीखों के साथ काम करने के लिए बनाया गया था। तारीखों की तुलना में एक सहज और तर्कसंगत ऑपरेशन शामिल है - `<`, `>`, और `==` ऑपरेटर्स का उपयोग करना।

Ruby में विभिन्न विधियाँ जैसे कि `Date.parse` और `Date.strptime` तारीखों को पढ़ने और परिवर्तित करने का एक अलग तरीका प्रदान करती हैं। `DateTime` वर्ग का उपयोग करके समय और तारीख दोनों के साथ तुलना भी की जा सकती है।

Ruby में, सबकुछ ऑब्जेक्ट है, इसलिए जब आप `Date.new` का उपयोग कर एक तारीख बनाते हैं, तो आप एक ऑब्जेक्ट बना रहे हैं जो `Date` क्लास के इंस्टेंस मेथड्स को एक्सेस कर सकता है।

तारीखों की तुलना करते समय, टाइमज़ोन्स और लीप इयर्स जैसे विवरण महत्वपूर्ण हो सकते हैं। Ruby की `Date` क्लास इन पहलुओं को संभालता है।

## See Also (और देखें):

- Ruby `Date` क्लास डॉक्यूमेंटेशन: [Date class](https://ruby-doc.org/stdlib-2.7.0/libdoc/date/rdoc/Date.html)
- Ruby `DateTime` वर्ग डॉक्यूमेंटेशन: [DateTime class](https://ruby-doc.org/stdlib-2.7.0/libdoc/date/rdoc/DateTime.html)
- समय क्षेत्रों के साथ काम करना: [Time zones](https://api.rubyonrails.org/classes/ActiveSupport/TimeZone.html)

ध्यान दें कि उपर्युक्त लिंक्स डॉक्यूमेंटेशन और गाइड के लिए हैं, जिनसे आपको Ruby में तारीखों की तुलना करने और समझने में और मदद मिलेगी।
