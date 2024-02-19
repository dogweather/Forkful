---
aliases:
- /pl/typescript/writing-to-standard-error/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:34:47.558706-07:00
description: "W TypeScript piszemy do standardowego b\u0142\u0119du (stderr) w celu\
  \ wysy\u0142ania komunikat\xF3w b\u0142\u0119d\xF3w lub rejestracji bezpo\u015B\
  rednio do strumienia wyj\u015Bciowego b\u0142\u0119d\xF3w\u2026"
lastmod: 2024-02-18 23:08:49.364046
model: gpt-4-0125-preview
summary: "W TypeScript piszemy do standardowego b\u0142\u0119du (stderr) w celu wysy\u0142\
  ania komunikat\xF3w b\u0142\u0119d\xF3w lub rejestracji bezpo\u015Brednio do strumienia\
  \ wyj\u015Bciowego b\u0142\u0119d\xF3w\u2026"
title: "Pisanie do standardowego b\u0142\u0119du"
---

{{< edit_this_page >}}

## Co i dlaczego?
W TypeScript piszemy do standardowego błędu (stderr) w celu wysyłania komunikatów błędów lub rejestracji bezpośrednio do strumienia wyjściowego błędów środowiska (np. konsoli w node.js lub przeglądarce internetowej). Jest to niezbędne do diagnozowania problemów bez ingerencji w standardowe wyjście (stdout), które jest zwykle używane dla danych programu, zapewniając, że obsługa błędów oraz rejestrowanie są zarządzane w sposób efektywny i spójny.

## Jak to zrobić:
TypeScript, będąc nadzbiorem JavaScript, opiera się na bazowym środowisku wykonawczym JS (jak Node.js) do pisania na stderr. Oto jak można to zrobić bezpośrednio:

```typescript
console.error("To jest komunikat błędu.");
```

Przykładowe wyjście na stderr:
```
To jest komunikat błędu.
```

W środowisku Node.js można również użyć metody `process.stderr.write()` do pisania na niższym poziomie:

```typescript
process.stderr.write("Komunikat błędu niskiego poziomu.\n");
```

Przykładowe wyjście na stderr:
```
Komunikat błędu niskiego poziomu.
```

Dla bardziej strukturalnego rejestrowania błędów, można używać popularnych bibliotek stron trzecich, takich jak `winston` lub `pino`. Oto jak rejestrować błędy używając `winston`:

Najpierw zainstaluj `winston`:

```bash
npm install winston
```

Następnie użyj go w swoim pliku TypeScript:

```typescript
import * as winston from 'winston';

const logger = winston.createLogger({
  levels: winston.config.syslog.levels,
  transports: [
    new winston.transports.Console(),
    new winston.transports.File({ filename: 'error.log', level: 'error' })
  ],
});

logger.error('Błąd zarejestrowany za pomocą winston.');
```

To zapisze błąd zarówno do konsoli, jak i do pliku o nazwie `error.log`. Pamiętaj, że przy zapisywaniu do plików ważne jest zarządzanie uprawnieniami do plików i ich rotacją, aby zapobiec problemom związanym z użyciem miejsca na dysku.
