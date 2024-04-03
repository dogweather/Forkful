---
changelog:
- 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-08 21:53:56.678514-07:00
description: "Att konvertera ett datum till en str\xE4ng i Dart \xE4r en vanlig uppgift\
  \ n\xE4r du beh\xF6ver visa datum- och tidsinformation i ett l\xE4ttl\xE4st format,\
  \ eller n\xE4r du\u2026"
lastmod: '2024-03-13T22:44:37.624501-06:00'
model: gpt-4-0125-preview
summary: "Att konvertera ett datum till en str\xE4ng i Dart \xE4r en vanlig uppgift\
  \ n\xE4r du beh\xF6ver visa datum- och tidsinformation i ett l\xE4ttl\xE4st format,\
  \ eller n\xE4r du t\xE4nker serialisera data f\xF6r lagring eller \xF6verf\xF6ring."
title: "Att konvertera ett datum till en str\xE4ng"
weight: 28
---

## Hur:
Dart tillhandahåller klassen `DateTime` för hantering av datum och tider, samt paketet `intl` för formatering. Se först till att du har paketet `intl` genom att lägga till `intl: ^0.17.0` (eller den senaste versionen) i din `pubspec.yaml`-fil.

### Använda Darts Kärnbibliotek
```dart
DateTime now = DateTime.now();
String formattedDate = "${now.year}-${now.month}-${now.day}";
print(formattedDate); // Utdata: 2023-4-12 (till exempel, detta beror på det aktuella datumet)
```

Detta exempel bygger direkt en sträng från `DateTime`-objektets egenskaper.

### Använda `intl`-paketet
Importera först paketet:

```dart
import 'package:intl/intl.dart';
```

Formatera sedan datumet:

```dart
DateTime now = DateTime.now();
String formattedDate = DateFormat('yyyy-MM-dd').format(now);
print(formattedDate); // Utdata: 2023-04-12
```

Paketet `intl` möjliggör mycket mer komplex formatering på ett enkelt sätt, inklusive lokal-specifika format:

```dart
String formattedDateLocale = DateFormat.yMMMMd('en_US').format(now);
print(formattedDateLocale); // Utdata: April 12, 2023
```

Dessa exempel visar enkla men kraftfulla sätt att konvertera och formatera datum till strängar i Dart, antingen genom att använda Darts kärnfunktioner eller genom att utnyttja `intl`-paketet för mer avancerade formateringsalternativ.
