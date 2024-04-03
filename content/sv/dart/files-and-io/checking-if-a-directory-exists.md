---
changelog:
- 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-08 21:53:55.580943-07:00
description: "Att kontrollera om en katalog finns i Dart handlar om att verifiera\
  \ n\xE4rvaron av en katalog p\xE5 en angiven s\xF6kv\xE4g i filsystemet innan man\
  \ utf\xF6r operationer\u2026"
lastmod: '2024-03-13T22:44:37.627753-06:00'
model: gpt-4-0125-preview
summary: "Att kontrollera om en katalog finns i Dart handlar om att verifiera n\xE4\
  rvaron av en katalog p\xE5 en angiven s\xF6kv\xE4g i filsystemet innan man utf\xF6\
  r operationer som att l\xE4sa eller skriva filer."
title: Kontrollera om en katalog existerar
weight: 20
---

## Hur man gör:
Dart använder biblioteket `dart:io` för att arbeta med filer och kataloger. Här är ett enkelt sätt att kontrollera om en katalog finns:

```dart
import 'dart:io';

void main() {
  var directory = Directory('path/to/your/directory');

  if (directory.existsSync()) {
    print('Katalogen finns');
  } else {
    print('Katalogen finns inte');
  }
}
```
Exempelutskrift om katalogen finns:
```
Katalogen finns
```

Eller, om den inte finns:
```
Katalogen finns inte
```

För att hantera mer komplexa scenarier, såsom asynkront kontroll eller att skapa en katalog om den inte finns, kan du använda följande tillvägagångssätt:

```dart
import 'dart:io';

void main() async {
  var directory = Directory('path/to/your/directory');

  // Kontrollera asynkront om katalogen finns
  var exists = await directory.exists();
  if (exists) {
    print('Katalogen finns');
  } else {
    print('Katalogen finns inte, skapar...');
    await directory.create(); // Detta skapar katalogen
    print('Katalogen skapad');
  }
}
```

Exempelutskrift om katalogen inte fanns och skapades:
```
Katalogen finns inte, skapar...
Katalogen skapad
```

Darts inbyggda funktioner är vanligtvis tillräckliga för att hantera filer och kataloger, så tredjepartsbibliotek är vanligtvis inte nödvändiga för denna uppgift. Dock, för mer komplexa filsystemoperationer, kan paket som `path` (för att manipulera sökvägar på ett plattformsoberoende sätt) komplettera `dart:io`-biblioteket men erbjuder inte direkt mer avancerade kontroller av katalogexistens än vad som visas.
