---
title:                "Een datum ontleden uit een string"
date:                  2024-03-08T21:55:27.664930-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?
Een datum parseren vanuit een string in Dart houdt in dat je tekstuele weergaven van datums en tijden omzet naar een `DateTime` object. Deze bewerking is essentieel voor applicaties die te maken hebben met planning, gegevensanalyse, of elke functie die datummanipulatie vereist, zodat ervoor zorg gedragen wordt dat de datum gerelateerde gegevens correct worden begrepen en verwerkt door het programma.

## Hoe te:
De kernbibliotheek van Dart vereenvoudigt het parseren van datums door de `DateTime` klasse. Voor eenvoudige gevallen waarin je het formaat van de datumstring kent, kun je de `DateTime.parse()` methode gebruiken. Echter, voor meer complexe scenario's of wanneer je te maken hebt met meerdere formaten, wordt het `intl` package, specifiek de `DateFormat` klasse, onmisbaar.

### Gebruikmakend van Dart Kernbibliotheek:
```dart
void main() {
  // Gebruikmakend van DateTime.parse()
  var datumString = "2023-10-31";
  var geparseerdeDatum = DateTime.parse(datumString);
  
  print(geparseerdeDatum); // 2023-10-31 00:00:00.000
}
```

### Het `intl` Package Gebruiken:
Voeg eerst het `intl` package toe aan je `pubspec.yaml` bestand:
```yaml
dependencies:
  intl: ^0.17.0
```
Importeer vervolgens het package en gebruik `DateFormat` voor het parseren:
```dart
import 'package:intl/intl.dart';

void main() {
  var datumString = "October 31, 2023";
  var datumFormaat = DateFormat("MMMM dd, yyyy");
  var geparseerdeDatum = datumFormaat.parse(datumString);
  
  print(geparseerdeDatum); // 2023-10-31 00:00:00.000
}
```
Het `intl` package biedt robuuste opties voor het parseren van datums, waardoor verschillende internationale datumformaten naadloos kunnen worden gehanteerd.
