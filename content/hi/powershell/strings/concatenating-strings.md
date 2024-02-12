---
title:                "स्ट्रिंग को जोड़ना"
aliases:
- /hi/powershell/concatenating-strings/
date:                  2024-01-20T17:35:50.086154-07:00
model:                 gpt-4-1106-preview
simple_title:         "स्ट्रिंग को जोड़ना"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/powershell/concatenating-strings.md"
---

{{< edit_this_page >}}

## What & Why? (क्या और क्यों?)

String concatenation का मतलब है दो या दो से ज्यादा strings को जोड़ना ताकि वे एक साथ एक नया संदेश बना सकें। Programmers इसे इसलिए करते हैं ताकि वे डाटा को फॉर्मेट कर सकें और यूजर्स के लिए मेनिंगफुल इन्फोर्मेशन डिस्प्ले कर सकें।

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
