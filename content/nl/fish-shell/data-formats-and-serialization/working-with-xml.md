---
aliases:
- /nl/fish-shell/working-with-xml/
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:11:21.181022-07:00
description: "Werken met XML betekent het omgaan met gegevens in een alomtegenwoordig,\
  \ gestructureerd formaat dat wordt gebruikt in configuraties, berichtgeving en\u2026"
lastmod: 2024-02-18 23:09:02.352448
model: gpt-4-0125-preview
summary: "Werken met XML betekent het omgaan met gegevens in een alomtegenwoordig,\
  \ gestructureerd formaat dat wordt gebruikt in configuraties, berichtgeving en\u2026"
title: Werken met XML
---

{{< edit_this_page >}}

## Wat & Waarom?
Werken met XML betekent het omgaan met gegevens in een alomtegenwoordig, gestructureerd formaat dat wordt gebruikt in configuraties, berichtgeving en meer. Programmeurs manipuleren XML om gegevens te lezen, schrijven, bijwerken en op te vragen - essentieel voor interoperabiliteit in tal van apps en diensten.

## Hoe:
Fish heeft geen ingebouwde XML-parser, dus je zult externe hulpmiddelen zoals `xmllint` of `xmlstarlet` gebruiken. Hier is een fragment om waarden te lezen:

```fish
# Parse XML met behulp van xmlstarlet
echo '<root><element>Hallo Wereld</element></root>' | xmlstarlet sel -t -v "/root/element"
```

Uitvoer:
```
Hallo Wereld
```

Gebruik dit om XML te bewerken:

```fish
# Bewerk XML-element met xmlstarlet
echo '<root><element>Oude Waarde</element></root>' | xmlstarlet ed -u "/root/element" -v 'Nieuwe Waarde'
```

Uitvoer:
```xml
<?xml version="1.0"?>
<root>
  <element>Nieuwe Waarde</element>
</root>
```

## Diepgaande verkenning:
XML bestaat al sinds de late jaren '90, gemaakt voor leesbaarheid en machine-vriendelijkheid. Hoewel JSON een deel van XML's populariteit heeft overgenomen vanwege eenvoud, blijft XML verankerd waar documentvalidatie en namespaces sleutel zijn.

Alternatieven? Zeker—JSON, YAML, of zelfs binaire formaten zoals Protocol Buffers voor die prestatie-intensieve apps. Maar XML's schema en XSLT (voor XML-transformaties) kunnen dealbreakers zijn voor complexe scenario's waar robuustheid belangrijk is.

Onder de motorkap wikkelen hulpmiddelen zoals `xmlstarlet` krachtige bibliotheken zoals libxml2 in, waarbij je XPath en XQuery krijgt voor fijne XML-aanpassingen. Dit zijn niet alleen XML-tools maar gateways naar DOM-manipulatie, zoals je vergelijkbare concepten zou toepassen in elke taal die met XML te maken heeft.

## Zie Ook:
- [xmlstarlet Documentatie](http://xmlstar.sourceforge.net/doc/UG/xmlstarlet-ug.html)
- [Fish Documentatie](https://fishshell.com/docs/current/index.html)
- [XPath en XQuery Functies en Operatoren](https://www.w3.org/TR/xpath-functions/)
