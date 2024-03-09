---
title:                "Sette stor bokstav i en streng"
date:                  2024-03-08T21:54:07.351975-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Hva & Hvorfor?

Det å sette stor forbokstav i en streng innebærer å endre den første bokstaven i et ord eller en hel setning til stor bokstav, mens resten av tegnene forblir som de er. Programmerere bruker ofte denne teknikken for å formatere brukerinndata eller vise tekst for å sikre konsistens eller følge grammatiske regler i brukergrensesnitt.

## Hvordan:

### Ved å bruke Dart's innebygde metoder

Dart tilbyr enkle, direkte metoder for strengmanipulering. For å sette stor forbokstav i et ord eller en setning, vil du vanligvis ta det første tegnet, konvertere det til stor bokstav, og deretter konkatere det med resten av strengen. Slik kan du implementere det:

```dart
String capitalize(String text) {
  if (text.isEmpty) return text;
  return text[0].toUpperCase() + text.substring(1).toLowerCase();
}

void main() {
  var eksempel = "hallo verden";
  print(capitalize(eksempel)); // Utdata: Hallo verden
}
```

### Sette stor forbokstav i hvert ord

For å sette stor forbokstav på det første bokstaven i hvert ord i en streng, kan du dele strengen inn i ord, sette stor forbokstav på hver av dem, og deretter sette dem sammen igjen:

```dart
String capitalizeWords(String text) {
  return text.split(' ').map(capitalize).join(' ');
}

void main() {
  var eksempel = "hallo dart entusiaster";
  print(capitalizeWords(eksempel)); // Utdata: Hallo Dart Entusiaster
}
```

### Ved å bruke tredjepartsbibliotek

Selv om Dart's standardbibliotek dekker grunnleggende behov, kan visse oppgaver være mer praktisk å utføre ved bruk av tredjepakker. Et populært valg for utvidede strengmanipuleringsegenskaper, inkludert bruk av stor bokstav, er pakken [`recase`](https://pub.dev/packages/recase). Etter å ha lagt den til i prosjektets `pubspec.yaml`, kan du enkelt endre stor bokstaver i strenger blant annen funksjonalitet:

```dart
import 'package:recase/recase.dart';

void main() {
  var eksempel = "hallo verden";
  var rc = ReCase(eksempel);

  print(rc.titleCase); // Utdata: Hallo Verden
}
```

Ved å bruke `recase`, kan du sette stor forbokstav i individuelle ord, hele setninger, eller til og med følge andre skrivekonvensjoner uten å manuelt håndtere strengtransformasjonene.
