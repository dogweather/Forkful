---
date: 2024-01-20 17:35:50.086154-07:00
description: "String concatenation \u0915\u093E \u092E\u0924\u0932\u092C \u0939\u0948\
  \ \u0926\u094B \u092F\u093E \u0926\u094B \u0938\u0947 \u091C\u094D\u092F\u093E\u0926\
  \u093E strings \u0915\u094B \u091C\u094B\u0921\u093C\u0928\u093E \u0924\u093E\u0915\
  \u093F \u0935\u0947 \u090F\u0915 \u0938\u093E\u0925 \u090F\u0915 \u0928\u092F\u093E\
  \ \u0938\u0902\u0926\u0947\u0936 \u092C\u0928\u093E \u0938\u0915\u0947\u0902\u0964\
  \ Programmers \u0907\u0938\u0947 \u0907\u0938\u0932\u093F\u090F \u0915\u0930\u0924\
  \u0947 \u0939\u0948\u0902 \u0924\u093E\u0915\u093F \u0935\u0947 \u0921\u093E\u091F\
  \u093E \u0915\u094B\u2026"
lastmod: '2024-03-13T22:44:52.685172-06:00'
model: gpt-4-1106-preview
summary: "String concatenation \u0915\u093E \u092E\u0924\u0932\u092C \u0939\u0948\
  \ \u0926\u094B \u092F\u093E \u0926\u094B \u0938\u0947 \u091C\u094D\u092F\u093E\u0926\
  \u093E strings \u0915\u094B \u091C\u094B\u0921\u093C\u0928\u093E \u0924\u093E\u0915\
  \u093F \u0935\u0947 \u090F\u0915 \u0938\u093E\u0925 \u090F\u0915 \u0928\u092F\u093E\
  \ \u0938\u0902\u0926\u0947\u0936 \u092C\u0928\u093E \u0938\u0915\u0947\u0902\u0964\
  \ Programmers \u0907\u0938\u0947 \u0907\u0938\u0932\u093F\u090F \u0915\u0930\u0924\
  \u0947 \u0939\u0948\u0902 \u0924\u093E\u0915\u093F \u0935\u0947 \u0921\u093E\u091F\
  \u093E \u0915\u094B \u092B\u0949\u0930\u094D\u092E\u0947\u091F \u0915\u0930 \u0938\
  \u0915\u0947\u0902 \u0914\u0930 \u092F\u0942\u091C\u0930\u094D\u0938 \u0915\u0947\
  \ \u0932\u093F\u090F \u092E\u0947\u0928\u093F\u0902\u0917\u092B\u0941\u0932 \u0907\
  \u0928\u094D\u092B\u094B\u0930\u094D\u092E\u0947\u0936\u0928 \u0921\u093F\u0938\u094D\
  \u092A\u094D\u0932\u0947 \u0915\u0930 \u0938\u0915\u0947\u0902\u0964."
title: "\u0938\u094D\u091F\u094D\u0930\u093F\u0902\u0917 \u0915\u094B \u091C\u094B\
  \u0921\u093C\u0928\u093E"
weight: 3
---

## How to: (कैसे करें?)
PowerShell में strings concatenate करने के लिए कई तरीके हैं:

```PowerShell
# 'Plus' operator का इस्तेमाल करते हुए
$string1 = "Hello, "
$string2 = "World!"
$concatenatedString = $string1 + $string2
$concatenatedString  # Output: Hello, World!

# -f operator format का इस्तेमाल करते हुए
$name = "दोस्त"
$greeting = "नमस्ते, {0}!"
$personalGreeting = $greeting -f $name
$personalGreeting  # Output: नमस्ते, दोस्त!

# Here-String का इस्तेमाल करते हुए
$part1 = "PowerShell"
$part2 = "रॉक्स!"
$multiline = @"
इसलिए कहते हैं:
$part1 $part2
"@
$multiline.Trim()  # Output:
                   # इसलिए कहते हैं:
                   # PowerShell रॉक्स!
```

## Deep Dive (गहराई में जानकारी)
Concatenation की अवधारणा नई नहीं है; यह मूल रूप से हर प्रोग्रामिंग भाषा में पाई जाती है। PowerShell में, आप '+' operator, फॉर्मेट operator `-f`, और here-strings का इस्तेमाल कर सकते हैं। ये विधियां अपनी simplicity और flexibility में भिन्न हैं। Plus operator सीधा और सरल है लेकिन बड़ी संख्या में strings के साथ धीमा हो सकता है। `-f` ऑपरेटर, कोड को readable रखते हुए dynamic values insert करने का एक शक्तिशाली तरीका है। Here-strings मल्टी-लाइन टेक्स्ट को संभालने के लिए बेहतर हैं, जिसमें वेरिएबल्स को भी embed किया जा सकता है।

## See Also (देखने योग्य लिंक्स)
- [About Automatic Variables in PowerShell](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_automatic_variables?view=powershell-7.1)
