---
date: 2024-01-20 17:32:07.595558-07:00
description: "Beregning av en dato i fremtiden eller fortiden inneb\xE6rer \xE5 legge\
  \ til eller trekke fra tid fra en n\xE5v\xE6rende dato. Programmerere bruker dette\
  \ for \xE5\u2026"
lastmod: '2024-03-13T22:44:40.545603-06:00'
model: gpt-4-1106-preview
summary: "Beregning av en dato i fremtiden eller fortiden inneb\xE6rer \xE5 legge\
  \ til eller trekke fra tid fra en n\xE5v\xE6rende dato."
title: Beregning av en dato i fremtiden eller fortiden
weight: 26
---

## Hvordan gjøre det:
```TypeScript
const today: Date = new Date();
const tenDaysLater: Date = new Date(today);
tenDaysLater.setDate(tenDaysLater.getDate() + 10); // Legger til 10 dager

console.log(today.toDateString()); // Eks.: "Wed Mar 15 2023"
console.log(tenDaysLater.toDateString()); // "Sat Mar 25 2023"

const thirtyDaysAgo: Date = new Date(today);
thirtyDaysAgo.setDate(thirtyDaysAgo.getDate() - 30); // Trekker fra 30 dager

console.log(thirtyDaysAgo.toDateString()); // "Sun Feb 13 2023"
```

## Dypdykk
Datohåndtering i programmering har historie tilbake til begynnelsen av datatiden. Tidligere var det ofte avhengig av plattforms-spesifikke funksjoner, men med moderne språk som JavaScript og TypeScript har vi innebygde klasser som `Date`. Implementasjonsdetaljer inkluderer å huske tidszoner og skuddår når man legger til og trekker fra dager. Alternativt kan biblioteker som Moment.js eller Date-fns benyttes for mer kompleks dato-håndtering.

## Se også
- MDN Web Docs: [Date reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)
- Moment.js: [Documentation](https://momentjs.com/docs/)
- Date-fns: [Documentation](https://date-fns.org/v2.28.0/docs/Getting-Started)
