---
aliases:
- /hi/elixir/comparing-two-dates/
date: 2024-01-20 17:33:18.058794-07:00
description: "\u0924\u093E\u0930\u0940\u0916\u094B\u0902 \u0915\u0940 \u0924\u0941\
  \u0932\u0928\u093E \u0915\u0930\u0928\u093E \u092E\u0924\u0932\u092C \u0939\u0948\
  \ \u092A\u0924\u093E \u0915\u0930\u0928\u093E \u0915\u093F \u090F\u0915 \u0924\u093E\
  \u0930\u0940\u0916 \u0926\u0942\u0938\u0930\u0947 \u0938\u0947 \u092A\u0939\u0932\
  \u0947 \u0939\u0948, \u092C\u093E\u0926 \u092E\u0947\u0902 \u0939\u0948 \u092F\u093E\
  \ \u092C\u0930\u093E\u092C\u0930 \u0939\u0948\u0964 \u092A\u094D\u0930\u094B\u0917\
  \u094D\u0930\u093E\u092E\u0930\u094D\u0938 \u0907\u0938\u0915\u093E \u0909\u092A\
  \u092F\u094B\u0917 \u0938\u092E\u092F \u0938\u092E\u094D\u092C\u0902\u0927\u093F\
  \u0924 \u092B\u0940\u091A\u0930\u094D\u0938, \u091C\u0948\u0938\u0947 \u0915\u0940\
  \ deadline\u2026"
lastmod: 2024-02-18 23:09:02.826131
model: gpt-4-1106-preview
summary: "\u0924\u093E\u0930\u0940\u0916\u094B\u0902 \u0915\u0940 \u0924\u0941\u0932\
  \u0928\u093E \u0915\u0930\u0928\u093E \u092E\u0924\u0932\u092C \u0939\u0948 \u092A\
  \u0924\u093E \u0915\u0930\u0928\u093E \u0915\u093F \u090F\u0915 \u0924\u093E\u0930\
  \u0940\u0916 \u0926\u0942\u0938\u0930\u0947 \u0938\u0947 \u092A\u0939\u0932\u0947\
  \ \u0939\u0948, \u092C\u093E\u0926 \u092E\u0947\u0902 \u0939\u0948 \u092F\u093E\
  \ \u092C\u0930\u093E\u092C\u0930 \u0939\u0948\u0964 \u092A\u094D\u0930\u094B\u0917\
  \u094D\u0930\u093E\u092E\u0930\u094D\u0938 \u0907\u0938\u0915\u093E \u0909\u092A\
  \u092F\u094B\u0917 \u0938\u092E\u092F \u0938\u092E\u094D\u092C\u0902\u0927\u093F\
  \u0924 \u092B\u0940\u091A\u0930\u094D\u0938, \u091C\u0948\u0938\u0947 \u0915\u0940\
  \ deadline\u2026"
title: "\u0926\u094B \u0924\u093E\u0930\u0940\u0916\u094B\u0902 \u0915\u0940 \u0924\
  \u0941\u0932\u0928\u093E"
---

{{< edit_this_page >}}

## What & Why? (क्या और क्यों?)
तारीखों की तुलना करना मतलब है पता करना कि एक तारीख दूसरे से पहले है, बाद में है या बराबर है। प्रोग्रामर्स इसका उपयोग समय सम्बंधित फीचर्स, जैसे की deadline checks और time-based sorting के लिए करते हैं।

## How to: (कैसे करें:)
Elixir में दो तारीखें तुलना करने के लिए `Date` मॉड्यूल का उपयोग होता है।

```elixir
# तारीख बनाना
date1 = ~D[2023-03-01]
date2 = ~D[2023-04-01]

# तारीखों की तुलना
before = Date.compare(date1, date2) # :lt (less than)
same = Date.compare(date1, date1)   # :eq (equal)
after = Date.compare(date2, date1)  # :gt (greater than)

IO.puts "date1 is before date2: #{before}"
IO.puts "date1 is same as date1: #{same}"
IO.puts "date2 is after date1: #{after}"
```

सैंपल आउटपुट:

```
date1 is before date2: lt
date1 is same as date1: eq
date2 is after date1: gt
```

## Deep Dive (गहन अंतर्दृष्टि)
Elixir में `Date.compare/2` फंक्शन दिनांक तुलना के लिए एक मानक तरीका है, जो कि 2016 में Elixir 1.3 के रिलीज के साथ आया। Elixir, Erlang वर्चुअल मशीन पर चलता है और प्राकृतिक रूप से concurrent programming से मेल खाता है। तारीखों की तुलना UTF-8 कैलेंडर स्टैंडर्ड्स के अनुसार होती है।

वैकल्पिक लाइब्रेरीज जैसे कि Timex भी मौजूद हैं, जो अतिरिक्त फंक्शनलिटीज प्रदान करती हैं, पर बुनियादी तारीख तुलना के लिए Elixir का मानक लाइब्रेरी पर्याप्त है। इसका कार्यान्वयन Elixir के कोड में highly optimized है, जिससे प्रदर्शन में लाभ होता है।

## See Also (और जानकारी के लिए)
- Elixir का ऑफिशियल डॉक्यूमेंटेशन: [Date](https://hexdocs.pm/elixir/Date.html)
- Timex लाइब्रेरी: [Timex on Hex.pm](https://hex.pm/packages/timex)
- Elixir फोरम, डिस्कशन के लिए: [Elixir Forum](https://elixirforum.com/)
- Learn Elixir, एक फ्री पाठ्य सामग्री : [Learn Elixir](https://elixirschool.com/en/)
