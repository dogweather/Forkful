---
title:                "Reguliere expressies gebruiken"
date:                  2024-03-08T21:57:11.013736-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?
Reguliere expressies (regex) in Dart bieden een krachtige manier om te zoeken en te manipuleren met strings, waardoor programmeurs complexe tekstverwerkingsopdrachten efficiënt kunnen uitvoeren. Door regex te begrijpen, kunnen ontwikkelaars tekstvalidaties uitvoeren, zoekpatronen vinden en teksttransformaties snel uitvoeren, wat essentieel is voor het verwerken van formulieren, gegevensparsen en algemene tekenreeksmanipulaties in moderne applicaties.

## Hoe:
Dart gebruikt de `RegExp` klasse voor reguliere expressies. Hier is een basisvoorbeeld om een eenvoudig patroon binnen een string te matchen:

```dart
void main() {
  var pattern = RegExp(r'\bDart\b');
  var text = 'Learning Dart programming is exciting.';

  if (pattern.hasMatch(text)) {
    print('Match gevonden!');
  } else {
    print('Geen match gevonden.');
  }
  // Uitvoer: Match gevonden!
}
```

Om matches uit een string te extraheren, kun je de `allMatches` methode gebruiken. Deze methode retourneert een iterabel van matches:

```dart
void main() {
  var pattern = RegExp(r'\b\w+\b');
  var text = 'Dart is awesome!';

  var matches = pattern.allMatches(text);
  for (final match in matches) {
    print(match.group(0)); // Dit print de overeenkomende substrings.
  }
  // Uitvoer:
  // Dart
  // is
  // awesome
}
```

Tekst vervangen kan worden bereikt met de `replaceFirst` of `replaceAll` methoden:

```dart
void main() {
  var pattern = RegExp(r'\bDart\b');
  var text = 'Dart is niet zomaar een dart.';
  
  // Vervang eerste voorkomen
  var gewijzigdeTekst = text.replaceFirst(pattern, 'Flutter');
  print(gewijzigdeTekst); 
  // Uitvoer: Flutter is niet zomaar een dart.

  // Vervang alle voorkomens
  gewijzigdeTekst = text.replaceAll(pattern, 'Flutter');
  print(gewijzigdeTekst);
  // Uitvoer: Flutter is niet zomaar een flutter.
}
```

Een string splitsen met een regex patroon is eenvoudig met de `split` methode:

```dart
void main() {
  var pattern = RegExp(r'\s+'); // Matcht elk witruimteteken
  var text = 'Dart is leuk';

  var delen = text.split(pattern);
  print(delen); 
  // Uitvoer: [Dart, is, leuk]
}
```

Voor complexe parsing of validaties die niet direct door Dart's `RegExp` worden ondersteund, zou je kunnen overwegen om third-party bibliotheken te gebruiken, maar Dart's standaardbibliotheek is vaak voldoende voor de meeste reguliere expressietaken, wat de bruikbaarheid en veelzijdigheid ervan benadrukt bij het afhandelen van reguliere expressies.
