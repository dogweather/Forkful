---
title:                "XML के साथ काम करना"
aliases:
- hi/kotlin/working-with-xml.md
date:                  2024-01-26T04:34:07.635085-07:00
model:                 gpt-4-0125-preview
simple_title:         "XML के साथ काम करना"

tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/kotlin/working-with-xml.md"
---

{{< edit_this_page >}}

## क्या और क्यों?
XML के साथ काम करना XML दस्तावेज़ों को पार्स करने, बनाने, और संशोधित करने में शामिल है - एक मार्कअप भाषा जो डेटा संग्रहण और हस्तांतरण के लिए होती है। प्रोग्रामर इसके साथ काम करते हैं क्योंकि बहुत सारी प्रणालियाँ अभी भी डेटा का आदान-प्रदान XML प्रारूप में करती हैं, और यह मौजूदा प्रौद्योगिकियों के साथ एकीकरण और विरासती समर्थन के लिए आवश्यक है।

## कैसे:
Kotlin में, आप पार्सिंग के लिए निर्मित `javax.xml.parsers` का उपयोग कर सकते हैं:

```Kotlin
import javax.xml.parsers.DocumentBuilderFactory
import org.w3c.dom.Document

fun parseXml(xmlData: String): Document {
    val dbFactory = DocumentBuilderFactory.newInstance()
    val dBuilder = dbFactory.newDocumentBuilder()
    return dBuilder.parse(xmlData.byteInputStream())
}
```
XML दस्तावेज़ बनाने के लिए, आप `javax.xml.transform` का उपयोग कर सकते हैं:

```Kotlin
import javax.xml.transform.TransformerFactory
import javax.xml.transform.dom.DOMSource
import javax.xml.transform.stream.StreamResult
import org.w3c.dom.Document
import java.io.StringWriter

fun convertDocumentToString(doc: Document): String {
    val transformer = TransformerFactory.newInstance().newTransformer()
    val result = StringWriter()
    transformer.transform(DOMSource(doc), StreamResult(result))
    return result.toString()
}
```
दस्तावेज़ के रूपांतरण के लिए नमूना आउटपुट सरलता से आपका XML सामग्री एक स्ट्रिंग प्रारूप में होगा।

## गहराई में जाने पर
XML 90 के दशक से वेब और सॉफ्टवेयर विकास का एक मुख्य तत्व रहा है, इसकी पठनीयता और संरचित पदानुक्रम के लिए पसंद किया जाता है। हालाँकि JSON ने वेब सेवाओं के लिए इसकी सादगी और छोटे संदेश आकार के कारण लोकप्रियता हासिल की है, XML एंटरप्राइज वातावरणों, SOAP-आधारित वेब सेवाओं, और कॉन्फ़िगरेशनों (जैसे कि एंड्रॉयड लेआउट फ़ाइलें) में प्रबल बना हुआ है।

Kotlin/Java की निर्मित सुविधाओं के अलावा, XML हैंडलिंग के लिए विभिन्न लाइब्रेरीज और APIs हैं, जैसे कि Simple XML Serialization और Jackson XML मॉड्यूल। लेकिन `javax.xml.parsers` और `javax.xml.transform` आमतौर पर बाहरी निर्भरताओं को जोड़े बिना अधिकांश आवश्यकताओं की सेवा करते हैं।

Kotlin में XML के साथ काम करते समय, चरित्र एनकोडिंग को उचित रूप से संभालना और XML इंजेक्शन हमलों से बचने के लिए XML इकाइयों को प्रबंधित करना महत्वपूर्ण कार्यान्वयन विवरणों में शामिल है। डेटा अखंडता सुनिश्चित करने के लिए XML पार्स करते समय नामस्थान जटिलताओं और स्कीमा सत्यापन पर विचार करें।

## यह भी देखें
- [Kotlin दस्तावेज़ीकरण](https://kotlinlang.org/docs/reference/)
- [Java DOM दस्तावेज़ीकरण](https://docs.oracle.com/javase/7/docs/api/org/w3c/dom/package-summary.html)
- [Simple XML Serialization](http://simple.sourceforge.net/)
- [Jackson XML मॉड्यूल](https://github.com/FasterXML/jackson-dataformat-xml)
