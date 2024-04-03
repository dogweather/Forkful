---
date: 2024-01-20 17:51:40.946194-07:00
description: "Stringinterpolering \xE4r att smidigt b\xE4dda in variabler eller uttryck\
  \ i str\xE4ngar. Vi g\xF6r det f\xF6r att bygga dynamiska texter enklare och f\xF6\
  r att koden ska\u2026"
lastmod: '2024-03-13T22:44:37.642489-06:00'
model: gpt-4-1106-preview
summary: "Stringinterpolering \xE4r att smidigt b\xE4dda in variabler eller uttryck\
  \ i str\xE4ngar."
title: "Interpolera en str\xE4ng"
weight: 8
---

## Hur gör man:
```TypeScript
let användare = 'Anna';
let hälsning = `Hej ${användare}, välkommen tillbaka!`;
console.log(hälsning);  // Output: Hej Anna, välkommen tillbaka!

let pris = 45.99;
let produkt = 'bok';
console.log(`Totalt pris för ${produkt}: ${pris} kr`); // Output: Totalt pris för bok: 45.99 kr
```

## Djupdykning
Före ES6 (ECMAScript 2015) användes konkatenering, som var klumpigt: `'Hej ' + användare + ', välkommen tillbaka!'`. Med ES6 introducerades `template literals`, tydliga med backticks (\`) som tillåter interpolering direkt i strängarna. Alternativ som `sprintf()` i andra språk finns, men i TypeScript är template literals standard. Implementationen under huven bygger på att körtiden ersätter platsen inom `${}` med värdet av variabeln eller resultatet av uttrycket.

## Se även
- TypeScript Handbook om Template Strings: [TypeScript Handbook Template Strings](https://www.typescriptlang.org/docs/handbook/2/template-literal-types.html)
- MDN Web Docs om Template Literals: [MDN Template Literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals)
- Ett djupare dyk in i ES6 Template Literals: [Exploring ES6: Template Literals](http://exploringjs.com/es6/ch_template-literals.html)
