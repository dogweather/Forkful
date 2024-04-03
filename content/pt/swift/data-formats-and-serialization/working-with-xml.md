---
date: 2024-01-26 04:35:59.006027-07:00
description: "Trabalhar com XML significa analisar e gerar dados XML em Swift. Os\
  \ programadores fazem isso para interc\xE2mbio de dados, especialmente quando se\
  \ integram a\u2026"
lastmod: '2024-03-13T22:44:46.945226-06:00'
model: gpt-4-0125-preview
summary: Trabalhar com XML significa analisar e gerar dados XML em Swift.
title: Trabalhando com XML
weight: 40
---

## Como fazer:
Swift oferece `XMLParser` e `XMLDocument` para a análise de dados XML. Aqui está um trecho para analisar uma simples string XML:

```swift
import Foundation

let xmlString = """
<?xml version="1.0" encoding="UTF-8"?>
<note>
    <to>Tove</to>
    <from>Jani</from>
    <heading>Lembrete</heading>
    <body>Não esqueça a festa na sexta-feira!</body>
</note>
"""

if let xmlData = xmlString.data(using: .utf8) {
    let parser = XMLParser(data: xmlData)
    parser.delegate = someParserDelegate // Seu XMLParserDelegate
    parser.parse()
}
```

Você também pode gerar XML usando `XMLDocument`:

```swift
import Foundation

let note = XMLElement(name: "note")
let to = XMLElement(name: "to", stringValue: "Tove")
note.addChild(to)
let xmlDoc = XMLDocument(rootElement: note)

print(xmlDoc.xmlString(options: .nodePrettyPrint))
```

Saída de amostra:

```xml
<note>
  <to>Tove</to>
</note>
```

## Aprofundamento
XML, ou Extensible Markup Language, existe desde o final dos anos 90. É verboso, mas legível por humanos, tornando-o adequado para estruturas de dados complexas. As capacidades de análise XML do Swift não são tão robustas quanto aquelas encontradas no ElementTree do Python ou no JAXB do Java, mas são suficientes para necessidades básicas.

Alternativas como JSON são muitas vezes preferidas em novos sistemas devido ao seu menor peso e parsers menos complexos, mas o XML ainda é proeminente em muitos sistemas empresariais e legados.

Ao trabalhar com XML em Swift, `XMLParser` é um parser baseado em fluxo, o que significa que ele lê o documento XML sequencialmente. Para arquivos XML grandes, isso é eficiente em termos de memória. No entanto, se você está procurando simplicidade e seus dados XML são razoavelmente pequenos, usar `XMLDocument` pode ser mais direto.

## Veja Também
- [Guia de Análise XML da Apple](https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/XMLParsing/XMLParsing.html)
- [Tutorial XML do W3Schools](https://www.w3schools.com/xml/)
