---
aliases:
- /sv/javascript/concatenating-strings/
date: 2024-01-20 17:34:55.633490-07:00
description: "Sammanfogning av str\xE4ngar handlar om att klistra ihop textstycken\
  \ i JavaScript. Vi g\xF6r det f\xF6r att dynamiskt bygga text, som anv\xE4ndarnamn\
  \ eller\u2026"
lastmod: 2024-02-18 23:08:52.157053
model: gpt-4-1106-preview
summary: "Sammanfogning av str\xE4ngar handlar om att klistra ihop textstycken i JavaScript.\
  \ Vi g\xF6r det f\xF6r att dynamiskt bygga text, som anv\xE4ndarnamn eller\u2026"
title: "Sammanslagning av str\xE4ngar"
---

{{< edit_this_page >}}

## What & Why? (Vad & Varför?)
Sammanfogning av strängar handlar om att klistra ihop textstycken i JavaScript. Vi gör det för att dynamiskt bygga text, som användarnamn eller meddelanden.

## How to: (Hur man gör:)
```javascript
// Använd '+' för att konkatenera
let greeting = "Hej " + "världen!";
console.log(greeting); // Output: Hej världen!

// Template literals med backticks (``)
let planet = "världen";
let greet = `Hallå ${planet}!`;
console.log(greet); // Output: Hallå världen!
```

## Deep Dive (Djupdykning)
Från början använde JavaScript `'+'` för att konkatenera strängar. Det är enkelt, men kan bli rörigt med många variabler och långa strängar. Sedan ES6 (ECMAScript 2015), har "template literals" förbättrat situationen. Med `${}` kan du infoga variabler direkt i strängen och behålla läsbarheten. JavaScript hanterar konkatenering genom att skapa en ny sträng varje gång, vilket kan vara minneskrävande i stora applikationer. Alternativ inkluderar `Array.join()` eller `String.concat()`, men de används mer sällan.

## See Also (Se även)
- [MDN - Template Literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals)
- [MDN - String.concat()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/concat)
- [MDN - Array.join()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join)
