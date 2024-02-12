---
title:                "Debug-output afdrukken"
aliases:
- /nl/typescript/printing-debug-output/
date:                  2024-01-28T22:04:45.089280-07:00
model:                 gpt-4-0125-preview
simple_title:         "Debug-output afdrukken"

tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/nl/typescript/printing-debug-output.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?
Debugoutput is je zaklamp in een donker code steegje; het helpt je fouten te spotten door je een kijkje te geven in wat je code doet tijdens de uitvoering. Programmeurs doen het omdat we, nou ja, menselijk zijn en onze code is niet altijd perfect bij de eerste poging.

## Hoe te:
Wil je debugoutput afdrukken in TypeScript? Consolemethoden zijn je beste keuze. Zie `console.log`, `console.error` en vrienden in actie:

```TypeScript
// Basis log
console.log('Kijk Ma, ik ben aan het debuggen!');

// Gegroepeerde logs
console.group('Gebruikersgegevens');
console.log('Naam: John Doe');
console.log('Leeftijd: 34');
console.groupEnd();

// Tabel
console.table([{ a: 1, b: 'Y' }, { a: 'Z', b: 2 }]);

// Foutuitvoer
console.error('Oeps! Er is iets fout gegaan.');

// Waarschuwingsuitvoer
console.warn('Dit is een waarschuwing.');

// Een debuguitvoer
console.debug('Dit is een debugbericht.');
```

Voorbeelduitvoer:
```
Kijk Ma, ik ben aan het debuggen!
Gebruikersgegevens
    Naam: John Doe
    Leeftijd: 34
(index) a  b
0       1  "Y"
1       "Z" 2
Oeps! Er is iets fout gegaan.
Dit is een waarschuwing.
Dit is een debugbericht.
```

## Diepgaande Duik
Vroeger hadden we `alert()` – het was in je gezicht en blokkeerde alles totdat het behandeld was. Nu regeren de `console` methoden. Ze zijn minder opdringerig en komen met superkrachten: categoriseer berichten, print tabellen, of stijl uitvoer.

Alternatieven? Zeker. Je zou naar een bestand kunnen schrijven of berichten over het netwerk kunnen versturen voor op afstand loggen. Voor de browser geven tools zoals Chrome's DevTools je meer controle over je logniveaus en formaten.

Wat betreft de implementatie, `console` in TypeScript wordt JavaScript tijdens de uitvoering, en dat is waar alle echte actie plaatsvindt. Fancy TypeScript types veranderen hier niets aan—het is gewoon oude `console` onder de motorkap, browser of Node.

## Zie Ook
- [MDN Web Docs over Console](https://developer.mozilla.org/en-US/docs/Web/API/Console)
- [Node.js Console Documentatie](https://nodejs.org/api/console.html)
- [TypeScript Handboek](https://www.typescriptlang.org/docs/handbook/intro.html)
