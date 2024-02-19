---
aliases:
- /no/typescript/working-with-xml/
date: 2024-01-26 04:36:21.322905-07:00
description: "\xC5 jobbe med XML betyr \xE5 analysere, manipulere og skrive XML-data\
  \ ved hjelp av programmering. Programmerere h\xE5ndterer XML for \xE5 utveksle data\
  \ p\xE5 tvers av\u2026"
lastmod: 2024-02-18 23:08:53.668255
model: gpt-4-0125-preview
summary: "\xC5 jobbe med XML betyr \xE5 analysere, manipulere og skrive XML-data ved\
  \ hjelp av programmering. Programmerere h\xE5ndterer XML for \xE5 utveksle data\
  \ p\xE5 tvers av\u2026"
title: "\xC5 jobbe med XML"
---

{{< edit_this_page >}}

## Hva og hvorfor?
Å jobbe med XML betyr å analysere, manipulere og skrive XML-data ved hjelp av programmering. Programmerere håndterer XML for å utveksle data på tvers av forskjellige systemer, for konfigurasjonsfiler, eller når de jobber med standarder som SOAP som er avhengige av XML.

## Hvordan:
```TypeScript
import { parseString } from 'xml2js';

// Eksempel på XML
const xml = `<note>
                <to>Bruker</to>
                <from>Forfatter</from>
                <heading>Påminnelse</heading>
                <body>Ikke glem møtet!</body>
             </note>`;

// Analyser XML til JSON
parseString(xml, (err, result) => {
    if(err) throw err;
    console.log(result);
});

// Forutsatt at parsingen var vellykket, kan utdataene se slik ut:
// { note:
//    { to: ['Bruker'],
//      from: ['Forfatter'],
//      heading: ['Påminnelse'],
//      body: ['Ikke glem møtet!'] } 
}
```

## Dypdykk
XML, eller Extensible Markup Language, har vært rundt siden slutten av 90-tallet. Dens selvbeskrivende natur og menneskelesbare format gjorde det raskt populært for ulike applikasjoner som RSS-feeder, konfigurasjonsstyring, og selv kontordokumentformater som Microsoft Office Open XML. Men, det er verbose sammenlignet med JSON, og tiden har forandret seg. JSON har fått søkelyset for webbaserte API-er på grunn av sin lettere vekt og innebygde kompatibilitet med JavaScript.

Likevel, XML er ikke død. Det brukes i storskala bedriftssystemer og for dokumentstandarder som ikke har skiftet til JSON. Verktøy som `xml2js` for TypeScript eller `lxml` i Python beviser at det fortsatt er et behov for XML-manipulasjon i programmering.

TypeScript har ikke innebygd støtte for XML slik som det har for JSON. I stedet jobber du med biblioteker. `xml2js` er et eksempel. Det transformerer XML til JSON, noe som gjør dataene lettere for JavaScript-eksperter å jobbe med.

## Se også
- [MDN Web Docs om XML](https://developer.mozilla.org/en-US/docs/Web/XML/XML_introduction)
- [xml2js npm-pakke](https://www.npmjs.com/package/xml2js)
- [W3Schools XML-opplæring](https://www.w3schools.com/xml/)
