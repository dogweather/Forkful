---
title:                "Een nieuw project starten"
date:                  2024-03-08T21:56:31.314321-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?

Een nieuw project starten in Dart omvat het opzetten van een omgeving die bevorderlijk is voor efficiënte ontwikkeling, testen en implementatie. Programmeurs initiëren nieuwe Dart-projecten om te profiteren van Dart's optimale prestaties en robuuste ecosysteem, met name voor web- en mobiele app-ontwikkeling met frameworks zoals Flutter.

## Hoe:

1. **Installeer Dart**:
   Zorg ervoor dat Dart op je systeem is geïnstalleerd. Zo niet, dan kun je het downloaden van [https://dart.dev/get-dart](https://dart.dev/get-dart). Verifieer de installatie met:

   ```shell
   dart --version
   ```

2. **Maak een Nieuw Dart Project**:
   Gebruik de Dart CLI om een nieuw project te genereren:

   ```shell
   dart create hello_dart
   ```

   Dit commando maakt een nieuwe map `hello_dart` met een eenvoudige voorbeeldweb- of console-applicatie, afhankelijk van je selectie.

3. **Bekijk de Structuur van het Project**:
   
   Navigeer naar je projectmap:

   ```shell
   cd hello_dart
   ```

   Een typisch Dart-project bevat de volgende belangrijke bestanden en mappen:

   - `pubspec.yaml`: Configuratiebestand dat de afhankelijkheden van je project en SDK-beperkingen bevat.
   - `lib/`: Map waar het grootste deel van de Dart-code zich bevindt.
   - `test/`: Map voor projecttests.

4. **Voeg Afhankelijkheden Toe**:
   Bewerk `pubspec.yaml` om afhankelijkheden toe te voegen. Overweeg voor webprojecten het toevoegen van `http`, een populair pakket voor het maken van HTTP-verzoeken:

   ```yaml
   dependencies:
     flutter:
       sdk: flutter
     http: ^0.13.3
   ```

   Na het bewerken, haal de afhankelijkheden op:

   ```shell
   dart pub get
   ```

5. **Schrijf Je Eerste Dart Code**:
   
   In de map `lib/`, maak een nieuw Dart-bestand, `main.dart`, en voeg een eenvoudige Dart-code toe:

   ```dart
   // Importeer de Dart core-bibliotheek
   import 'dart:core';

   void main() {
     print('Hallo, Dart!');
   }
   ```

6. **Voer Je Dart Applicatie Uit**:

   Voer je Dart-programma uit met:

   ```shell
   dart run
   ```

   De uitvoer moet zijn:

   ```
   Hallo, Dart!
   ```

Door deze stappen te volgen, heb je met succes een nieuw Dart-project gestart, van installatie tot het uitvoeren van je eerste stuk Dart-code. Deze fundamentele kennis legt de basis voor het dieper duiken in het rijke ecosysteem van Dart en zijn mogelijkheden voor het bouwen van schaalbare applicaties.
