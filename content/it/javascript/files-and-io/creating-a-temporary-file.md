---
date: 2024-01-20 17:40:28.607857-07:00
description: "Creare un file temporaneo significa realizzare un documento destinato\
  \ a una breve esistenza. I programmatori ne fanno uso per diversi motivi: per\u2026"
lastmod: '2024-03-13T22:44:43.832977-06:00'
model: gpt-4-1106-preview
summary: Creare un file temporaneo significa realizzare un documento destinato a una
  breve esistenza.
title: Creazione di un file temporaneo
weight: 21
---

## How to:
JavaScript non gestisce direttamente la creazione di file temporanei, ma possiamo usare il pacchetto `tmp` di Node.js:

```Javascript
const tmp = require('tmp');

// Crea file temporaneo in modo sincrono
const tmpFile = tmp.fileSync();
console.log(`File temporaneo creato in: ${tmpFile.name}`);

// Quando hai finito, chiudi e cancella il file
tmpFile.removeCallback();
```

Installazione di `tmp` via NPM:
```shell
npm install tmp
```

## Deep Dive
Historically, i file temporanei in Unix-like systems are often created in `/tmp` directory. 

In JavaScript, la creazione di file temporanei è affidata a librerie esterne Node.js perché JS è originariamente un linguaggio lato client, senza accesso al filesystem. Il pacchetto `tmp` è una scelta popolare per la sua API semplice, sia sincrona che asincrona.

Ci sono alternative a `tmp`, come `temp` e `tempfile`, ma `tmp` è ampiamente usato e mantenuto. Dettagli d'implementazione interessanti:

- `tmp` può generare file e directory temporanei.
- I file rimangono finché l'applicazione è in esecuzione o fino a quando non vengono eliminati esplicitamente.
- `tmp` offre la pulizia automatica, ma è buona norma rimuoverli manualmente con `removeCallback()` per evitare sprechi di spazio disco.

## See Also
- Node.js `fs` module: [Node.js File System](https://nodejs.org/api/fs.html)
- npm package `tmp`: [tmp on npm](https://www.npmjs.com/package/tmp)
- Alternative npm package `tempfile`: [tempfile on npm](https://www.npmjs.com/package/tempfile)
