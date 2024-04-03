---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:07:46.768749-07:00
description: "Att kontrollera om en katalog finns i JavaScript \xE4r avg\xF6rande\
  \ f\xF6r filhanteringsuppgifter, vilket m\xF6jligg\xF6r f\xF6r skript att verifiera\
  \ katalogens n\xE4rvaro\u2026"
lastmod: '2024-03-13T22:44:38.307744-06:00'
model: gpt-4-0125-preview
summary: "Att kontrollera om en katalog finns i JavaScript \xE4r avg\xF6rande f\xF6\
  r filhanteringsuppgifter, vilket m\xF6jligg\xF6r f\xF6r skript att verifiera katalogens\
  \ n\xE4rvaro innan de l\xE4ser fr\xE5n eller skriver till den."
title: Kontrollera om en katalog existerar
weight: 20
---

## Hur:
I Node.js, eftersom JavaScript i sig inte har direkt tillgång till filsystemet, används vanligtvis `fs`-modulen för sådana operationer. Här är ett enkelt sätt att kontrollera om en katalog finns med `fs.existsSync()`:

```javascript
const fs = require('fs');

const directoryPath = './sample-directory';

// Kontrollera om katalogen finns
if (fs.existsSync(directoryPath)) {
  console.log('Katalogen finns.');
} else {
  console.log('Katalogen finns inte.');
}
```
**Exempelutmatning:**
```
Katalogen finns.
```
Eller, för ett icke-blockerande asynkront tillvägagångssätt, använd `fs.promises` med `async/await`:

```javascript
const fs = require('fs').promises;

async function checkDirectory(directoryPath) {
  try {
    await fs.access(directoryPath);
    console.log('Katalogen finns.');
  } catch (error) {
    console.log('Katalogen finns inte.');
  }
}

checkDirectory('./sample-directory');
```
**Exempelutmatning:**
```
Katalogen finns.
```

För projekt som gör stor användning av fil- och katalogoperationer, erbjuder `fs-extra`-paketet, en utvidgning av den inbyggda `fs`-modulen, bekväma ytterligare metoder. Så här kan du uppnå samma sak med `fs-extra`:

```javascript
const fs = require('fs-extra');

const directoryPath = './sample-directory';

// Kontrollera om katalogen finns
fs.pathExists(directoryPath)
  .then(exists => console.log(exists ? 'Katalogen finns.' : 'Katalogen finns inte.'))
  .catch(err => console.error(err));
```
**Exempelutmatning:**
```
Katalogen finns.
```

Denna metod möjliggör ren, lättläst kod som problemfritt integreras med moderna JavaScript-praxis.
