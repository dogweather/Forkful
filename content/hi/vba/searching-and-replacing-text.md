---
title:                "पाठ की खोज एवं प्रतिस्थापन"
aliases:
- hi/vba/searching-and-replacing-text.md
date:                  2024-02-01T22:02:26.862083-07:00
model:                 gpt-4-0125-preview
simple_title:         "पाठ की खोज एवं प्रतिस्थापन"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/vba/searching-and-replacing-text.md"
changelog:
  - 2024-02-01, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## क्या और क्यों?

विज़ुअल बेसिक फॉर एप्लिकेशन्स (VBA) में पाठ को खोजना और उसे बदलना दस्तावेजों, स्प्रेडशीट्स, और डेटाबेस को कार्यक्रम के अनुसार संपादित करने के लिए आवश्यक है। यह क्षमता प्रोग्रामर्स को थोक संपादन, त्रुटियों को सही करने या बिना मैनुअल हस्तक्षेप के बड़े डेटासेट्स में जानकारी को अपडेट करने के लिए स्वचालित बनाने में सक्षम बनाता है।

## कैसे:

VBA में, पाठ को खोजने और बदलने को `Replace` फ़ंक्शन का उपयोग करके या Excel या Word जैसे एप्लिकेशनों में विशिष्ट ऑब्जेक्ट मॉडल्स के माध्यम से प्राप्त किया जा सकता है। नीचे दोनों दृष्टिकोणों को इलस्ट्रेट करने वाले उदाहरण दिए गए हैं।

### `Replace` फ़ंक्शन का उपयोग:

`Replace` फ़ंक्शन सरल पाठ प्रतिस्थापनों के लिए सीधा है। इसका रूप होता है `Replace(expression, find, replaceWith[, start[, count[, compare]]])`.

उदाहरण:
```vb
Dim originalText As String
Dim newText As String

originalText = "Hello, World! Programming in VBA is fun."
newText = Replace(originalText, "World", "Everyone")

Debug.Print newText
```
आउटपुट:
```
Hello, Everyone! Programming in VBA is fun.
```

### Excel में खोजना और बदलना:

Excel के लिए, आप `Range.Replace` मेथड का उपयोग कर सकते हैं जो अधिक नियंत्रण प्रदान करता है, जैसे कि मामले की संवेदनशीलता और पूरे शब्द प्रतिस्थापन।

उदाहरण:
```vb
Sub ReplaceTextInExcel()
    Dim ws As Worksheet
    Set ws = ThisWorkbook.Sheets("Sheet1")

    With ws.Range("A1:A100") ' खोज करने के लिए रेंज निर्धारित करें
        .Replace What:="old", Replacement:="new", MatchCase:=False, LookAt:=xlPart
    End With
End Sub
```

### Word में खोजना और बदलना:

इसी तरह, Word में VBA के माध्यम से सुलभ एक शक्तिशाली `Find` और `Replace` सुविधा है।

उदाहरण:
```vb
Sub ReplaceTextInWord()
    Dim doc As Document
    Set doc = ActiveDocument
    
    With doc.Content.Find
        .Text = "specific"
        .Replacement.Text = "particular"
        .Execute Replace:=wdReplaceAll
    End With
End Sub
```

## गहन अध्ययन:

VBA में पाठ को खोजने और बदलने की क्षमता Microsoft Office एप्लिकेशनों में शुरुआती ऑटोमेशन क्षमताओं से जुड़ी है, जिससे दोहरावदार कार्यों को स्क्रिप्टिंग के माध्यम से उत्पादकता में महत्वपूर्ण वृद्धि हुई है। समय के साथ, ये कार्य अधिक शक्तिशाली और लचीले हो गए हैं, विविध उपयोग के मामलों की पूर्ति करने के लिए।

जहां VBA का `Replace` फ़ंक्शन सरल पाठ संचालनों के लिए सुविधाजनक है, वहीं Excel और Word ऑब्जेक्ट मॉडल्स अधिक नियंत्रण प्रदान करते हैं और एप्लिकेशन-विशिष्ट कार्यों के लिए उपयोग किए जाने चाहिए। वे उन्नत सुविधाओं जैसे पैटर्न मिलान, प्रारूप संरक्षण, और सूक्ष्म खोज मानदंड (उदाहरण के लिए, मामले का मिलान, पूरे शब्द) का समर्थन करते हैं।

हालांकि, VBA और इसकी पाठ संचालन क्षमताएं, Microsoft इकोसिस्टम के भीतर मजबूत होते हुए भी, उच्च-प्रदर्शन या अधिक जटिल पाठ संसाधन आवश्यकताओं के लिए हमेशा सर्वश्रेष्ठ उपकरण नहीं हो सकते हैं। नियमित अभिव्यक्तियों के लिए `re` जैसी पुस्तकालयों के साथ Python जैसी भाषाएँ अधिक शक्तिशाली और बहुमुखी पाठ संचालन विकल्प प्रदान करती हैं। लेकिन Microsoft Office एप्लिकेशनों के भीतर पहले से काम करने वालों के लिए, VBA खोज और प्रतिस्थापन कार्यों को स्वचालित करने के लिए एक सुलभ और प्रभावी विकल्प बनी हुई है।
