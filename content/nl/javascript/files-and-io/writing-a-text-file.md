---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:13:03.760161-07:00
description: "Een tekstbestand schrijven in JavaScript betekent meestal het cre\xEB\
  ren en opslaan van gegevens in een bestand in een voor mensen leesbaar formaat.\u2026"
lastmod: '2024-03-13T22:44:51.221170-06:00'
model: gpt-4-0125-preview
summary: "Een tekstbestand schrijven in JavaScript betekent meestal het cre\xEBren\
  \ en opslaan van gegevens in een bestand in een voor mensen leesbaar formaat."
title: Een tekstbestand schrijven
weight: 24
---

## Hoe te:
JavaScript in een browser heeft om veiligheidsredenen geen directe toegang tot het bestandssysteem. Maar je kunt een tekstbestand maken en de gebruiker vragen het op te slaan:

```javascript
function downloadTextFile(text, filename) {
  const blob = new Blob([text], { type: 'text/plain' });
  const a = document.createElement('a');
  a.download = filename;
  a.href = window.URL.createObjectURL(blob);
  a.dataset.downloadurl = ['text/plain', a.download, a.href].join(':');
  a.style.display = "none";
  document.body.appendChild(a);  // Voeg anker toe aan body.
  a.click();
  
  document.body.removeChild(a);  // Opruimen anker na gebruik.
  window.URL.revokeObjectURL(a.href);  // Blob URL vrijgeven.
}

// Gebruik:
downloadTextFile('Hallo, wereld!', 'voorbeeld.txt');
```

Node.js biedt een eenvoudigere manier om bestanden te schrijven via de `fs` module:

```javascript
const fs = require('fs');

fs.writeFile('voorbeeld.txt', 'Hallo, wereld!', (err) => {
  if (err) throw err;
  console.log('Bestand is opgeslagen!');
});
```

## Diepgaande Duik
Historisch gezien was JavaScript beperkt tot de browser zonder toegang tot het bestandssysteem. Node.js veranderde dat spel door server-side mogelijkheden bloot te leggen.

Alternatieven voor `fs.writeFile` omvatten `fs.writeFileSync` voor synchrone operaties en `fs.promises.writeFile` voor op promises gebaseerde asynchrone controle.

Node's `fs` methoden behandelen buffers en streams—gereedschappen die grote bestandsverwerking en netwerkcommunicatie aanpakken.

## Zie Ook
- Node.js Bestandssysteem Docs: [https://nodejs.org/api/fs.html](https://nodejs.org/api/fs.html)
- MDN - Blob: [https://developer.mozilla.org/en-US/docs/Web/API/Blob](https://developer.mozilla.org/en-US/docs/Web/API/Blob)
- MDN - JavaScript Gids: [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide)
