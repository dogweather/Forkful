---
title:                "Controleren of een directory bestaat"
aliases:
- nl/typescript/checking-if-a-directory-exists.md
date:                  2024-01-28T21:56:02.549931-07:00
model:                 gpt-4-0125-preview
simple_title:         "Controleren of een directory bestaat"

tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/nl/typescript/checking-if-a-directory-exists.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?
Controleren of een directory bestaat gaat over zorgen dat een map daadwerkelijk aanwezig is voordat je eruit leest of ernaar schrijft. Programmeurs doen dit om fouten te voorkomen, zoals proberen een bestand op te slaan op een niet-bestaande plaats - dat is absoluut not done.

## Hoe te:
In TypeScript gebruik je meestal Node.js's `fs` module om te controleren op een directory. Hier is de snelle manier om het te doen:

```typescript
import { existsSync } from 'fs';

// Controleren of een directory bestaat
const directoryPath = './path/to/directory';

if (existsSync(directoryPath)) {
  console.log(`Yep, hij is er!`);
} else {
  console.log(`Nee, bestaat niet.`);
}
```

Output is afhankelijk van het bestaan van de directory:
```
Yep, hij is er!
// of
Nee, bestaat niet.
```

## Diepere Duik
Historisch gezien gebruikten mensen de asynchrone `fs.exists`, maar deze werd afgekeurd omdat het een vervelende gewoonte had om programmeerfouten te veroorzaken, zoals check-then-act racecondities. `existsSync` is eenvoudiger en schakelt de callback rommel uit.

Wat alternatieven betreft, de `fs.statSync` of `fs.accessSync` methoden kunnen ook het werk doen, maar vereisen wat meer code:

```typescript
import { statSync } from 'fs';

try {
  const stats = statSync(directoryPath);
  if (stats.isDirectory()) {
    console.log('Hij bestaat inderdaad.');
  }
} catch (error) {
  if (error.code === 'ENOENT') {
    console.log('Nee, nergens te vinden.');
  }
}
```

Zowel `statSync` als `accessSync` geven fouten als het pad niet bestaat, dus je moet dat afhandelen.

Wanneer je TypeScript gebruikt, herinner je dan dat deze methoden van Node.js komen, niet van TypeScript zelf. En de rol van TypeScript? Voornamelijk, het biedt de types en zorgt ervoor dat je de methoden correct gebruikt.

## Zie Ook
- Node.js Bestandssysteem Documentatie: https://nodejs.org/api/fs.html
- TypeScript Handboek: https://www.typescriptlang.org/docs/handbook/intro.html
- Foutafhandeling in Node.js: https://nodejs.org/en/knowledge/errors/what-are-the-error-conventions/
