---
date: 2024-01-26 03:47:26.170190-07:00
description: "Avrunding av tall er \xE5 beskj\xE6re et tall til en spesifikk presisjon.\
  \ Programmerere gj\xF8r dette for \xE5 kontrollere numerisk utdata for lesbarhet,\u2026"
lastmod: '2024-03-13T22:44:40.527173-06:00'
model: gpt-4-0125-preview
summary: "Avrunding av tall er \xE5 beskj\xE6re et tall til en spesifikk presisjon."
title: Avrunding av tall
weight: 13
---

## Hvordan:
Avrunding i TypeScript kan gjøres ved hjelp av flere metoder. Her er en kjapp gjennomgang:

```typescript
// Math.round avrunder til nærmeste heltall
console.log(Math.round(1.5)); // Utdata: 2

// Math.ceil avrunder opp til nærmeste heltall
console.log(Math.ceil(1.1)); // Utdata: 2

// Math.floor avrunder ned til nærmeste heltall
console.log(Math.floor(1.8)); // Utdata: 1

// toFixed avrunder til et fast antall desimaler
let num = 1.23456;
console.log(num.toFixed(2)); // Utdata: "1.23"
// Merk: toFixed returnerer en streng! Bruk parseFloat for å konvertere tilbake ved behov.
console.log(parseFloat(num.toFixed(2))); // Utdata: 1.23
```

## Dypdykk
I gamle dager var avrunding et must på grunn av begrenset plass og presisjonsproblemer i tidlige datamaskiner. I dag kan flyttallsaritmetikk føre til snodige resultater på grunn av hvordan tall lagres i binærform. Alternativer til avrunding inkluderer floor, ceil, og trunc (for å kutte av desimaler uten avrunding).

Interne detaljer er verdt å merke seg: `Math.round` følger "avrund halv opp" (også kjent som "kommersiell avrunding"), mens `Math.floor` og `Math.ceil` er enkle og greie. `toFixed` kan gi uventede resultater fordi det returnerer en streng, og det avrunder ved å bruke "avrund halv til jevnt" (også kjent som "bankers avrunding"), spesielt nyttig for å redusere skjevhet ved avrunding av samme tall flere ganger.

## Se Også
- [MDN - Math.round()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/round)
- [MDN - Math.ceil()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/ceil)
- [MDN - Math.floor()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/floor)
- [MDN - toFixed()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toFixed)
- [IEEE Standard for Floating-Point Arithmetic (IEEE 754)](https://ieeexplore.ieee.org/document/4610935)
