---
title:                "Working with YAML"
date:                  2024-03-08T21:33:58.218914-07:00
model:                 gpt-4-0125-preview
---

{{< edit_this_page >}}

## What & Why?

YAML, short for YAML Ain't Markup Language, is a human-readable data serialization format. Programmers use it for configuration files, data exchange, and in applications where data needs to be stored or transmitted in a format that is easy to understand.

## How to:

In Dart, working with YAML typically involves using a third-party library as the language does not include built-in YAML parsing capabilities. A popular choice is the `yaml` package. To begin, you'll need to add this package to your `pubspec.yaml`:

```yaml
dependencies:
  yaml: ^3.1.0
```

Remember to run `pub get` to fetch the package.

### Reading YAML

To read a YAML file, first, import the `yaml` package and then use the `loadYaml` function:

```dart
import 'package:yaml/yaml.dart';
import 'dart:io';

void main() {
  final file = File('config.yaml').readAsStringSync();
  final yamlMap = loadYaml(file);

  print(yamlMap['name']); // Output: John Doe
}

```

Assuming your `config.yaml` file looks like this:

```yaml
name: John Doe
age: 30
```

### Writing YAML

While the `yaml` package is great for parsing, it doesn't support writing YAML. For that, you might need to convert your data to YAML manually or use another package if available. Or, more straightforwardly, manage your data transformations and output them as strings that match YAML syntax:

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
  print(toYamlString(data)); // Output: name: Jane Doe
                             //         age: 29
}
```

This is a rudimentary approach and might not suit complex data structures or special YAML features. For sophisticated needs, you might have to look for or contribute to a more comprehensive Dart package.
