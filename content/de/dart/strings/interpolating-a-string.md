---
changelog:
- 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-08 21:54:47.086903-07:00
description: "String-Interpolation ist der Prozess, Variablenwerte direkt in Strings\
  \ einzuf\xFCgen, oft um aussagekr\xE4ftige Nachrichten ohne umst\xE4ndliche Verkettungen\
  \ zu\u2026"
lastmod: '2024-03-13T22:44:53.564888-06:00'
model: gpt-4-0125-preview
summary: "String-Interpolation ist der Prozess, Variablenwerte direkt in Strings einzuf\xFC\
  gen, oft um aussagekr\xE4ftige Nachrichten ohne umst\xE4ndliche Verkettungen zu\
  \ erstellen."
title: Interpolation eines Strings
weight: 8
---

## Wie geht das:
In Dart ist die String-Interpolation unkompliziert, wobei das `$`-Symbol genutzt wird, um Ausdrücke direkt in String-Literalen zu interpolieren:

```dart
void main() {
  String name = 'Dart';
  int year = 2023;
  // Einfache Variableninterpolation
  print('Lerne $name im Jahr $year!');
  // Ausgabe: Lerne Dart im Jahr 2023!
  
  // Interpolation von Ausdrücken
  print('In zwei Jahren wird es ${year + 2} sein.');
  // Ausgabe: In zwei Jahren wird es 2025 sein.
}
```

Für den Fall, dass du komplexere Ausdrücke hast oder Operationen innerhalb des Strings selbst durchführen möchtest, schließe den Ausdruck in `${}` ein. Dart verfügt über keine populären Drittanbieter-Bibliotheken speziell für die String-Interpolation, da es von Haus aus gut ausgestattet ist, um vielfältige und komplexe Szenarien zu bewältigen.
