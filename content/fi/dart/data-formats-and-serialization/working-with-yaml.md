---
title:                "Työskentely YAML:n kanssa"
date:                  2024-03-08T21:57:36.175232-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Mikä & Miksi?

YAML, lyhenne sanoista YAML Ain't Markup Language, on ihmisluettava tietojen serialisointiformaatti. Ohjelmoijat käyttävät sitä asetustiedostoihin, tietojen vaihtoon ja sovelluksissa, joissa tietoja on tallennettava tai lähetettävä muodossa, joka on helppo ymmärtää.

## Kuinka:

Dartissa YAML:n käyttö tyypillisesti edellyttää kolmannen osapuolen kirjaston käyttöä, koska kieli ei sisällä sisäänrakennettuja YAML-jäsennysominaisuuksia. Suosittu valinta on `yaml`-paketti. Aloittaaksesi sinun tulee lisätä tämä paketti `pubspec.yaml`-tiedostoosi:

```yaml
dependencies:
  yaml: ^3.1.0
```

Muista suorittaa `pub get` noutaaksesi paketin.

### YAML:n lukeminen

YAML-tiedoston lukemiseksi, tuo ensin `yaml`-paketti ja käytä sitten `loadYaml`-funktiota:

```dart
import 'package:yaml/yaml.dart';
import 'dart:io';

void main() {
  final file = File('config.yaml').readAsStringSync();
  final yamlMap = loadYaml(file);

  print(yamlMap['name']); // Tulostus: John Doe
}

```

Olettaen, että `config.yaml`-tiedostosi näyttää tältä:

```yaml
name: John Doe
age: 30
```

### YAML:n kirjoittaminen

Vaikka `yaml`-paketti onkin hieno jäsennykseen, se ei tue YAML:n kirjoittamista. Tätä varten saatat joutua muuntamaan tietosi manuaalisesti YAML:ksi tai käyttämään toista pakettia, jos sellainen on saatavilla. Tai, yksinkertaisemmin, hallitsemaan datamuunnoksiasi ja tulostamaan ne merkkijonoina, jotka vastaavat YAML-syntaksia:

```dart
Map<String, dynamic> data = {
  'name': 'Jane Doe',
  'age': 29,
};

String toYamlString(Map<String, dynamic> map) {
  String yaml = '';
  map.forEach((key, value) {
    yaml += '$key: $value\n';
  });
  return yaml;
}

void main() {
  print(toYamlString(data)); // Tulostus: name: Jane Doe
                             //           age: 29
}
```

Tämä on alkeellinen lähestymistapa, eikä se välttämättä sovi monimutkaisiin tietorakenteisiin tai erityisiin YAML-ominaisuuksiin. Monimutkaisempien tarpeiden varalta saatat joutua etsimään tai myötävaikuttamaan kattavampaan Dart-pakettiin.
