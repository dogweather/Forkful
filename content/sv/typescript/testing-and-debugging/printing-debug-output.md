---
date: 2024-01-20 17:53:25.853827-07:00
description: "Utskrift f\xF6r fels\xF6kning (debugging) \xE4r n\xE4r du skriver ut\
  \ data till konsolen f\xF6r att se vad som h\xE4nder i din kod. Programmerare g\xF6\
  r det f\xF6r att snabbt\u2026"
lastmod: '2024-03-13T22:44:37.658676-06:00'
model: gpt-4-1106-preview
summary: "Utskrift f\xF6r fels\xF6kning (debugging) \xE4r n\xE4r du skriver ut data\
  \ till konsolen f\xF6r att se vad som h\xE4nder i din kod."
title: "Skriva ut fels\xF6kningsdata"
weight: 33
---

## How to:
```TypeScript
function addNumbers(a: number, b: number): number {
  console.log(`Adding ${a} + ${b}`);
  return a + b;
}

const result = addNumbers(5, 7);
console.log(`Result: ${result}`);
```
Sample output:
```
Adding 5 + 7
Result: 12
```

## Deep Dive
Utskrift för debuggning är lika gammalt som programmering självt. Förr i tiden kunde det betyda att skriva ut på papper. Idag använder vi `console.log()` i JavaScript och TypeScript. Alternativ till `console.log()` inkluderar mer avancerade debuggare som låter oss stega igenom kod, titta på variabelvärden och tillstånd utan att "smutsa ned" koden med utskrifter. TypeScript är ett superset av JavaScript som kompileras ner till JavaScript och ger därmed samma `console` metoder för debuggning.

## See Also
- [TypeScript Handbook](https://www.typescriptlang.org/docs/handbook/intro.html)
- [Using console in MDN web docs](https://developer.mozilla.org/en-US/docs/Web/API/console)
- [Node.js debugging guide](https://nodejs.org/en/docs/guides/debugging-getting-started/)
- [Visual Studio Code Debugger](https://code.visualstudio.com/docs/editor/debugging)
