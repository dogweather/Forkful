---
title:                "Sprawdzanie, czy katalog istnieje"
date:                  2024-03-08T21:54:03.432847-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Co i dlaczego?

Sprawdzanie, czy katalog istnieje w języku Dart, polega na weryfikacji obecności katalogu pod określoną ścieżką w systemie plików przed wykonaniem operacji takich jak odczyt lub zapis plików. Programiści robią to, aby uniknąć błędów, które występują podczas próby dostępu lub modyfikacji katalogów, które nie istnieją.

## Jak to zrobić:

Dart używa biblioteki `dart:io` do pracy z plikami i katalogami. Oto prosty sposób, aby sprawdzić, czy katalog istnieje:

```dart
import 'dart:io';

void main() {
  var directory = Directory('ścieżka/do/twojego/katalogu');

  if (directory.existsSync()) {
    print('Katalog istnieje');
  } else {
    print('Katalog nie istnieje');
  }
}
```
Przykładowe wyjście, jeśli katalog istnieje:
```
Katalog istnieje
```

Lub jeśli nie istnieje:
```
Katalog nie istnieje
```

Aby poradzić sobie z bardziej skomplikowanymi scenariuszami, takimi jak asynchroniczne sprawdzanie lub tworzenie katalogu, jeśli nie istnieje, można użyć następującego podejścia:

```dart
import 'dart:io';

void main() async {
  var directory = Directory('ścieżka/do/twojego/katalogu');

  // Asynchroniczne sprawdzanie, czy katalog istnieje
  var exists = await directory.exists();
  if (exists) {
    print('Katalog istnieje');
  } else {
    print('Katalog nie istnieje, tworzenie...');
    await directory.create(); // To tworzy katalog
    print('Katalog został utworzony');
  }
}
```

Przykładowe wyjście, jeśli katalog nie istniał i został utworzony:
```
Katalog nie istnieje, tworzenie...
Katalog został utworzony
```

Wbudowane możliwości Darta są zazwyczaj wystarczające do obsługi plików i katalogów, więc biblioteki stron trzecich zazwyczaj nie są potrzebne do tego zadania. Jednak dla bardziej skomplikowanych operacji na systemie plików, pakiety takie jak `path` (do manipulacji ścieżkami w sposób niezależny od platformy) mogą uzupełniać bibliotekę `dart:io`, ale nie oferują bezpośrednio bardziej zaawansowanych sprawdzeń istnienia katalogów niż to, co zostało pokazane.
