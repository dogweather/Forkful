---
date: 2024-01-20 17:46:52.862533-07:00
description: "Wyci\u0105ganie pod\u0142a\u0144cuch\xF3w to proces pozyskiwania kr\xF3\
  tszych ci\u0105g\xF3w znak\xF3w z wi\u0119kszego tekstu. Programi\u015Bci u\u017C\
  ywaj\u0105 tej techniki, by manipulowa\u0107 danymi\u2026"
lastmod: '2024-03-13T22:44:35.127341-06:00'
model: gpt-4-1106-preview
summary: "Wyci\u0105ganie pod\u0142a\u0144cuch\xF3w to proces pozyskiwania kr\xF3\
  tszych ci\u0105g\xF3w znak\xF3w z wi\u0119kszego tekstu."
title: "Wycinanie pod\u0142a\u0144cuch\xF3w"
weight: 6
---

## How to:
TypeScript daje kilka metod do łatwego wydobywania podłańcuchów. Przyjrzyjmy się przykładom:

```typescript
let text: string = "Witajcie w wesołym świecie TypeScript!";

// Użycie metody .substring(startIndex, endIndex)
let substring1: string = text.substring(8, 15);
console.log(substring1); // "w wesoł"

// Użycie metody .slice(startIndex, endIndex)
let substring2: string = text.slice(8, -14);
console.log(substring2); // "w wesoł"

// Użycie metody .substr(startIndex, length)
let substring3: string = text.substr(8, 7);
console.log(substring3); // "w wesoł"
```

Wynik w konsoli:
```
"w wesoł"
"w wesoł"
"w wesoł"
```
Jak widać, efekty są podobne, ale metody się różnią. Wybór należy do programisty.

## Deep Dive:
Branie podściągów informacji z tekstu nie jest niczym nowym. Na przykład w JavaScript używa się `substring`, `slice` i `substr` od lat. W TypeScript, który jest nadzbiorem JavaScript, funkcje te również działają.

Alternatywą jest użycie wyrażeń regularnych z metodą `.match()`, co daje większą kontrolę i elastyczność. Jednakże, wyrażenia regularne mogą być overkill'em dla prostych zadań i są trudniejsze w debugowaniu.

`substring` różni się od `slice` tym, że nie akceptuje ujemnych indeksów i ma mniej elastyczną obsługę przypadków skrajnych, takich jak przekazanie większego `startIndex` przed `endIndex`. `substr` jest już uznawana za przestarzałą i nie jest zalecana do nowych projektów.

## See Also:
- MDN Web Docs na temat `String.prototype.substring()`: https://developer.mozilla.org/pl/docs/Web/JavaScript/Reference/Global_Objects/String/substring
- MDN Web Docs na temat `String.prototype.slice()`: https://developer.mozilla.org/pl/docs/Web/JavaScript/Reference/Global_Objects/String/slice
- MDN Web Docs na temat `String.prototype.substr()`: https://developer.mozilla.org/pl/docs/Web/JavaScript/Reference/Global_Objects/String/substr
- Artykuł o wyrażeniach regularnych w TypeScript: [Link do artykułu]
