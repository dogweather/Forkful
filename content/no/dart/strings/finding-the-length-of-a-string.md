---
changelog:
- 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-08 21:54:50.123627-07:00
description: "\xC5 finne lengden p\xE5 en String i Dart handler om \xE5 bestemme antallet\
  \ kodeenheter (i hovedsak antallet tegn hvis man tenker p\xE5 det p\xE5 en forenklet\
  \ m\xE5te) i en\u2026"
lastmod: '2024-03-13T22:44:40.477431-06:00'
model: gpt-4-0125-preview
summary: "\xC5 finne lengden p\xE5 en String i Dart handler om \xE5 bestemme antallet\
  \ kodeenheter (i hovedsak antallet tegn hvis man tenker p\xE5 det p\xE5 en forenklet\
  \ m\xE5te) i en gitt String."
title: "Finne lengden p\xE5 en streng"
weight: 7
---

## Slik gjør du:
Dart gjør det enkelt å få lengden på en streng ved å bruke `length`-egenskapen. Her er et grunnleggende eksempel:

```dart
void main() {
  String myString = "Hello, Dart!";
  print("Lengden på '\(myString)' er: \(myString.length)");
  // Utdata: Lengden på 'Hello, Dart!' er: 12
}
```
Denne egenskapen teller antall UTF-16 kodeenheter i strengen, som tilsvarer strengens lengde for de fleste vanlige bruksområder.

For mer nyansert tekstbehandling, spesielt med tanke på Unicode-tegn utenfor det grunnleggende flerspråklige planet (BMP), bør man vurdere å bruke `characters`-pakken for å telle grafemklynger, som representerer brukeroppfattede tegn mer nøyaktig.

Først, legg til `characters` i din `pubspec.yaml`:

```yaml
dependencies:
  characters: ^1.2.0
```

Deretter, bruk den slik:

```dart
import 'package:characters/characters.dart';

void main() {
  String myEmojiString = "👨‍👩‍👧‍👦 family";
  print("Lengden på '\(myEmojiString)' er: \(myEmojiString.characters.length)");
  // Utdata: Lengden på '👨‍👩‍👧‍👦 family' er: 8
}
```

I dette eksemplet gir `myEmojiString.characters.length` oss lengden i form av Unicode-grafemklynger, som er en mer nøyaktig representasjon for strenger som inneholder komplekse tegn, som emojis eller kombinerte tegnmerker.
