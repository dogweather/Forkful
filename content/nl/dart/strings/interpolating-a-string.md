---
changelog:
- 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-08 21:54:49.446402-07:00
description: "Stringinterpolatie is het proces van het direct invoegen van variabele\
  \ waarden in strings, vaak om betekenisvolle berichten te cre\xEBren zonder lastige\u2026"
lastmod: '2024-03-13T22:44:50.490151-06:00'
model: gpt-4-0125-preview
summary: "Stringinterpolatie is het proces van het direct invoegen van variabele waarden\
  \ in strings, vaak om betekenisvolle berichten te cre\xEBren zonder lastige aaneenschakelingen."
title: Een string interpoleren
weight: 8
---

## Hoe te:
In Dart is stringinterpolatie eenvoudig, met behulp van het `$`-symbool om uitdrukkingen direct in string literals te interpoleren:

```dart
void main() {
  String name = 'Dart';
  int year = 2023;
  // Eenvoudige variabele interpolatie
  print('Leren $name in $year!');
  // Output: Leren Dart in 2023!
  
  // Uitdrukkingen interpoleren
  print('Over twee jaar zal het ${year + 2} zijn.');
  // Output: Over twee jaar zal het 2025 zijn.
}
```

In het geval waar je meer complexe uitdrukkingen hebt of operaties binnen de string zelf wilt uitvoeren, sluit de uitdrukking in met `${}`. Dart heeft geen populaire bibliotheken van derden specifiek voor stringinterpolatie, omdat het van nature goed uitgerust is om gevarieerde en complexe scenario's te hanteren.
