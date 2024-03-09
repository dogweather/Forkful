---
title:                "Czytanie argumentów z linii poleceń"
date:                  2024-03-08T21:56:07.190118-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Co i dlaczego?

Odczytywanie argumentów linii poleceń w Dart umożliwia programistom bezpośrednie wprowadzanie danych do konsoli podczas wykonywania programu Dart, zwiększając jego interaktywność i elastyczność dla różnych przypadków użycia, w tym skryptów automatyzujących, narzędzi CLI lub przetwarzania wsadowego. Funkcja ta jest kluczowa dla tworzenia elastycznych i przyjaznych dla użytkownika aplikacji konsolowych.

## Jak to zrobić:

Dart oferuje prostą metodę dostępu do argumentów linii poleceń za pośrednictwem `List<String> args` w głównej metodzie. Poniżej znajduje się prosty przykład demonstrujący, jak odczytywać i wykorzystywać argumenty linii poleceń.

```dart
// main.dart
void main(List<String> args) {
  print('Argumenty linii poleceń:');
  for (var i = 0; i < args.length; i++) {
    print('${i + 1}: ${args[i]}');
  }
}
```

Aby uruchomić ten program Dart i przekazać argumenty linii poleceń, użyj Dart CLI w następujący sposób:

```shell
dart run main.dart Hello World!
```

Oczekiwane wyjście:

```
Argumenty linii poleceń:
1: Hello
2: World!
```

### Używanie popularnej biblioteki stron trzecich: `args`

Chociaż wbudowane możliwości Darta do obsługi argumentów linii poleceń są solidne dla wielu aplikacji, pakiet `args` zapewnia udoskonalony sposób definiowania i analizowania argumentów linii poleceń dla bardziej złożonych potrzeb.

Najpierw dodaj pakiet `args` do swojego `pubspec.yaml`:

```yaml
dependencies:
  args: ^2.0.0
```

Następnie użyj go w swoim programie w następujący sposób:

```dart
// Używanie pakietu 'args'
import 'package:args/args.dart';

void main(List<String> arguments) {
  final parser = ArgParser()..addOption('name', abbr: 'n');
  final argResults = parser.parse(arguments);

  if (argResults.wasParsed('name')) {
    print('Cześć, ${argResults['name']}!');
  } else {
    print('Nie podano imienia.');
  }
}
```

Uruchom program z argumentem nazwanym:

```shell
dart run main.dart --name=John
```

Oczekiwane wyjście:

```
Cześć, John!
```

To proste wprowadzenie do analizowania argumentów linii poleceń, zarówno natywnie, jak i za pomocą biblioteki `args`, pokazuje, jak Dart może obsługiwać wejścia użytkownika bezpośrednio z konsoli, otwierając drogę do tworzenia bardziej interaktywnych i dynamicznych aplikacji CLI.
