---
changelog:
- 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-08 21:57:36.284181-07:00
description: "YAML, \u0430\u0431\u0440\u0435\u0432\u0456\u0430\u0442\u0443\u0440\u0430\
  \ \u0432\u0456\u0434 \"YAML Ain't Markup Language\", \u0454 \u0444\u043E\u0440\u043C\
  \u0430\u0442\u043E\u043C \u0441\u0435\u0440\u0456\u0430\u043B\u0456\u0437\u0430\u0446\
  \u0456\u0457 \u0434\u0430\u043D\u0438\u0445, \u043F\u0440\u0438\u0437\u043D\u0430\
  \u0447\u0435\u043D\u0438\u043C \u0434\u043B\u044F \u0437\u0440\u0443\u0447\u043D\
  \u043E\u0433\u043E \u0447\u0438\u0442\u0430\u043D\u043D\u044F \u043B\u044E\u0434\
  \u0438\u043D\u043E\u044E. \u041F\u0440\u043E\u0433\u0440\u0430\u043C\u0456\u0441\
  \u0442\u0438 \u0432\u0438\u043A\u043E\u0440\u0438\u0441\u0442\u043E\u0432\u0443\u044E\
  \u0442\u044C\u2026"
lastmod: '2024-03-13T22:44:48.834837-06:00'
model: gpt-4-0125-preview
summary: "YAML, \u0430\u0431\u0440\u0435\u0432\u0456\u0430\u0442\u0443\u0440\u0430\
  \ \u0432\u0456\u0434 \"YAML Ain't Markup Language\", \u0454 \u0444\u043E\u0440\u043C\
  \u0430\u0442\u043E\u043C \u0441\u0435\u0440\u0456\u0430\u043B\u0456\u0437\u0430\u0446\
  \u0456\u0457 \u0434\u0430\u043D\u0438\u0445, \u043F\u0440\u0438\u0437\u043D\u0430\
  \u0447\u0435\u043D\u0438\u043C \u0434\u043B\u044F \u0437\u0440\u0443\u0447\u043D\
  \u043E\u0433\u043E \u0447\u0438\u0442\u0430\u043D\u043D\u044F \u043B\u044E\u0434\
  \u0438\u043D\u043E\u044E."
title: "\u0420\u043E\u0431\u043E\u0442\u0430 \u0437 YAML"
weight: 41
---

## Як це зробити:
У Dart робота з YAML, як правило, передбачає використання сторонньої бібліотеки, оскільки мова не включає вбудованих можливостей аналізу YAML. Популярний вибір — пакет `yaml`. Для початку, вам потрібно додати цей пакет до вашого `pubspec.yaml`:

```yaml
dependencies:
  yaml: ^3.1.0
```

Не забудьте запустити `pub get`, щоб завантажити пакет.

### Читання YAML
Щоб прочитати файл YAML, спочатку імпортуйте пакет `yaml`, а потім використовуйте функцію `loadYaml`:

```dart
import 'package:yaml/yaml.dart';
import 'dart:io';

void main() {
  final file = File('config.yaml').readAsStringSync();
  final yamlMap = loadYaml(file);

  print(yamlMap['name']); // Вивід: John Doe
}

```

Виходячи з того, що ваш файл `config.yaml` виглядає ось так:

```yaml
name: John Doe
age: 30
```

### Запис YAML
Хоча пакет `yaml` чудово підходить для аналізу, він не підтримує запис YAML. Для цього вам, можливо, доведеться вручну конвертувати ваші дані в YAML або використати інший пакет, якщо такий є. Або, простіше, керуйте перетвореннями ваших даних і виведіть їх як рядки, які відповідають синтаксису YAML:

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
  print(toYamlString(data)); // Вивід: name: Jane Doe
                             //         age: 29
}
```

Це примітивний підхід і може не підійти для складних структур даних або особливих функцій YAML. Для складніших потреб, можливо, доведеться шукати або допомагати в розробці більш повної бібліотеки Dart.
