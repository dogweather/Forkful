---
aliases:
- /pl/javascript/checking-if-a-directory-exists/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:07:48.880318-07:00
description: "Sprawdzanie, czy katalog istnieje w JavaScript, jest kluczowe dla zada\u0144\
  \ manipulacji plikami. Pozwala skryptom zweryfikowa\u0107 obecno\u015B\u0107 katalogu\
  \ przed\u2026"
lastmod: 2024-02-18 23:08:50.007803
model: gpt-4-0125-preview
summary: "Sprawdzanie, czy katalog istnieje w JavaScript, jest kluczowe dla zada\u0144\
  \ manipulacji plikami. Pozwala skryptom zweryfikowa\u0107 obecno\u015B\u0107 katalogu\
  \ przed\u2026"
title: Sprawdzanie, czy katalog istnieje
---

{{< edit_this_page >}}

## Co i dlaczego?
Sprawdzanie, czy katalog istnieje w JavaScript, jest kluczowe dla zadań manipulacji plikami. Pozwala skryptom zweryfikować obecność katalogu przed odczytem z niego lub zapisem do niego. Operacja ta zapobiega błędom i zapewnia płynniejsze wykonanie programu, szczególnie w aplikacjach, które dynamicznie obsługują pliki lub katalogi na podstawie wprowadzonych danych użytkownika lub zewnętrznych źródeł danych.

## Jak to zrobić:
W Node.js, ponieważ JavaScript sam w sobie nie ma bezpośredniego dostępu do systemu plików, zazwyczaj używany jest moduł `fs` do tego typu operacji. Oto prosty sposób, aby sprawdzić, czy katalog istnieje, używając `fs.existsSync()`:

```javascript
const fs = require('fs');

const directoryPath = './sample-directory';

// Sprawdź, czy katalog istnieje
if (fs.existsSync(directoryPath)) {
  console.log('Katalog istnieje.');
} else {
  console.log('Katalog nie istnieje.');
}

```
**Przykładowy wynik:**
```
Katalog istnieje.
```
Lub, dla podejścia nieblokującego i asynchronicznego, użyj `fs.promises` z `async/await`:

```javascript
const fs = require('fs').promises;

async function checkDirectory(directoryPath) {
  try {
    await fs.access(directoryPath);
    console.log('Katalog istnieje.');
  } catch (error) {
    console.log('Katalog nie istnieje.');
  }
}

checkDirectory('./sample-directory');
```
**Przykładowy wynik:**
```
Katalog istnieje.
```

Dla projektów, które intensywnie korzystają z operacji na plikach i katalogach, pakiet `fs-extra`, rozszerzenie natywnego modułu `fs`, oferuje wygodne dodatkowe metody. Oto jak możesz osiągnąć to samo z `fs-extra`:

```javascript
const fs = require('fs-extra');

const directoryPath = './sample-directory';

// Sprawdź, czy katalog istnieje
fs.pathExists(directoryPath)
  .then(exists => console.log(exists ? 'Katalog istnieje.' : 'Katalog nie istnieje.'))
  .catch(err => console.error(err));
```
**Przykładowy wynik:**
```
Katalog istnieje.
```

To podejście umożliwia czysty i czytelny kod, który bezproblemowo integruje się z nowoczesnymi praktykami JavaScript.
