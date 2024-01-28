---
title:                "Praca z XML"
date:                  2024-01-26T04:36:01.119861-07:00
model:                 gpt-4-0125-preview
simple_title:         "Praca z XML"
programming_language: "Swift"
category:             "Swift"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/swift/working-with-xml.md"
---

{{< edit_this_page >}}

## Co i dlaczego?
Praca z XML w kontekście Swift oznacza analizę i generowanie danych XML. Programiści robią to dla wymiany danych, zwłaszcza podczas integracji z systemami, gdzie XML jest standardowym formatem.

## Jak to zrobić:
Swift zapewnia `XMLParser` oraz `XMLDocument` do analizy danych XML. Oto fragment kodu do analizy prostego ciągu XML:

```swift
import Foundation

let xmlString = """
<?xml version="1.0" encoding="UTF-8"?>
<note>
    <to>Tove</to>
    <from>Jani</from>
    <heading>Przypomnienie</heading>
    <body>Nie zapomnij o imprezie w piątek!</body>
</note>
"""

if let xmlData = xmlString.data(using: .utf8) {
    let parser = XMLParser(data: xmlData)
    parser.delegate = someParserDelegate // Twój XMLParserDelegate
    parser.parse()
}
```

Możesz też generować XML za pomocą `XMLDocument`:

```swift
import Foundation

let note = XMLElement(name: "note")
let to = XMLElement(name: "to", stringValue: "Tove")
note.addChild(to)
let xmlDoc = XMLDocument(rootElement: note)

print(xmlDoc.xmlString(options: .nodePrettyPrint))
```

Przykładowy wynik:

```xml
<note>
  <to>Tove</to>
</note>
```

## Pogłębiona analiza
XML, czyli Rozszerzalny Język Znaczników, istnieje od końca lat 90. Jest rozwlekły, ale czytelny dla człowieka, co czyni go dobrym wyborem dla skomplikowanych struktur danych. Możliwości analizy XML w Swifcie nie są tak rozbudowane jak te dostępne w Python's ElementTree czy Java's JAXB, ale wystarczają do zaspokojenia podstawowych potrzeb.

Alternatywy, takie jak JSON, są często preferowane w nowych systemach ze względu na ich mniejszą wagę i mniej skomplikowane parsery, ale XML jest nadal obecny w wielu systemach korporacyjnych i starszych.

Pracując z XML w Swifcie, `XMLParser` to parser oparty na strumieniach, co oznacza, że czyta dokument XML sekwencyjnie. Dla dużych plików XML jest to wydajne pod względem pamięci. Jednakże, jeśli szukasz prostoty i Twoje dane XML są raczej małe, użycie `XMLDocument` może być bardziej bezpośrednie.

## Zobacz również
- [Przewodnik po analizie XML od Apple](https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/XMLParsing/XMLParsing.html)
- [Samouczek XML z W3Schools](https://www.w3schools.com/xml/)
