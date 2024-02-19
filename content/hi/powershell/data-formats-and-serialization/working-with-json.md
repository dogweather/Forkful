---
aliases:
- /hi/powershell/working-with-json/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:24:04.883165-07:00
description: "PowerShell \u0915\u093E JSON (JavaScript Object Notation) \u0915\u0947\
  \ \u0938\u093E\u0925 \u090F\u0915\u0940\u0915\u0930\u0923 \u092A\u093E\u0930\u094D\
  \u0938\u093F\u0902\u0917 (\u092A\u0922\u093C\u0928\u093E) \u0914\u0930 \u091C\u0947\
  \u0928\u0930\u0947\u091F\u093F\u0902\u0917 (\u0932\u093F\u0916\u0928\u093E) JSON\
  \ \u0921\u0947\u091F\u093E \u0915\u0947 \u092C\u093E\u0930\u0947 \u092E\u0947\u0902\
  \ \u0939\u0948, \u091C\u094B \u0935\u0947\u092C \u092A\u0930 \u0921\u0947\u091F\u093E\
  \ \u0935\u093F\u0928\u093F\u092E\u092F \u0915\u0947 \u0932\u093F\u090F\u2026"
lastmod: 2024-02-18 23:09:03.777289
model: gpt-4-0125-preview
summary: "PowerShell \u0915\u093E JSON (JavaScript Object Notation) \u0915\u0947 \u0938\
  \u093E\u0925 \u090F\u0915\u0940\u0915\u0930\u0923 \u092A\u093E\u0930\u094D\u0938\
  \u093F\u0902\u0917 (\u092A\u0922\u093C\u0928\u093E) \u0914\u0930 \u091C\u0947\u0928\
  \u0930\u0947\u091F\u093F\u0902\u0917 (\u0932\u093F\u0916\u0928\u093E) JSON \u0921\
  \u0947\u091F\u093E \u0915\u0947 \u092C\u093E\u0930\u0947 \u092E\u0947\u0902 \u0939\
  \u0948, \u091C\u094B \u0935\u0947\u092C \u092A\u0930 \u0921\u0947\u091F\u093E \u0935\
  \u093F\u0928\u093F\u092E\u092F \u0915\u0947 \u0932\u093F\u090F\u2026"
title: "JSON \u0915\u0947 \u0938\u093E\u0925 \u0915\u093E\u092E \u0915\u0930\u0928\
  \u093E"
---

{{< edit_this_page >}}

## क्या और क्यों?

PowerShell का JSON (JavaScript Object Notation) के साथ एकीकरण पार्सिंग (पढ़ना) और जेनरेटिंग (लिखना) JSON डेटा के बारे में है, जो वेब पर डेटा विनिमय के लिए एक सामान्य प्रारूप है। प्रोग्रामर्स JSON के साथ काम करते हैं ताकि वे वेब APIs, कॉन्फ़िगरेशन फ़ाइलों के साथ इंटरैक्ट कर सकें, या इसकी हल्के और भाषा-स्वतंत्र प्रकृति के कारण विभिन्न भाषाओं और प्लेटफॉर्म्स के बीच डेटा विनिमय की सुविधा प्रदान कर सकें।

## कैसे:

### JSON का पार्सिंग

PowerShell में JSON को पढ़ने या पार्स करने के लिए, आप `ConvertFrom-Json` cmdlet का उपयोग कर सकते हैं। एक JSON स्ट्रिंग दिए जाने पर, यह cmdlet इसे एक PowerShell ऑब्जेक्ट में बदल देता है।

```powershell
$json = '{"name": "John Doe", "age": 30, "city": "New York"}'
$person = $json | ConvertFrom-Json
$person.name
```

नमूना आउटपुट:

```
John Doe
```

यह उदाहरण दिखाता है कि कैसे एक सरल JSON स्ट्रिंग को पार्स किया जाए ताकि परिणामस्वरूप ऑब्जेक्ट के गुणों तक पहुँचा जा सके।

### JSON का जेनरेट करना

एक PowerShell ऑब्जेक्ट से JSON उत्पन्न करने के लिए, आप `ConvertTo-Json` cmdlet का उपयोग कर सकते हैं। यह डेटा को एक वेब सर्विस को भेजने या एक कॉन्फ़िगरेशन फ़ाइल में सेव करने के लिए तैयार करने में सहायक है।

```powershell
$person = [PSCustomObject]@{
    name = "Jane Doe"
    age = 25
    city = "Los Angeles"
}
$json = $person | ConvertTo-Json
Write-Output $json
```

नमूना आउटपुट:

```json
{
    "name":  "Jane Doe",
    "age":  25,
    "city":  "Los Angeles"
}
```

यह कोड स्निपेट एक PowerShell ऑब्जेक्ट बनाता है और फिर इसे एक JSON स्ट्रिंग में बदल देता है।
