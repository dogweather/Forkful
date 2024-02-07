---
title:                "Sprawdzanie, czy katalog istnieje"
date:                  2024-02-03T19:08:46.693454-07:00
model:                 gpt-4-0125-preview
simple_title:         "Sprawdzanie, czy katalog istnieje"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/typescript/checking-if-a-directory-exists.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Co i dlaczego?
Sprawdzanie, czy katalog istnieje w TypeScript, jest kluczowe dla zadań związanych z zarządzaniem plikami, takich jak odczytywanie z plików lub zapisywanie do nich danych, zapewniając, że operacje są wykonywane tylko na istniejących katalogach. Ta operacja jest istotna, aby unikać błędów wynikających z prób dostępu lub manipulacji nieistniejącymi katalogami.

## Jak to zrobić:

TypeScript, uruchomiony w środowisku Node.js, umożliwia sprawdzenie, czy katalog istnieje, za pomocą modułu `fs`, który dostarcza funkcję `existsSync()` lub asynchroniczną funkcję `access()` połączoną z `constants.F_OK`.

### Używając `fs.existsSync()`:

```typescript
import { existsSync } from 'fs';

const directoryPath = './sciezka/do/katalogu';

if (existsSync(directoryPath)) {
  console.log('Katalog istnieje.');
} else {
  console.log('Katalog nie istnieje.');
}
```

### Używając `fs.access()` z `fs.constants.F_OK`:

```typescript
import { access, constants } from 'fs';

const directoryPath = './sciezka/do/katalogu';

access(directoryPath, constants.F_OK, (err) => {
  if (err) {
    console.log('Katalog nie istnieje.');
    return;
  }
  console.log('Katalog istnieje.');
});
```

**Przykładowy wynik** dla obu metod, zakładając, że katalog istnieje:
```
Katalog istnieje.
```

A jeśli nie istnieje:
```
Katalog nie istnieje.
```

### Używając biblioteki innej firmy - `fs-extra`:

`fs-extra` to popularna biblioteka innej firmy, która ulepsza wbudowany moduł `fs` i dostarcza bardziej wygodne funkcje.

```typescript
import { pathExists } from 'fs-extra';

const directoryPath = './sciezka/do/katalogu';

pathExists(directoryPath).then(exists => {
  console.log(`Katalog istnieje: ${exists}`);
});
```

**Przykładowy wynik** gdy katalog istnieje:
```
Katalog istnieje: true
```

A jeśli nie:
```
Katalog istnieje: false
```
