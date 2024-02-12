---
title:                "Konwersja daty na łańcuch znaków"
aliases:
- pl/javascript/converting-a-date-into-a-string.md
date:                  2024-01-20T17:37:08.682754-07:00
model:                 gpt-4-1106-preview
simple_title:         "Konwersja daty na łańcuch znaków"

tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/javascript/converting-a-date-into-a-string.md"
---

{{< edit_this_page >}}

## What & Why?
Czasami potrzebujemy reprezentować datę tekstowo - do wyświetlenia, logowania czy zapisywania. Robimy to, przekształcając obiekty daty (`Date`) w JavaScript na ciągi znaków (stringi), aby były czytelne dla ludzi i kompatybilne z innymi systemami.

## How to:
Konwersja daty na string w JS jest prosta. Spójrzmy:

```javascript
const aktualnaData = new Date();

// Konwersja do stringa przy użyciu metody toString()
console.log(aktualnaData.toString()); // "Wed Apr 05 2023 12:34:56 GMT+0200 (Central European Summer Time)"

// Formatowanie do UTC używając metody toUTCString()
console.log(aktualnaData.toUTCString()); // "Wed, 05 Apr 2023 10:34:56 GMT"

// Formatowanie zgodne z ISO przy użyciu toISOString()
console.log(aktualnaData.toISOString()); // "2023-04-05T10:34:56.000Z"
```

Gdy potrzebujemy tylko daty bez godziny i strefy czasowej:

```javascript
console.log(aktualnaData.toDateString()); // "Wed Apr 05 2023"
```

Lub gdy chcesz samemu kontrolować format:

```javascript
console.log(aktualnaData.toLocaleDateString('pl-PL')); // "05.04.2023"
```

## Deep Dive:
Historia metod konwersji daty w JS sięga początków języka. „toString” i „toUTCString” były od zawsze, a „toISOString” dodano później, ustandaryzowano w ES5.

Alternativy to biblioteki zewnętrzne jak Moment.js czy nowoczesna biblioteka date-fns, które oferują bardziej zaawansowane formatowanie.

Jeśli chodzi o implementację, metody obiektu Date korzystają z ustawień przeglądarki - strefy czasowej czy lokalizacji, co wpływa na wynik metody `toLocaleDateString`. Z kolei `toISOString` zawsze zwraca datę w UTC, więc jest niezawodna dla formatowania międzynarodowego.

## See Also:
- MDN Web Docs dla metody [`Date.prototype.toString()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/toString)
- MDN Web Docs dla [`Date.prototype.toISOString()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/toISOString)
- Porównanie bibliotek dat [`Moment.js vs date-fns`](https://stackoverflow.com/questions/35272893/what-is-the-difference-between-moment-js-and-date-fns)
