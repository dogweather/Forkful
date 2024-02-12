---
title:                "HTML विश्लेषण"
aliases:
- hi/powershell/parsing-html.md
date:                  2024-02-03T19:13:28.589724-07:00
model:                 gpt-4-0125-preview
simple_title:         "HTML विश्लेषण"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/powershell/parsing-html.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## क्या और क्यों?
PowerShell में HTML पार्सिंग का अर्थ है HTML सामग्री का विश्लेषण करना ताकि विशेष डेटा निकाला जा सके या वेब-संबंधित कार्यों को स्वचालित किया जा सके। प्रोग्रामर इसे वेब पेजों के साथ इंटरैक्ट करने, वेब सामग्री को स्क्रेप करने, या फार्म सबमिशन और अन्य वेब इंटरैक्शन को वेब ब्राउज़र की आवश्यकता के बिना स्वचालित करने के लिए करते हैं।

## कैसे:

PowerShell में मूल रूप से कोई समर्पित HTML पार्सर नहीं है, लेकिन आप `Invoke-WebRequest` cmdlet का उपयोग करके HTML सामग्री तक पहुंच सकते हैं और उसे पार्स कर सकते हैं। अधिक जटिल पार्सिंग और मैनिपुलेशन के लिए, HtmlAgilityPack, एक लोकप्रिय .NET लाइब्रेरी, का उपयोग किया जा सकता है।

### `Invoke-WebRequest` का उपयोग करना:

```powershell
# एक वेबपेज से शीर्षक फेच करने के लिए सरल उदाहरण
$response = Invoke-WebRequest -Uri 'http://example.com'
# DOM तत्वों तक पहुंचने के लिए ParsedHtml प्रॉपर्टी का इस्तेमाल करें
$title = $response.ParsedHtml.title
Write-Output $title
```

नमूना आउटपुट:

```
उदाहरण डोमेन
```

### HtmlAgilityPack का उपयोग करना:

सबसे पहले, आपको HtmlAgilityPack इंस्टॉल करना होगा। आप इसे NuGet पैकेज मैनेजर के माध्यम से कर सकते हैं:

```powershell
Install-Package HtmlAgilityPack -ProviderName NuGet
```

फिर, आप इसका उपयोग PowerShell में HTML पार्स करने के लिए कर सकते हैं:

```powershell
# HtmlAgilityPack असेंबली लोड करें
Add-Type -Path "path\to\HtmlAgilityPack.dll"

# एक HtmlDocument ऑब्जेक्ट बनाएँ
$doc = New-Object HtmlAgilityPack.HtmlDocument

# एक फाइल या वेब रिक्वेस्ट से HTML लोड करें
$htmlContent = (Invoke-WebRequest -Uri "http://example.com").Content
$doc.LoadHtml($htmlContent)

# तत्वों को निकालने के लिए XPath या अन्य क्वेरी मेथड्स का उपयोग करें
$node = $doc.DocumentNode.SelectSingleNode("//h1")

if ($node -ne $null) {
    Write-Output $node.InnerText
}
```

नमूना आउटपुट:

```
वेलकम टू Example.com!
```

इन उदाहरणों में, `Invoke-WebRequest` सरल कार्यों के लिए बेहतर है, जबकि HtmlAgilityPack जटिल HTML पार्सिंग और मैनिपुलेशन के लिए कहीं अधिक समृद्ध सुविधाओं का प्रस्ताव करता है।
