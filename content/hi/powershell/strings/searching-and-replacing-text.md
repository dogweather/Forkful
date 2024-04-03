---
date: 2024-01-20 17:58:57.552360-07:00
description: "\u0938\u0930\u094D\u091A\u093F\u0902\u0917 \u0914\u0930 \u0930\u093F\
  \u092A\u094D\u0932\u0947\u0938\u093F\u0902\u0917 \u091F\u0947\u0915\u094D\u0938\u094D\
  \u091F \u0915\u093E \u092E\u0924\u0932\u092C \u0939\u0948, \u092B\u093E\u0907\u0932\
  \u094B\u0902 \u092F\u093E \u0938\u094D\u091F\u094D\u0930\u093F\u0902\u0917\u094D\
  \u0938 \u092E\u0947\u0902 \u0935\u093F\u0936\u0947\u0937 \u091F\u0947\u0915\u094D\
  \u0938\u094D\u091F \u0915\u094B \u0922\u0942\u0901\u0922\u0928\u093E \u0914\u0930\
  \ \u092C\u0926\u0932\u0928\u093E\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\
  \u093E\u092E\u0930\u094D\u0938 \u092F\u0939 \u0907\u0938\u0932\u093F\u090F \u0915\
  \u0930\u0924\u0947 \u0939\u0948\u0902 \u0915\u094D\u092F\u094B\u0902\u0915\u093F\
  \ \u0915\u0908 \u092C\u093E\u0930 \u0938\u092E\u093E\u0928\u2026"
lastmod: '2024-03-13T22:44:52.673924-06:00'
model: gpt-4-1106-preview
summary: "\u0938\u0930\u094D\u091A\u093F\u0902\u0917 \u0914\u0930 \u0930\u093F\u092A\
  \u094D\u0932\u0947\u0938\u093F\u0902\u0917 \u091F\u0947\u0915\u094D\u0938\u094D\u091F\
  \ \u0915\u093E \u092E\u0924\u0932\u092C \u0939\u0948, \u092B\u093E\u0907\u0932\u094B\
  \u0902 \u092F\u093E \u0938\u094D\u091F\u094D\u0930\u093F\u0902\u0917\u094D\u0938\
  \ \u092E\u0947\u0902 \u0935\u093F\u0936\u0947\u0937 \u091F\u0947\u0915\u094D\u0938\
  \u094D\u091F \u0915\u094B \u0922\u0942\u0901\u0922\u0928\u093E \u0914\u0930 \u092C\
  \u0926\u0932\u0928\u093E\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\u0930\u093E\u092E\
  \u0930\u094D\u0938 \u092F\u0939 \u0907\u0938\u0932\u093F\u090F \u0915\u0930\u0924\
  \u0947 \u0939\u0948\u0902 \u0915\u094D\u092F\u094B\u0902\u0915\u093F \u0915\u0908\
  \ \u092C\u093E\u0930 \u0938\u092E\u093E\u0928 \u091C\u093E\u0928\u0915\u093E\u0930\
  \u0940 \u0915\u094B \u0905\u092A\u0921\u0947\u091F \u0915\u0930\u0928\u093E \u0939\
  \u094B\u0924\u093E \u0939\u0948, \u0917\u0932\u0924\u093F\u092F\u094B\u0902 \u0915\
  \u094B \u0938\u0939\u0940 \u0915\u0930\u0928\u093E \u0939\u094B\u0924\u093E \u0939\
  \u0948 \u092F\u093E \u0921\u0947\u091F\u093E \u0915\u094B \u092E\u093E\u0928\u0915\
  \u0940\u0915\u0943\u0924 \u0915\u0930\u0928\u093E \u0939\u094B\u0924\u093E \u0939\
  \u0948\u0964."
title: "\u092A\u093E\u0920 \u0916\u094B\u091C\u0928\u093E \u0914\u0930 \u092C\u0926\
  \u0932\u0928\u093E"
weight: 10
---

## How to: (कैसे करें:)
```PowerShell
# फाइल से टेक्स्ट सर्च और रिप्लेस
(Get-Content 'example.txt').Replace('पुराना', 'नया') | Set-Content 'example.txt'

# परिणाम को चेक करना
Get-Content 'example.txt'
```
यह `example.txt` फाइल में हर `पुराना` शब्द को `नया` के साथ बदल देगा।

```PowerShell
# रेगेक्स का इस्तेमाल करके अधिक जटिल सर्च और रिप्लेस
$content = [IO.File]::ReadAllText('example.txt')
$pattern = 'पुराना'
$replacement = 'नया'
$regex = [regex]$pattern
$updatedContent = $regex.Replace($content, $replacement)
[IO.File]::WriteAllText('example.txt', $updatedContent)
```

## Deep Dive (गहराई में जानकारी):
सर्च और रिप्लेस टेक्स्ट की कला पुरानी है। पहले, लोग टाइपराइटर पर भी गलतियों को सही करने के लिए इसी तरह की क्रियाएँ करते थे। कंप्यूटरों के आने से, इसे एडिटर्स और स्क्रिप्टिंग लैंग्वेजेज ने बहुत आसान बना दिया। जैसे PowerShell में `.Replace()` और `[regex]` का इस्तेमाल। इसके अल्टरनेटिव हैं, जैसे की `sed` लिनक्स पर और `findstr` विंडोज़ CMD में। अवधारणा एक ही है, लेकिन इम्प्लीमेंटेशन अलग-अलग संभावनाएँ प्रस्तुत करती हैं।

## See Also (इसे भी देखें):
- [PowerShell स्क्रिप्टिंग गाइड](https://docs.microsoft.com/en-us/powershell/scripting/)
- [Regex सपोर्ट इन PowerShell](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_regular_expressions?view=powershell-7.1)
