---
title:                "Überprüfung, ob ein Verzeichnis existiert"
aliases:
- /de/javascript/checking-if-a-directory-exists/
date:                  2024-02-03T19:07:44.953177-07:00
model:                 gpt-4-0125-preview
simple_title:         "Überprüfung, ob ein Verzeichnis existiert"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/javascript/checking-if-a-directory-exists.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Was & Warum?
Es ist wesentlich in JavaScript zu überprüfen, ob ein Verzeichnis existiert, um Aufgaben der Dateimanipulation durchzuführen. Dadurch können Skripte die Anwesenheit eines Verzeichnisses bestätigen, bevor sie daraus lesen oder darauf schreiben. Diese Operation verhindert Fehler und gewährleistet einen reibungsloseren Programmablauf, insbesondere bei Anwendungen, die Dateien oder Verzeichnisse dynamisch basierend auf Benutzereingaben oder externen Datenquellen handhaben.

## Wie geht das:
In Node.js, da JavaScript selbst keinen direkten Zugriff auf das Dateisystem hat, wird für solche Operationen typischerweise das `fs` Modul verwendet. Hier ist eine einfache Methode, um zu überprüfen, ob ein Verzeichnis mithilfe von `fs.existsSync()` existiert:

```javascript
const fs = require('fs');

const directoryPath = './sample-directory';

// Überprüfen, ob das Verzeichnis existiert
if (fs.existsSync(directoryPath)) {
  console.log('Verzeichnis existiert.');
} else {
  console.log('Verzeichnis existiert nicht.');
}
```
**Beispielausgabe:**
```
Verzeichnis existiert.
```
Oder, für einen nicht-blockierenden asynchronen Ansatz, verwenden Sie `fs.promises` mit `async/await`:

```javascript
const fs = require('fs').promises;

async function checkDirectory(directoryPath) {
  try {
    await fs.access(directoryPath);
    console.log('Verzeichnis existiert.');
  } catch (error) {
    console.log('Verzeichnis existiert nicht.');
  }
}

checkDirectory('./sample-directory');
```
**Beispielausgabe:**
```
Verzeichnis existiert.
```

Für Projekte, die intensiv Datei- und Verzeichnisoperationen nutzen, bietet das `fs-extra` Paket, eine Erweiterung des nativen `fs` Moduls, praktische zusätzliche Methoden. So können Sie dasselbe mit `fs-extra` erreichen:

```javascript
const fs = require('fs-extra');

const directoryPath = './sample-directory';

// Überprüfen, ob das Verzeichnis existiert
fs.pathExists(directoryPath)
  .then(exists => console.log(exists ? 'Verzeichnis existiert.' : 'Verzeichnis existiert nicht.'))
  .catch(err => console.error(err));
```
**Beispielausgabe:**
```
Verzeichnis existiert.
```

Dieser Ansatz ermöglicht sauberen, gut lesbaren Code, der sich nahtlos in moderne JavaScript-Praktiken integriert.
