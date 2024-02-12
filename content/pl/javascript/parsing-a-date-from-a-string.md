---
title:                "Analiza składniowa daty z łańcucha znaków"
aliases:
- pl/javascript/parsing-a-date-from-a-string.md
date:                  2024-02-03T19:14:30.881461-07:00
model:                 gpt-4-0125-preview
simple_title:         "Analiza składniowa daty z łańcucha znaków"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/javascript/parsing-a-date-from-a-string.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Co i dlaczego?
Parsowanie daty z ciągu znaków pozwala programistom konwertować tekstowe reprezentacje dat na obiekty `Date` w JavaScript, ułatwiając operacje manipulowania datą, porównywania i formatowania. Proces ten jest niezbędny do obsługi danych wprowadzanych przez użytkownika, przetwarzania danych z baz danych lub pracy z API, które komunikują daty w formatach tekstowych.

## Jak to zrobić:
JavaScript natywnie oferuje metodę `Date.parse()` oraz konstruktor `Date` do parsowania ciągów dat. Jednak te podejścia mają ograniczenia i niespójności w różnych przeglądarkach, szczególnie przy niestandardowych formatach dat. Aby rozwiązać te problemy, popularne ze względu na swoją niezawodność i łatwość użycia są biblioteki stron trzecich, takie jak `Moment.js` i `date-fns`.

### Używając natywnego JavaScript:
```javascript
const dateString = "2023-04-30T14:55:00";
const dateObj = new Date(dateString);

console.log(dateObj);  // Wynik: Sun Apr 30 2023 14:55:00 GMT+0000 (Czas Uniwersalny Koordynowany)
```

### Używając Moment.js:
Najpierw zainstaluj Moment.js za pomocą npm lub dołącz go do swojego projektu. Następnie:
```javascript
const moment = require('moment');

const dateString = "2023-04-30T14:55:00";
const dateObj = moment(dateString);

console.log(dateObj.toString());  // Wynik: Sun Apr 30 2023 14:55:00 GMT+0000
```

### Używając date-fns:
Po dodaniu `date-fns` do swojego projektu, zparsuj ciąg daty w następujący sposób:
```javascript
const { parseISO } = require('date-fns');

const dateString = "2023-04-30T14:55:00";
const dateObj = parseISO(dateString);

console.log(dateObj);  // Wynik: 2023-04-30T14:55:00.000Z
```

Zarówno `Moment.js`, jak i `date-fns` oferują bardziej wszechstronne możliwości parsowania, w tym obsługę różnorodnych formatów i ustawień regionalnych, co sprawia, że są one preferowane w skomplikowanych aplikacjach.
