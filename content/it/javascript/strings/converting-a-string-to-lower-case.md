---
title:                "Conversione di una stringa in minuscolo"
aliases:
- /it/javascript/converting-a-string-to-lower-case/
date:                  2024-01-20T17:38:29.760361-07:00
model:                 gpt-4-1106-preview
simple_title:         "Conversione di una stringa in minuscolo"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/it/javascript/converting-a-string-to-lower-case.md"
---

{{< edit_this_page >}}

## What & Why?
Convertire una stringa in minuscolo significa trasformare tutti i caratteri alfabetici in minuscole. I programmatori lo fanno per uniformare i dati, specialmente quando confrontano stringhe o li rendono case-insensitive.

## How to:
Utilizza il metodo `.toLowerCase()` di JavaScript. Ecco un esempio:

```Javascript
let frase = "Ciao Mondo!";
let fraseMinuscola = frase.toLowerCase();

console.log(fraseMinuscola); // "ciao mondo!"
```

Output:

```
ciao mondo!
```

## Deep Dive
Nato con i primi linguaggi di programmazione, convertire testo in minuscolo è essenziale per l'uniformità dei dati. Alternative a `.toLowerCase()` includono uso di espressioni regolari o loop per processare ogni carattere. Importante notare come `.toLocaleLowerCase()` gestisca le stringhe tenendo conto delle località, utile per lingue con caratteri specifici.

Internamente, `.toLowerCase()` si confronta con una mappa di caratteri Unicode convertendoli individualmente. Il metodo è direttamente collegato al prototipo `String`, disponibile per tutte le stringhe in JavaScript.

## See Also
- [MDN Web Docs - String.prototype.toLowerCase()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toLowerCase)
- [MDN Web Docs - String.prototype.toLocaleLowerCase()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toLocaleLowerCase)
