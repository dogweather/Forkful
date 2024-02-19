---
aliases:
- /hi/c-sharp/searching-and-replacing-text/
date: 2024-01-20 17:57:57.065495-07:00
description: "\u091F\u0947\u0915\u094D\u0938\u094D\u091F \u0938\u0930\u094D\u091A\
  \ \u0915\u0930\u0928\u093E \u0914\u0930 \u0909\u0938\u0947 \u0930\u093F\u092A\u094D\
  \u0932\u0947\u0938 \u0915\u0930\u0928\u093E \u092E\u0924\u0932\u092C \u0939\u0948\
  \ \u0915\u093F\u0938\u0940 \u0936\u092C\u094D\u0926 \u092F\u093E \u0935\u093E\u0915\
  \u094D\u092F\u093E\u0902\u0936 \u0915\u094B \u0916\u094B\u091C\u0928\u093E \u0914\
  \u0930 \u0909\u0938\u0947 \u0928\u090F \u0936\u092C\u094D\u0926 \u0938\u0947 \u092C\
  \u0926\u0932\u0928\u093E\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\
  \u0930\u094D\u0938 \u092F\u0939 \u0915\u093E\u092E \u0907\u0938\u0932\u093F\u090F\
  \ \u0915\u0930\u0924\u0947 \u0939\u0948\u0902 \u0915\u094D\u092F\u094B\u0902\u0915\
  \u093F \u0905\u0915\u094D\u0938\u0930 \u0915\u094B\u0921\u2026"
lastmod: 2024-02-18 23:09:03.319019
model: gpt-4-1106-preview
summary: "\u091F\u0947\u0915\u094D\u0938\u094D\u091F \u0938\u0930\u094D\u091A \u0915\
  \u0930\u0928\u093E \u0914\u0930 \u0909\u0938\u0947 \u0930\u093F\u092A\u094D\u0932\
  \u0947\u0938 \u0915\u0930\u0928\u093E \u092E\u0924\u0932\u092C \u0939\u0948 \u0915\
  \u093F\u0938\u0940 \u0936\u092C\u094D\u0926 \u092F\u093E \u0935\u093E\u0915\u094D\
  \u092F\u093E\u0902\u0936 \u0915\u094B \u0916\u094B\u091C\u0928\u093E \u0914\u0930\
  \ \u0909\u0938\u0947 \u0928\u090F \u0936\u092C\u094D\u0926 \u0938\u0947 \u092C\u0926\
  \u0932\u0928\u093E\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\u0930\
  \u094D\u0938 \u092F\u0939 \u0915\u093E\u092E \u0907\u0938\u0932\u093F\u090F \u0915\
  \u0930\u0924\u0947 \u0939\u0948\u0902 \u0915\u094D\u092F\u094B\u0902\u0915\u093F\
  \ \u0905\u0915\u094D\u0938\u0930 \u0915\u094B\u0921\u2026"
title: "\u092A\u093E\u0920 \u0916\u094B\u091C\u0928\u093E \u0914\u0930 \u092C\u0926\
  \u0932\u0928\u093E"
---

{{< edit_this_page >}}

## What & Why? (क्या और क्यों?)
टेक्स्ट सर्च करना और उसे रिप्लेस करना मतलब है किसी शब्द या वाक्यांश को खोजना और उसे नए शब्द से बदलना। प्रोग्रामर्स यह काम इसलिए करते हैं क्योंकि अक्सर कोड में बार-बार उपयोग होने वाले शब्दों को सुधारना या अपडेट करना पड़ता है।

## How To: (कैसे करें:)
```C#
using System;
using System.Text.RegularExpressions;

class Program
{
    static void Main()
    {
        string originalText = "हम C# सीख रहे हैं। C# मजेदार है।";
        string searchText = "C#";
        string replaceText = "C#.NET";

        // सिंपल रिप्लेसमेंट
        string replacedText = originalText.Replace(searchText, replaceText);
        Console.WriteLine(replacedText);

        // Regex के जरिये रिप्लेसमेंट
        string regexReplacedText = Regex.Replace(originalText, searchText, replaceText);
        Console.WriteLine(regexReplacedText);
    }
}
```
सैंपल आउटपुट:
```
हम C#.NET सीख रहे हैं। C#.NET मजेदार है।
हम C#.NET सीख रहे हैं। C#.NET मजेदार है।
```

## Deep Dive (गहराई में जानकारी):
टेक्स्ट की सर्च और रिप्लेसमेंट की जरूरत पुराने प्रोग्राम्स में भी थी, जैसे कि पुराने टेक्स्ट एडिटर्स। हालाँकि, आज यह ऑपरेशन ज्यादा सोफिस्टिकेटेड हो गया है और Regex (Regular Expressions) के इस्तेमाल से बहुत फ्लेक्सिबल भी। रेगुलर एक्सप्रेशन का इस्तेमाल करके आप कॉम्प्लेक्स पैटर्न्स को भी सर्च और रिप्लेस कर सकते हैं। इसके अल्टरनेटिव में कई लाइब्रेरीज और टूल्स हैं जैसे कि sed (stream editor) जो लिनक्स पर यूज होता है। C# में `String.Replace` मेथड सीधा और सरल है, जबकि `Regex.Replace` जटिल पैटर्न्स के साथ काम कर सकता है।

## See Also (और जानें):
- Microsoft Docs on String.Replace method: [Microsoft Docs](https://docs.microsoft.com/dotnet/api/system.string.replace)
- Regular Expressions in .NET: [Regular Expressions](https://docs.microsoft.com/dotnet/standard/base-types/regular-expressions)
- .NET Regex.Replace method: [Regex.Replace](https://docs.microsoft.com/dotnet/api/system.text.regularexpressions.regex.replace)
