---
title:                "Substrings extraheren"
aliases:
- nl/typescript/extracting-substrings.md
date:                  2024-01-28T21:59:55.102019-07:00
model:                 gpt-4-0125-preview
simple_title:         "Substrings extraheren"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/nl/typescript/extracting-substrings.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?
Het extraheren van substrings betekent het uitkiezen van specifieke stukken van een string. Dit is handig voor taken zoals het parseren van gegevens, het valideren van invoer, of gewoon het opsplitsen van tekst in beter beheersbare brokken.

## Hoe doe je dat:
In TypeScript snijd en hak je strings met methoden zoals `substring()`, `slice()`, en de ES6 `includes()` voor het vinden van tekst binnen strings.

```TypeScript
let volledigeString: string = "Hallo, TypeScript enthousiastelingen!";

// Pak van karakter 7 tot 18
let substr: string = volledigeString.substring(7, 18);
console.log(substr); // Geeft uit: TypeScript

// Hetzelfde maar dan met slice()
let gesneden: string = volledigeString.slice(7, 18);
console.log(gesneden); // Geeft uit: TypeScript

// Controleer of een substring bestaat
let bestaat: boolean = volledigeString.includes("TypeScript");
console.log(bestaat); // Geeft uit: waar
```

## Dieper Duiken
Ooit was stringmanipulatie lastiger—denk aan de stringfuncties van C. Nu bieden JavaScript en TypeScript methoden die Unicode hanteren, rekening houden met karaktercodering, en rechtstreeks werken met stringobjecten. `substring()` en `slice()` lijken op elkaar maar met een twist: `slice()` kan negatieve indices aannemen, retroactief tellend vanaf het einde. `substring()` behandelt ze als nullen. In prestatiegevoelige situaties kan het kiezen van de een boven de ander belangrijk zijn, maar voor dagelijks gebruik is het veel van hetzelfde.

```TypeScript
// Negatieve index gebruiken met slice
let eindeGesneden: string = volledigeString.slice(-25, -7);
console.log(eindeGesneden); // Geeft uit: Hallo, Type
```

Wat betreft `includes()`, het is een zegen voor leesbaarheid ten opzichte van de klassieke `indexOf()`, waardoor je intenties in één oogopslag duidelijk zijn. Niet meer `if (string.indexOf('some text') !== -1)`; gewoon een rechttoe rechtaan `if (string.includes('some text'))`.

## Zie Ook
- Het TypeScript handboek over strings, voor meer over hoe je `'string'` types gebruikt: [TypeScript String](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html#string)
- MDN Web Docs over String-methoden in JavaScript, toepasbaar voor TypeScript: [MDN String](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String)
- Voor meer begrip van Unicode en JavaScript (dus ook TypeScript), bekijk [Understanding JavaScript's internal character encoding: UCS-2? UTF-16?](http://mathiasbynens.be/notes/javascript-encoding)
