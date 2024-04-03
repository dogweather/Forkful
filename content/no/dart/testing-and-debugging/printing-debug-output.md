---
changelog:
- 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-08 21:55:55.255686-07:00
description: "\xC5 skrive ut debug-output i Dart handler om \xE5 vise informasjon\
  \ til konsollen under kj\xF8retiden, noe som gj\xF8r det mulig for utviklere \xE5\
  \ spore\u2026"
lastmod: '2024-03-13T22:44:40.490161-06:00'
model: gpt-4-0125-preview
summary: "\xC5 skrive ut debug-output i Dart handler om \xE5 vise informasjon til\
  \ konsollen under kj\xF8retiden, noe som gj\xF8r det mulig for utviklere \xE5 spore\
  \ utf\xF8relsesflyten, unders\xF8ke tilstanden til variabler eller identifisere\
  \ kilden til feil."
title: "Utskrift av feils\xF8kingsresultat"
weight: 33
---

## Hvordan:
I Dart kan du skrive ut debug-output ved å bruke `print()`-funksjonen. Slik skriver du ut enkle meldinger og variabelverdier:

```dart
void main() {
  String greeting = "Hallo, Dart!";
  print(greeting); // Skriver ut: Hallo, Dart!

  int number = 42;
  print('Tallet er $number.'); // Skriver ut: Tallet er 42.
}
```

For strukturerte data, som lister eller objekter, kan Dart sin `toString()`-metode kanskje ikke gi nok detaljer. I disse tilfellene kan du bruke `jsonEncode`-funksjonen fra Dart sin `dart:convert`-bibliotek for å konvertere dataene til en JSON-streng for mer lesbart output:

```dart
import 'dart:convert';

void main() {
  var user = {
    'name': 'John Doe',
    'age': 30,
    'emails': ['john.doe@example.com', 'john@example.com'],
  };

  print(jsonEncode(user));
  // Skriver ut: {"name":"John Doe","age":30,"emails":["john.doe@example.com","john@example.com"]}
}
```

Når mer sofistikerte feilsøkingsmuligheter er nødvendige, som logging med forskjellige viktighetsnivåer (info, advarsel, feil), kan du bruke tredjepartsbiblioteker som `logger`. Slik bruker du det:

1. Legg til `logger` i din `pubspec.yaml`:

```yaml
dependencies:
  logger: ^1.0.0
```

2. Bruk `logger` i din Dart-kode:

```dart
import 'package:logger/logger.dart';

var logger = Logger();

void main() {
  logger.d("Dette er en debug-melding");
  logger.w("Dette er en advarselmelding");
  logger.e("Dette er en feilmelding");
}
```

Outputen vil være mer informativ, ved å vise viktighetsnivået til meldingen og selve meldingen, noe som gjør det lettere å skille mellom forskjellige typer loggmeldinger.
