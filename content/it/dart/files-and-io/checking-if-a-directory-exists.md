---
changelog:
- 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-08 21:53:29.329476-07:00
description: "Controllare se una directory esiste in Dart comporta la verifica della\
  \ presenza di una directory in un percorso specificato sul file system prima di\u2026"
lastmod: '2024-03-13T22:44:43.147872-06:00'
model: gpt-4-0125-preview
summary: Controllare se una directory esiste in Dart comporta la verifica della presenza
  di una directory in un percorso specificato sul file system prima di eseguire operazioni
  come la lettura o la scrittura di file.
title: Verifica dell'esistenza di una directory
weight: 20
---

## Come fare:
Dart utilizza la libreria `dart:io` per lavorare con file e directory. Ecco un modo semplice per verificare se una directory esiste:

```dart
import 'dart:io';

void main() {
  var directory = Directory('percorso/della/tua/directory');

  if (directory.existsSync()) {
    print('La directory esiste');
  } else {
    print('La directory non esiste');
  }
}
```
Output di esempio se la directory esiste:
```
La directory esiste
```

Oppure, se non esiste:
```
La directory non esiste
```

Per gestire scenari più complessi, come il controllo asincrono o la creazione di una directory se non esiste, si potrebbe utilizzare il seguente approccio:

```dart
import 'dart:io';

void main() async {
  var directory = Directory('percorso/della/tua/directory');

  // Verifica asincronamente se la directory esiste
  var exists = await directory.exists();
  if (exists) {
    print('La directory esiste');
  } else {
    print('La directory non esiste, creazione in corso...');
    await directory.create(); // Questo crea la directory
    print('Directory creata');
  }
}
```

Output di esempio se la directory non esisteva ed è stata creata:
```
La directory non esiste, creazione in corso...
Directory creata
```

Le capacità integrate di Dart sono solitamente sufficienti per gestire file e directory, quindi le librerie di terze parti non sono tipicamente necessarie per questo compito. Tuttavia, per operazioni sul file system più complesse, pacchetti come `path` (per manipolare i percorsi in modo indipendente dalla piattaforma) possono completare la libreria `dart:io`, ma non offrono direttamente controlli di esistenza di directory più avanzati di quanto mostrato.
