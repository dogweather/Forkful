---
title:                "स्ट्रिंग का अंतर्कलन"
html_title:           "Arduino: स्ट्रिंग का अंतर्कलन"
simple_title:         "स्ट्रिंग का अंतर्कलन"
programming_language: "PowerShell"
category:             "PowerShell"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/powershell/interpolating-a-string.md"
---

{{< edit_this_page >}}

# स्ट्रिंग इंटरपोलेशन: PowerShell प्रोग्रामिंग में असली शक्ति

## क्या और क्यों?
स्ट्रिंग इंटरपोलेशन | स्ट्रिंग में वेरिएबल की मूल्यों को संदर्भित करना है। इसे कार्यान्वित करने का मुख्य उद्देश्य प्रोग्रामरों को कोड में आसानता और पठनीयता प्रदान करना है।

## कैसे:

निम्नलिखित कोड उदाहरण स्थलीय चर के संदर्भ को इंटरपोलेट करने का उपयोग करता है:

```PowerShell
$name = "Vijay"
"नमस्ते, $name!"
```

उपरोक्त स्क्रिप्ट को चलाने से आपको निम्न आउटपुट मिलेगा:

```PowerShell
नमस्ते, Vijay!
```

## गहरा डाइव
1. इतिहास: PowerShell में स्ट्रिंग इंटरपोलेशन की क्षमता इसे अधिक लचीला और पठनीय बनाने के लिए जोडी गई थी। यह विशेष रूप से जटिल कोडिंग कार्यों को आसान बनाता है।
2. विकल्प: `$()` वाली वर्णनीय स्थलीयता ऑपरेटर का एक अन्य उपयोग होता है, जिसे ऐसे वेरिएबल के संदर्भ के लिए इंटरपोलेशन की आवश्यकता हो सकती है जिनमें एक से अधिक शब्द हों।
3. कार्यान्वयन विवरण: PowerShell में, डबल कोट्स " " इंटरपोलेशन का उपयोग करेंगे, जबकि सिंगल कोट्स ' ' वेरिएबल संदर्भित करने में असमर्थ रहेंगे।

## और देखें
1. [स्ट्रिंग इंटरपोलेशन में PowerShell](https://docs.microsoft.com/powershell/scripting/learn/deep-dives/everything-about-string-substitutions?view=powershell-7.1)
2. [PowerShell कोडिंग स्टैंडर्ड्स और प्रथाएं](https://poshcode.gitbooks.io/powershell-practice-and-style/content/Style-Guide/Quoting-Rules.html)