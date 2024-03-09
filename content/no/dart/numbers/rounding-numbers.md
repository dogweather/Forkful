---
title:                "Avrunding av tall"
date:                  2024-03-08T21:56:14.310552-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Hva & Hvorfor?

Avrunding av tall er prosessen med å justere et tall til nærmeste hele tall eller til et spesifisert antall desimalplasser. Programmerere runder ofte av tall for å forenkle beregninger, forbedre lesbarheten, eller forberede data for visning, noe som sikrer konsistens og klarhet i numeriske utdata.

## Hvordan:

Dart tilbyr native metoder i sin kjerne `num`-type for avrundingsoperasjoner. Her vil vi utforske metoder som `round()`, `floor()`, `ceil()`, og hvordan runde av til et spesifikt antall desimalplasser.

### Avrunding til nærmeste hele tall:

```dart
var number = 3.56;
print(number.round()); // Gir ut: 4
```

### Avrunding ned:

```dart
print(number.floor()); // Gir ut: 3
```

### Avrunding opp:

```dart
print(number.ceil()); // Gir ut: 4
```

### Avrunding til et spesifikt antall desimalplasser:

For å avrunde til et spesifikt antall desimalplasser, kan vi bruke metoden `toStringAsFixed()`, som returnerer en streng, eller bruke en kombinasjon av `pow` fra `dart:math` for et numerisk resultat.

```dart
import 'dart:math';

var number = 3.56789;
String roundedString = number.toStringAsFixed(2); // For visningsformål
print(roundedString); // Gir ut: 3.57

double roundedNumber = double.parse(roundedString);
print(roundedNumber); // Gir ut: 3.57

// Alternativt, for et numerisk resultat:
double roundedToDecimal = (number * pow(10, 2)).round().toDouble() / pow(10, 2);
print(roundedToDecimal); // Gir ut: 3.57
```

Mens Darts kjernebibliotek effektivt dekker de fleste behov for avrunding, kan biblioteker som `decimal` være nyttige for mer komplekse matematiske operasjoner eller presise avrundingskrav. `Decimal`-biblioteket gir en enkel måte å arbeide med desimaltall uten å miste presisjon, noe som er spesielt hendig for finansielle beregninger, men for enkle avrundingsmetoder som vist, er vanligvis Darts kjernefunksjonalitet tilstrekkelig.
