---
title:                "Korzystanie z wyrażeń regularnych"
aliases:
- pl/javascript/using-regular-expressions.md
date:                  2024-02-03T19:17:27.387209-07:00
model:                 gpt-4-0125-preview
simple_title:         "Korzystanie z wyrażeń regularnych"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/javascript/using-regular-expressions.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Co i dlaczego?

Wyrażenia regularne (regex) w JavaScript są wzorcami używanymi do dopasowywania kombinacji znaków w ciągach tekstowych. Programiści używają ich do wyszukiwania, ekstrakcji i manipulowania tekstem, co pozwala na potężne operacje przetwarzania ciągów znaków za pomocą zwięzłego kodu.

## Jak to zrobić:

### Podstawowe Dopasowanie

Na początek możesz stworzyć prosty wzór regex i użyć go do znalezienia dopasowań w ciągu tekstowym. Tutaj znajdziemy słowo "kod":

```javascript
const str = "Uwielbiam programować w JavaScript.";
const pattern = /kod/;
const result = pattern.test(str);
console.log(result); // true
```

### Użycie `String.prototype.match()`

Aby otrzymać tablicę dopasowań:

```javascript
const matches = str.match(/kod/);
console.log(matches[0]); // "kod"
console.log(matches.index); // 10
```

### Globalne Wyszukiwanie

Aby znaleźć wszystkie dopasowania, użyj flagi `g`:

```javascript
const globalMatches = str.match(/o/g);
console.log(globalMatches); // ["o", "o", "o"]
```

### Dopasowanie Niezależne od Wielkości Liter

Flaga `i` ignoruje wielkość liter:

```javascript
const caseInsensitiveMatch = "JavaScript jest fajny".match(/javascript/i);
console.log(caseInsensitiveMatch[0]); // "JavaScript"
```

### Zastępowanie Tekstu

Użyj `String.prototype.replace()`, aby zastąpić części ciągu tekstowego:

```javascript
const newStr = "JavaScript jest fajny".replace(/fajny/, "niesamowity");
console.log(newStr); // "JavaScript jest niesamowity"
```

### Użycie Grup

Grupy mogą przechwytywać części wzorca:

```javascript
const groupedPattern = /(\w+) jest (\w+)/;
const replaceWithGroups = "JavaScript jest fajny".replace(groupedPattern, "$2 jest $1");
console.log(replaceWithGroups); // "fajny jest JavaScript"
```

### Biblioteki Stron Trzecich

Chociaż wbudowane możliwości regex JavaScript są potężne, niektóre zadania mogą być uproszczone za pomocą bibliotek takich jak `XRegExp`. Oferuje dodatkową składnię i flagi, dzięki czemu skomplikowane wzorce są bardziej czytelne:

```javascript
// Przykład użycia biblioteki XRegExp
const XRegExp = require('xregexp');
const str = "Koty są fantastyczne.";
const unicodeWordMatch = XRegExp.match(str, XRegExp('\\p{L}+'), 'all');
console.log(unicodeWordMatch); // ["Koty", "są", "fantastyczne"]
```

Ten fragment kodu demonstruje użycie `XRegExp` do dopasowania wszystkich słów Unicode w ciągu tekstowym, prezentując zdolność biblioteki do obsługi rozszerzonych zestawów znaków, wykraczających poza wbudowane możliwości JavaScript.
