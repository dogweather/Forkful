---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:11:57.407788-07:00
description: "Werken met XML omvat het manipuleren en toegang krijgen tot gegevens\
  \ gestructureerd in de eXtensible Markup Language. Programmeurs werken met XML om\u2026"
lastmod: '2024-03-13T22:44:51.054698-06:00'
model: gpt-4-0125-preview
summary: Werken met XML omvat het manipuleren en toegang krijgen tot gegevens gestructureerd
  in de eXtensible Markup Language.
title: Werken met XML
weight: 40
---

## Hoe:
```PowerShell
# Een XML-bestand laden in een variabele
[xml]$xmlContent = Get-Content 'pad\naar\uw\bestand.xml'

# XML-knooppunten benaderen
$books = $xmlContent.catalog.book
foreach ($book in $books) {
  Write-Output "Titel: $($book.title)"
}

# Een nieuw XML-element maken
$newBook = $xmlContent.CreateElement("book")
$newBook.SetAttribute("id", "bk999")
$xmlContent.DocumentElement.AppendChild($newBook)

# De XML terug opslaan naar bestand
$xmlContent.Save('pad\naar\uw\update\bestand.xml')
```
Voorbeelduitvoer:
```
Titel: Programmeren met PowerShell
Titel: XML Essentials
```

## Diepgaand
XML, of eXtensible Markup Language, bestaat al sinds eind jaren '90 en blijft een veelgebruikt formaat voor gestructureerde gegevens. PowerShell vereenvoudigt het werken met XML in vergelijking met traditionele parsingsmethoden; het zet XML direct om naar objecten, waardoor je met elementen kunt interageren via bekende dotnotatie.

Alternatieven voor XML zijn onder andere JSON, YAML of aangepaste gegevensformaten. JSON heeft bijvoorbeeld aan populariteit gewonnen vanwege zijn lichtgewicht aard en gebruiksgemak met webtechnologieën. Echter, de uitgebreide functies van XML zoals namespaces, schema's en XSLT-verwerking maken het vaak een betere keuze voor complexe documenten of industriestandaarden.

PowerShell gebruikt de XML-mogelijkheden van het .NET Framework voor zijn XML-behandeling. Dit betekent dat het niet alleen gaat om eenvoudige lees-schrijfoperaties; je kunt ook werken met XML-schema's voor validatie, XPath gebruiken voor queries en XSLT-transformaties uitvoeren, allemaal via PowerShell.

## Zie Ook
- [W3Schools XML tutorial](https://www.w3schools.com/xml/)
- [XML vs. JSON](https://www.json.org/json-en.html)
