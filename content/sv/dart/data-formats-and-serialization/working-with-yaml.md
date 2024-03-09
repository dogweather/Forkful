---
title:                "Arbeta med YAML"
date:                  2024-03-08T21:57:39.226366-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Vad & Varför?

YAML, en förkortning för YAML Ain't Markup Language, är ett läsbart format för dataserialisering. Programmerare använder det för konfigurationsfiler, datautbyte och i applikationer där data behöver lagras eller överföras i ett format som är enkelt att förstå.

## Hur man gör:

I Dart involverar arbete med YAML vanligtvis användning av ett externt bibliotek eftersom språket inte inkluderar inbyggda YAML-tolkningsfunktioner. Ett populärt val är `yaml`-paketet. För att börja behöver du lägga till detta paket i din `pubspec.yaml`:

```yaml
dependencies:
  yaml: ^3.1.0
```

Kom ihåg att köra `pub get` för att hämta paketet.

### Läsa YAML

För att läsa en YAML-fil, börja med att importera `yaml`-paketet och använd sedan funktionen `loadYaml`:

```dart
import 'package:yaml/yaml.dart';
import 'dart:io';

void main() {
  final file = File('config.yaml').readAsStringSync();
  final yamlMap = loadYaml(file);

  print(yamlMap['name']); // Utdata: John Doe
}
```

Antag att din `config.yaml`-fil ser ut så här:

```yaml
name: John Doe
age: 30
```

### Skriva YAML

Även om `yaml`-paketet är bra för att tolka, stöder det inte skrivning av YAML. För det kan du behöva konvertera dina data till YAML manuellt eller använda ett annat paket om tillgängligt. Eller, mer rakt på sak, hantera dina datatransformationer och mata ut dem som strängar som matchar YAML-syntax:

```dart
Map<String, dynamic> data = {
  'name': 'Jane Doe',
  'age': 29,
};

String tillYamlString(Map<String, dynamic> map) {
  String yaml = '';
  map.forEach((key, value) {
    yaml += '$key: $value\n';
  });
  return yaml;
}

void main() {
  print(tillYamlString(data)); // Utdata: name: Jane Doe
                               //         age: 29
}
```

Detta är en grundläggande metod och kanske inte passar komplexa datastrukturer eller speciella YAML-funktioner. För mer avancerade behov kanske du måste leta efter eller bidra till ett mer omfattande Dart-paket.
