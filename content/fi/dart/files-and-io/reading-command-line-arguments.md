---
title:                "Komentorivin argumenttien lukeminen"
date:                  2024-03-08T21:55:43.200429-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Mikä & Miksi?

Komentoriviargumenttien lukeminen Dartissa mahdollistaa ohjelmoijien syöttää tietoja suoraan konsoliin Dart-ohjelman suorittamisen aikana, parantaen sen interaktiivisuutta ja joustavuutta erilaisissa käyttötapauksissa, mukaan lukien automaatioskriptit, CLI-työkalut tai eränkäsittely. Tämä ominaisuus on keskeinen, kun luodaan sopeutuvia ja käyttäjäystävällisiä komentorivisovelluksia.

## Kuinka:

Dart tarjoaa suoraviivaisen tavan päästä käsiksi komentoriviargumentteihin `List<String> args`:n kautta päämetodissa. Alla on yksinkertainen esimerkki, joka näyttää, kuinka lukea ja käyttää komentoriviargumentteja.

```dart
// main.dart
void main(List<String> args) {
  print('Komentoriviargumentit:');
  for (var i = 0; i < args.length; i++) {
    print('${i + 1}: ${args[i]}');
  }
}
```

Suorittaaksesi tämän Dart-ohjelman ja syöttääksesi komentoriviargumentteja, käytä Dart CLI:tä seuraavasti:

```shell
dart run main.dart Hei Maailma!
```

Odotettu tulos:

```
Komentoriviargumentit:
1: Hei
2: Maailma!
```

### Käyttäen Suosittua Kolmannen Osapuolen Kirjastoa: `args`

Vaikka Dartin sisäänrakennetut valmiudet komentoriviargumenttien käsittelyyn ovatkin riittävät moniin sovelluksiin, `args`-paketti tarjoaa hienostuneen tavan määritellä ja jäsentää komentoriviargumentteja monimutkaisempiin tarpeisiin.

Lisää ensin `args`-paketti `pubspec.yaml`-tiedostoosi:

```yaml
dependencies:
  args: ^2.0.0
```

Käytä sitten ohjelmassasi seuraavasti:

```dart
// Käyttäen 'args'-pakettia
import 'package:args/args.dart';

void main(List<String> arguments) {
  final parser = ArgParser()..addOption('name', abbr: 'n');
  final argResults = parser.parse(arguments);

  if (argResults.wasParsed('name')) {
    print('Hei, ${argResults['name']}!');
  } else {
    print('Nimeä ei annettu.');
  }
}
```

Suorita ohjelma nimetyn argumentin kanssa:

```shell
dart run main.dart --name=John
```

Odotettu tulos:

```
Hei, John!
```

Tämä yksinkertainen johdatus komentoriviargumenttien jäsentämiseen, sekä natiivisti että `args`-kirjaston avulla, esittelee, kuinka Dart voi käsitellä käyttäjän syötteitä suoraan konsolista, avaten polun interaktiivisempien ja dynaamisempien CLI-sovellusten luomiselle.
