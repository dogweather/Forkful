---
title:                "Pisanie testów"
date:                  2024-03-08T21:58:15.355068-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Co i dlaczego?

Pisanie testów w Dart polega na tworzeniu przypadków testowych, aby automatycznie weryfikować, czy różne części programu działają zgodnie z oczekiwaniami. Programiści robią to, aby upewnić się, że ich kod jest niezawodny i wolny od defektów, co ułatwia łatwiejsze aktualizacje i refaktoryzację, a także zapobiega regresji.

## Jak to zrobić:

W Dartcie często używa się pakietu `test` do pisania testów. Najpierw dodaj pakiet `test` do pliku `pubspec.yaml`:

```yaml
dev_dependencies:
  test: ^1.0.0
```

Następnie napisz test dla prostej funkcji. Załóżmy, że masz funkcję, która dodaje dwie liczby:

```dart
int add(int a, int b) {
  return a + b;
}
```

Kolejno, utwórz plik o nazwie `add_test.dart` w katalogu `test` i napisz swój przypadek testowy:

```dart
import 'package:test/test.dart';
import '../lib/add.dart'; // Zakładając, że twoja funkcja `add` znajduje się w lib/add.dart

void main() {
  test('dodaje dwie liczby', () {
    var expected = 3;
    expect(add(1, 2), equals(expected));
  });
}
```

Aby uruchomić testy, użyj polecenia Dart:

```bash
$ dart test
```

Przykładowe wyjście może wyglądać tak:

```
00:01 +1: Wszystkie testy zakończone sukcesem!
```

### Używanie biblioteki firm trzecich: Mockito do mockowania

Do testowania kodu, który ma złożone zależności, możesz użyć Mockito do tworzenia obiektów mock. Najpierw dodaj Mockito do swojego `pubspec.yaml`:

```yaml
dev_dependencies:
  mockito: ^5.0.0
```

Załóżmy, że masz klasę `UserRepository`, która pobiera dane użytkownika, i chcesz przetestować `UserService`, który zależy od `UserRepository`, bez uderzania do prawdziwej bazy danych:

```dart
import 'package:mockito/mockito.dart';
import 'package:test/test.dart';
import 'package:your_project/user_repository.dart';
import 'package:your_project/user_service.dart';

// Tworzenie klasy Mock za pomocą Mockito
class MockUserRepository extends Mock implements UserRepository {}

void main() {
  group('Testy UserService', () {
    test('Pobiera użytkownika pomyślnie', () {
      // Utwórz instancję mock
      final mockUserRepository = MockUserRepository();
      final userService = UserService(mockUserRepository);

      // Ustawienie zachowania mock
      when(mockUserRepository.fetchUser(1)).thenReturn(User(id: 1, name: 'Testowy Użytkownik'));

      // Asercja, że zmokowana metoda została wywołana z oczekiwanymi argumentami
      expect(userService.getUserName(1), 'Testowy Użytkownik');
      verify(mockUserRepository.fetchUser(1)).called(1);
    });
  });
}
```

Uruchomienie tego testu potwierdza, że `UserService` poprawnie współpracuje z `UserRepository`, używając mockowania do symulowania prawdziwych interakcji w kontrolowany sposób.
