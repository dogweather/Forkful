---
title:                "Interpolering av en streng"
date:                  2024-03-08T21:55:01.000644-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Hva og hvorfor?

Strenginterpolasjon er prosessen med å injisere variabelverdier direkte inn i strenger, ofte for å skape meningsfulle meldinger uten tungvinte sammenslåinger. Programmerere gjør dette for renere, mer lesbare koder, og for å forhindre feil som er tilbøyelige til å skje i komplekse strengsammenslåinger.

## Hvordan:

I Dart er strenginterpolasjon grei, ved å bruke `$`-symbolet for å interpolere uttrykk direkte innenfor strengliteraler:

```dart
void main() {
  String name = 'Dart';
  int year = 2023;
  // Enkel variabelinterpolasjon
  print('Lærer $name i $year!');
  // Utdata: Lærer Dart i 2023!
  
  // Interpolerer uttrykk
  print('Om to år, vil det være ${year + 2}.');
  // Utdata: Om to år, vil det være 2025.
}
```

I tilfeller der du har mer komplekse uttrykk, eller ønsker å utføre operasjoner innenfor strengen selv, omslutt uttrykket med `${}`. Dart har ikke noen populære tredjepartsbiblioteker spesifikt for strenginterpolasjon ettersom det er godt utrustet fra før for å håndtere varierte og komplekse scenarioer.
