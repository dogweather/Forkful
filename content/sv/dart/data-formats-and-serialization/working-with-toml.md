---
changelog:
- 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-08 21:57:20.355843-07:00
description: "TOML, eller Toms Uppenbara, Minimala Spr\xE5k, \xE4r ett konfigurationsfilformat\
  \ som \xE4r l\xE4tt att l\xE4sa p\xE5 grund av sin tydliga semantik. Programmerare\
  \ anv\xE4nder\u2026"
lastmod: '2024-03-13T22:44:37.637449-06:00'
model: gpt-4-0125-preview
summary: "TOML, eller Toms Uppenbara, Minimala Spr\xE5k, \xE4r ett konfigurationsfilformat\
  \ som \xE4r l\xE4tt att l\xE4sa p\xE5 grund av sin tydliga semantik."
title: Att Arbeta med TOML
weight: 39
---

## Hur man gör:
Dart inkluderar inte inbyggt stöd för TOML, men du kan arbeta med TOML-filer med hjälp av tredjepartspaket som `toml`. Lägg först till `toml` i din `pubspec.yaml`:

```yaml
dependencies:
  toml: ^0.10.0
```

### Läsa TOML
För att läsa en TOML-fil, låt oss anta att du har en enkel konfigurationsfil `config.toml`:

```toml
[database]
server = "192.168.1.1"
ports = [ 8001, 8001, 8002 ]
connection_max = 5000
enabled = true
```

Du kan tolka denna TOML-fil i Dart enligt följande:

```dart
import 'dart:io';
import 'package:toml/toml.dart';

void main() async {
  var innehåll = await File('config.toml').readAsString();
  var doc = TomlDocument.parse(innehåll);
  var data = doc.toMap();

  print(data['database']); // Skriv ut 'database'-sektionen
}
```

Detta skriver ut:

```dart
{server: 192.168.1.1, ports: [8001, 8001, 8002], connection_max: 5000, enabled: true}
```

### Skriva TOML
För att skapa TOML-innehåll, använd `TomlBuilder` som tillhandahålls av `toml`-paketet:

```dart
import 'package:toml/toml.dart';

void main() {
  final byggare = TomlBuilder();

  byggare.table('database')
    ..set('server', '192.168.1.1')
    ..set('ports', [8001, 8001, 8002])
    ..set('connection_max', 5000)
    ..set('enabled', true);

  var tomlString = byggare.build().toString();
  print(tomlString);
}
```

Detta kommer att generera och skriva ut en strängrepresentation av TOML-innehållet, mycket lik vår `config.toml`-fil:

```toml
[database]
server = "192.168.1.1"
ports = [8001, 8001, 8002]
connection_max = 5000
enabled = true
```

Dessa exempel visar hur man läser från och skriver till TOML-filer, vilket gör det enkelt att arbeta med konfigurationsdata i dina Dart-applikationer.
