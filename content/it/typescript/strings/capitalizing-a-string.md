---
title:                "Capitalizzare una stringa"
aliases:
- /it/typescript/capitalizing-a-string/
date:                  2024-02-03T19:06:40.794443-07:00
model:                 gpt-4-0125-preview
simple_title:         "Capitalizzare una stringa"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/it/typescript/capitalizing-a-string.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Cosa e Perché?
Capitalizzare una stringa comporta modificare il primo carattere di una data stringa in maiuscolo se è in minuscolo, lasciando spesso inalterata la restante parte della stringa. Questa operazione è tipicamente utilizzata per assicurare che i nomi propri o gli inizi di frase aderiscano alle regole grammaticali nella elaborazione del testo, rendendo i risultati professionali e leggibili.

## Come fare:

TypeScript, essendo un superset di JavaScript, permette vari metodi per capitalizzare le stringhe, che vanno dagli approcci puramente JavaScript all'utilizzo di librerie di terze parti per casi d'uso più complessi o specifici.

**Approccio JavaScript Puro:**

```typescript
function capitalize(str: string): string {
  return str.charAt(0).toUpperCase() + str.slice(1);
}

// Esempio di Output:
console.log(capitalize('hello TypeScript!')); // 'Hello TypeScript!'
```

Questo metodo è diretto e si affida al metodo `charAt()` per accedere al primo carattere della stringa e `toUpperCase()` per convertirlo in maiuscolo. Il metodo `slice(1)` recupera poi il resto della stringa, lasciandolo inalterato.

**Utilizzando la Libreria Lodash:**

Per i progetti che già utilizzano la libreria [Lodash](https://lodash.com/), è possibile utilizzare la sua funzione `_.capitalize` per ottenere lo stesso risultato con meno codice boilerplate.

Prima, installa Lodash:

```bash
npm install lodash
```

Poi, usalo nel tuo file TypeScript:

```typescript
import * as _ from 'lodash';

// Esempio di Output:
console.log(_.capitalize('hello TypeScript!')); // 'Hello typescript!'
```

Nota: Il metodo `_.capitalize` di Lodash converte il resto della stringa in minuscolo, il che potrebbe non essere sempre desiderabile.

**Utilizzando un'espressione regolare:**

Un'espressione regolare può fornire un modo conciso per capitalizzare la prima lettera di una stringa, specialmente se è necessario capitalizzare la prima lettera di ogni parola in una stringa.

```typescript
function capitalizeWords(str: string): string {
  return str.replace(/\b\w/g, char => char.toUpperCase());
}

// Esempio di Output:
console.log(capitalizeWords('hello typescript world!')); // 'Hello Typescript World!'
```

Questo metodo usa la funzione `replace()` per cercare qualsiasi confine di parola seguito da un carattere alfanumerico (`\b\w`), capitalizzando ogni corrispondenza. È particolarmente utile per titoli o intestazioni.
