---
title:                "वर्तमान तारीख प्राप्त करना"
date:                  2024-01-20T15:14:07.417349-07:00
simple_title:         "वर्तमान तारीख प्राप्त करना"

tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/elixir/getting-the-current-date.md"
---

{{< edit_this_page >}}

## What & Why? (क्या और क्यों?)
वर्तमान तिथि प्राप्त करना मतलब है आज का दिन, महीना, और साल जानना। प्रोग्रामर्स इसे लॉग्स, फीचर्स या उपयोगकर्ता इंटरफेस में तारीख दिखाने के लिए करते हैं।

## How to: (कैसे करें:)
Elixir में वर्तमान तिथि प्राप्त करना आसान है। नीचे Elixir कोड और आउटपुट दिया हुआ है:

```elixir
# Elixir का इस्तेमाल करके वर्तमान तिथि प्राप्त करने का उदाहरण:

# NaiveDateTime मॉड्यूल का उपयोग
current_date = Date.utc_today()
IO.puts("आज की तिथि है: #{current_date}")

# इसे चलाने पर निम्न आउटपुट मिलेगा:
# आज की तिथि है: YYYY-MM-DD
```

इस कोड को आपके Elixir प्रोजेक्ट में रन करवा कर आप वर्तमान तिथि प्राप्त कर सकते हैं।

## Deep Dive (गहराई में जानकारी):

Elixir की डेट और टाइम हैंडलिंग क्षमताओं को `Date`, `Time`, `DateTime`, और `NaiveDateTime` मॉड्यूल्स के माध्यम से प्रदान किया जाता है। पहले की बजाय, एर्लैंग और Elixir में वर्ष 2012 के बाद समय संबंधी कार्यक्षमता में काफी सुधार हुआ है। आजकल, `Date.utc_today/0` जैसे फंक्शन्स आपको सीधे UTC में वर्तमान तिथि देते हैं। 

इसके अलावा, आप `Timex` जैसे थर्ड-पार्टी लाइब्रेरी का भी उपयोग कर सकते हैं, जो जटिल तारीख और समय ऑपरेशन्स को हैंडल करने के लिए बेहतर सपोर्ट प्रदान करती है।

## See Also (और जानकारी के लिए):

- Elixir डॉक्स फॉर `Date`: https://hexdocs.pm/elixir/Date.html
- Elixir डॉक्स फॉर `NaiveDateTime`: https://hexdocs.pm/elixir/NaiveDateTime.html
- Timex लाइब्रेरी: https://hex.pm/packages/timex

इन लिंक्स को फॉलो करके आप विस्तृत जानकारी और कोड उदाहरण प्राप्त कर सकते हैं।
