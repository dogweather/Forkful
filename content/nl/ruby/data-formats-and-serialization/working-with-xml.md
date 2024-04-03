---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:11:29.932388-07:00
description: "Werken met XML betekent het parseren, genereren en manipuleren van XML\
  \ (eXtensible Markup Language) documenten met behulp van code. Programmeurs doen\
  \ dit\u2026"
lastmod: '2024-03-13T22:44:51.395231-06:00'
model: gpt-4-0125-preview
summary: Werken met XML betekent het parseren, genereren en manipuleren van XML (eXtensible
  Markup Language) documenten met behulp van code.
title: Werken met XML
weight: 40
---

## Hoe te:
Laten we REXML, inbegrepen bij Ruby, gebruiken om een XML-snippet te parsen:
```Ruby
require 'rexml/document'
include REXML

xml_data = <<-XML
<fruits>
  <fruit name="apple" color="green"/>
  <fruit name="banana" color="yellow"/>
</fruits>
XML

document = Document.new(xml_data)
document.elements.each('fruits/fruit') doen |element|
  puts "Naam: #{element.attributes['name']}, Kleur: #{element.attributes['color']}"
end
```
Uitvoer:
```
Naam: appel, Kleur: groen
Naam: banaan, Kleur: geel
```

XML genereren is ook eenvoudig:
```Ruby
doc = Document.new
doc.add_element 'fruits'
apple = doc.root.add_element 'fruit', {'name' => 'apple', 'color' => 'green'}
banana = doc.root.add_element 'fruit', {'name' => 'banana', 'color' => 'yellow'}
puts doc
```
XML-uitvoer:
```XML
<fruits>
  <fruit name="apple" color="green"/>
  <fruit name="banana" color="yellow"/>
</fruits>
```

## Diepduiken:
De wortels van XML gaan terug naar de jaren 90 als een vereenvoudigde subset van SGML voor webdocumenten. Het is langdradig, maar zeer gestructureerd, en dat is waarom het is blijven hangen. Het is niet het enige spel in de stad - JSON en YAML zijn populair geworden vanwege hun eenvoud - maar XML houdt sterk stand in veel enterprise en legacy-systemen.

Ruby biedt een paar manieren om met XML om te gaan. REXML is een volledig-Ruby bibliotheek die gemakkelijk te beginnen is. Nokogiri is een gem die snellere C-bibliotheken inpakt, die snelheid en extra functies biedt. Kiezen tussen hen? Begin met REXML voor kleinere taken en ga over naar Nokogiri als je meer kracht nodig hebt.

Onder de motorkap gaat het parsen van XML over het vertalen van strings naar DOM- of SAX-modellen. DOM creëert een boom in het geheugen, terwijl SAX het document streamt en gebeurtenissen afvuurt terwijl het wordt geparseerd. REXML biedt beide modellen, maar is meestal langzamer dan C-extensies zoals die gebruikt worden door Nokogiri.

## Zie ook:
- Ruby REXML-documentatie: https://www.rubydoc.info/stdlib/rexml
- Nokogiri-gem: https://nokogiri.org/
- XML-specificatie: https://www.w3.org/XML/
- Een introductie tot SAX: https://www.saxproject.org/
- YAML vs. JSON vs. XML vergelijking: https://www.upwork.com/resources/json-vs-xml-vs-yaml
