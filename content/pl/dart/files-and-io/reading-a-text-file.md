---
title:                "Czytanie pliku tekstowego"
date:                  2024-03-08T21:55:33.878496-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Co i dlaczego?

Odczytywanie pliku tekstowego w Dart polega na dostępie i pobieraniu danych z plików zapisanych w systemie plików. Programiści robią to, aby obsługiwać dane wejściowe, ustawienia konfiguracyjne lub czytać zbiory danych, co czyni to podstawową operacją dla wielu aplikacji, od prostych skryptów po złożone aplikacje.

## Jak to zrobić:

Podstawowa biblioteka Darta, `dart:io`, zapewnia niezbędne funkcjonalności do synchronicznego lub asynchronicznego odczytu plików tekstowych. Oto jak podejść do obu metod.

**Synchronicznie:**

```dart
import 'dart:io';

void main() {
  var fileName = "ścieżka/do/twojego/pliku_tekstowego.txt";
  var file = File(fileName);

  // Odczytywanie pliku synchronicznie
  var contents;
  try {
    contents = file.readAsStringSync();
    print(contents);
  } catch (e) {
    print('Błąd odczytu pliku: $e');
  }
}
```

**Asynchronicznie:**

Aby nie blokować programu podczas odczytywania pliku, co jest szczególnie przydatne dla dużych plików lub responsywnych aplikacji:

```dart
import 'dart:io';

void main() async {
  var fileName = "ścieżka/do/twojego/pliku_tekstowego.txt";
  var file = File(fileName);

  try {
    String contents = await file.readAsString();
    print(contents);
  } catch (e) {
    print('Błąd odczytu pliku: $e');
  }
}
```

**Przykładowe wyjście:**

Jeśli twój plik tekstowy zawiera:

```
Hello, Dart!
```

Obie powyższe metody wyświetlą:

```
Hello, Dart!
```

**Korzystanie z biblioteki innej firmy:**

Dla dodatkowych funkcji, takich jak uproszczone operacje na plikach lub ulepszone obsługi błędów, można rozważyć biblioteki stron trzecich, takie jak `package:file`. Jednak, jak wynika z mojej ostatniej aktualizacji, bezpośrednie używanie podstawowego pakietu `dart:io`, jak pokazano powyżej, jest najbardziej powszechną i prostą metodą odczytu plików tekstowych w Dart.
