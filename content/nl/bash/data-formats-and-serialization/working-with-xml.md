---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:11:04.068587-07:00
description: "Werken met XML houdt in: het parsen, extraheren en manipuleren van gegevens\
  \ in het Extensible Markup Language-formaat. Programmeurs worstelen met XML,\u2026"
lastmod: '2024-03-13T22:44:51.008263-06:00'
model: gpt-4-0125-preview
summary: 'Werken met XML houdt in: het parsen, extraheren en manipuleren van gegevens
  in het Extensible Markup Language-formaat.'
title: Werken met XML
weight: 40
---

## Hoe:
Zo parseer je XML in Bash. Gereedschappen? xmllint en xmlstarlet. Door XML-elementen loopen? Absoluut. Voorbeeld met voorbeelduitvoer:

```bash
# Aannemende dat xmlstarlet is geïnstalleerd
# Installeren met: apt-get install xmlstarlet

# XML-inhoud parsen
cat <<EOF > voorbeeld.xml
<fruits>
  <fruit name="Appel"/>
  <fruit name="Banaan"/>
</fruits>
EOF

# Namen extraheren met xmlstarlet
xmlstarlet sel -t -m "//fruit" -v "@name" -n voorbeeld.xml

# Uitvoer zou moeten zijn:
# Appel
# Banaan
```

## Diepere Duik
Terug in de jaren '90, dook XML op als een simpeler alternatief voor SGML, maar gestructureerder dan HTML. Nu heeft het gezelschap – JSON, YAML, bijvoorbeeld. Maar XML is nog steeds springlevend, vooral in configuraties en op SOAP-gebaseerde webservices.

Wat betreft gereedschap, xmllint is comfortabel voor XML-validatie, xpath queries. xmlstarlet is het Zwitsers zakmes voor XML-kunstjes – query'en, bewerken, valideren, transformeren. In bash-scripts zijn ze superhelden voor XML-taken.

Onder de motorkap gebruikt xmllint libxml2 – de XML C parser. Het is snel, maar de foutmeldingen? Cryptisch. En xmlstarlet? Recursieve templates en de EXSLT-ondersteuning. Hersenkraker, maar krachtig.

## Zie Ook
- [xmlsoft.org](http://xmlsoft.org/): Libxml2 en xmllint spullen.
- [Stack Overflow](https://stackoverflow.com/questions/tagged/xml+bash): Problemen en oplossingen uit de echte wereld.
- [W3Schools XML Tutorial](https://www.w3schools.com/xml/): Basis van XML.
