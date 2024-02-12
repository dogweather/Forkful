---
title:                "Scrivere sull'errore standard"
date:                  2024-02-03T19:34:38.838300-07:00
model:                 gpt-4-0125-preview
simple_title:         "Scrivere sull'errore standard"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/it/typescript/writing-to-standard-error.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Cosa e perché?
In TypeScript, scrivere sull'errore standard (stderr) è un processo che invia messaggi di errore o log direttamente al flusso di uscita di errore dell'ambiente (ad esempio, la console in node.js o un browser web). Questo è fondamentale per diagnosticare problemi senza interferire con l'output standard (stdout) normalmente utilizzato per i dati del programma, garantendo che la gestione degli errori e la registrazione siano gestite in modo efficiente e coeso.

## Come fare:
TypeScript, essendo un sovrainsieme di JavaScript, si affida all'ambiente di runtime JS sottostante (come Node.js) per scrivere su stderr. Ecco come puoi farlo direttamente:

```typescript
console.error("Questo è un messaggio di errore.");
```

Esempio di output su stderr:
```
Questo è un messaggio di errore.
```

In un ambiente Node.js, puoi anche utilizzare il metodo `process.stderr.write()` per scrivere a un livello più basso:

```typescript
process.stderr.write("Messaggio di errore di basso livello.\n");
```

Esempio di output su stderr:
```
Messaggio di errore di basso livello.
```

Per una registrazione degli errori più strutturata, potresti usare librerie di terze parti popolari come `winston` o `pino`. Ecco come registrare gli errori utilizzando `winston`:

Prima, installa `winston`:

```bash
npm install winston
```

Quindi usalo nel tuo file TypeScript:

```typescript
import * as winston from 'winston';

const logger = winston.createLogger({
  levels: winston.config.syslog.levels,
  transports: [
    new winston.transports.Console(),
    new winston.transports.File({ filename: 'error.log', level: 'error' })
  ],
});

logger.error('Errore registrato usando winston.');
```

Questo scriverà l'errore sia sulla console che su un file denominato `error.log`. Ricorda, quando scrivi su file, è importante gestire i permessi dei file e il loro rollover per prevenire problemi relativi all'uso dello spazio su disco.
