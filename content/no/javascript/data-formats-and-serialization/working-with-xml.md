---
date: 2024-01-26 04:32:37.548223-07:00
description: "\xC5 jobbe med XML betyr \xE5 analysere, manipulere og produsere XML-innhold\
  \ ved hjelp av kode. Programmerere gj\xF8r det fordi XML er mye brukt til\u2026"
lastmod: '2024-03-13T22:44:41.207660-06:00'
model: gpt-4-0125-preview
summary: "\xC5 jobbe med XML betyr \xE5 analysere, manipulere og produsere XML-innhold\
  \ ved hjelp av kode."
title: "\xC5 jobbe med XML"
weight: 40
---

## Hvordan:
Slik analyserer du XML:

```javascript
let parser = new DOMParser();
let xmlString = `<note>
                    <to>Bruker</to>
                    <from>Forfatter</from>
                    <heading>Påminnelse</heading>
                    <body>Ikke glem meg denne helgen!</body>
                 </note>`;

let xmlDoc = parser.parseFromString(xmlString, "application/xml");
console.log(xmlDoc.getElementsByTagName('to')[0].childNodes[0].nodeValue);
// Utdata: Bruker
```

Og for å produsere XML:

```javascript
let xmlDocument = document.implementation.createDocument('', '', null);
let noteElement = xmlDocument.createElement('note');
noteElement.appendChild(xmlDocument.createElement('to')).textContent = 'Bruker';
xmlDocument.appendChild(noteElement);
let serializer = new XMLSerializer();
let xmlString = serializer.serializeToString(xmlDocument);
console.log(xmlString);
// Utdata: <note><to>Bruker</to></note>
```

## Dyp dykk
XML står for eXtensible Markup Language, et dataformat som har vært rundt siden slutten av 90-tallet. Det definerer et sett med regler for koding av dokumenter som både mennesker og maskiner kan lese. Historisk sett fikk XML oppmerksomhet for sin fleksibilitet og strukturerte hierarki, noe som gjorde det til et valg for webtjenester, som SOAP, og tallrike konfigurasjonsfiler.

Alternativer til XML inkluderer JSON (JavaScript Object Notation), som har blitt populært for sin enkelhet i bruk med JavaScript og mindre vekt. YAML er et annet alternativ, verdsatt for å være både menneskevennlig og et vanlig valg for konfigurasjon.

XML er implementert i JavaScript ved hjelp av DOMParser- og XMLSerializer-grensesnittene. XML DOM (Document Object Model) tillater navigering og redigering av XML-dokumenter på samme måte som du ville ha gjort med HTML. Til tross for JSONs oppstigning, er forståelsen av XML nøkkelen, ettersom mange eldre systemer og spesifikke industrier fortsatt stoler på det for datautveksling.

## Se også
- MDN Web Docs (XML Parsing): https://developer.mozilla.org/en-US/docs/Web/API/DOMParser
- W3Schools (XML DOM Tutorial): https://www.w3schools.com/xml/dom_intro.asp
- "Hva er XML?": https://www.w3.org/XML/
