---
title:                "XML के साथ काम करना"
date:                  2024-01-26T04:36:44.918323-07:00
model:                 gpt-4-0125-preview
simple_title:         "XML के साथ काम करना"
programming_language: "Swift"
category:             "Swift"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/hi/swift/working-with-xml.md"
---

{{< edit_this_page >}}

## क्या और क्यों?
Swift में XML के साथ काम करना का मतलब है XML डेटा को पार्स करना और उत्पन्न करना। प्रोग्रामर ऐसा डेटा इंटरचेंज के लिए करते हैं, विशेष रूप से जब उन्हें उन सिस्टमों के साथ एकीकृत करना होता है जहां XML मानक प्रारूप है।

## कैसे करें:
Swift `XMLParser` और `XMLDocument` को XML डेटा पार्स करने के लिए प्रदान करता है। यहाँ एक साधारण XML स्ट्रिंग को पार्स करने के लिए एक स्निपेट है:

```swift
import Foundation

let xmlString = """
<?xml version="1.0" encoding="UTF-8"?>
<note>
    <to>Tove</to>
    <from>Jani</from>
    <heading>Reminder</heading>
    <body>शुक्रवार को पार्टी को मत भूलना!</body>
</note>
"""

if let xmlData = xmlString.data(using: .utf8) {
    let parser = XMLParser(data: xmlData)
    parser.delegate = someParserDelegate // आपका XMLParserDelegate
    parser.parse()
}
```

आप `XMLDocument` का उपयोग करके XML भी उत्पन्न कर सकते हैं:

```swift
import Foundation

let note = XMLElement(name: "note")
let to = XMLElement(name: "to", stringValue: "Tove")
note.addChild(to)
let xmlDoc = XMLDocument(rootElement: note)

print(xmlDoc.xmlString(options: .nodePrettyPrint))
```

नमूना आउटपुट:

```xml
<note>
  <to>Tove</to>
</note>
```

## गहराई में जानें
XML, या Extensible Markup Language, 90 के दशक के अंत से आसपास रहा है। यह वर्बोस है लेकिन मानव-पठनीय, जो इसे जटिल डेटा संरचनाओं के लिए एक अच्छा फिट बनाता है। Swift की XML पार्सिंग क्षमताएँ Python के ElementTree या Java के JAXB जितनी मजबूत नहीं हैं, लेकिन बुनियादी जरूरतों के लिए वे काम कर जाती हैं।

नए सिस्टमों में अक्सर JSON जैसे विकल्पों को हल्का वजन और कम जटिल पार्सर के कारण पसंद किया जाता है, लेकिन XML अभी भी कई उद्यम और विरासती सिस्टमों में प्रमुख है।

Swift में XML के साथ काम करते समय, `XMLParser` एक स्ट्रीम-आधारित पार्सर है जिसका अर्थ है कि यह XML दस्तावेज़ को क्रमिक रूप से पढ़ता है। बड़ी XML फाइलों के लिए, यह मेमोरी-कुशल है। हालाँकि, यदि आप सादगी की तलाश में हैं और आपका XML डेटा उचित रूप से छोटा है, तो `XMLDocument` का उपयोग करना अधिक सीधा हो सकता है।

## देखें भी
- [Apple की XML पार्सिंग गाइड](https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/XMLParsing/XMLParsing.html)
- [W3Schools XML ट्यूटोरियल](https://www.w3schools.com/xml/)
