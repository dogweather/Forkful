---
title:                "Obsługa błędów"
date:                  2024-03-08T21:56:45.382082-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Co & Dlaczego?
Obsługa błędów w Dart polega na przewidywaniu i zarządzaniu wyjątkami, które pojawiają się podczas wykonywania programu, aby zwiększyć jego niezawodność i użyteczność. Programiści implementują obsługę błędów, aby zapobiec awariom i zapewnić użytkownikom znaczące informacje zwrotne, gwarantując płynniejsze, bezpieczniejsze doświadczenie z aplikacją.

## Jak to zrobić:
Dart obsługuje dwa typy błędów: błędy *w czasie kompilacji* oraz błędy *w czasie wykonania*. Błędy w czasie kompilacji są wykrywane przez analizator Darta przed uruchomieniem kodu, natomiast błędy w czasie wykonania, czyli wyjątki, występują podczas wykonania. Oto jak obsługiwać wyjątki w Dart:

### Try-Catch
Użyj `try-catch`, aby przechwycić wyjątki i zapobiec awarii aplikacji:

```dart
try {
  var result = 100 ~/ 0; // Próba dzielenia przez zero, rzuca wyjątek
} catch (e) {
  print('Przechwycono wyjątek: $e'); // Obsługuje wyjątek
}
```
Przykładowe wyjście: `Przechwycono wyjątek: IntegerDivisionByZeroException`

### Konkretny Wyjątek
Aby obsłużyć konkretny wyjątek, wskaż wyjątek po `catch`:

```dart
try {
  var result = 100 ~/ 0;
} on IntegerDivisionByZeroException {
  print('Nie można dzielić przez zero.'); // Specyficznie obsługuje wyjątek dzielenia przez zero
}
```
Przykładowe wyjście: `Nie można dzielić przez zero.`

### Ślad Stosu
Aby uzyskać ślad stosu do debugowania, użyj drugiego parametru w bloku catch:

```dart
try {
  var result = 100 ~/ 0;
} catch (e, s) {
  print('Wyjątek: $e');
  print('Ślad stosu: $s'); // Drukuje ślad stosu do debugowania
}
```

### Finally
Użyj `finally`, aby wykonać kod po bloku try/catch, niezależnie od tego, czy wyjątek został rzucony:

```dart
try {
  var result = 100 ~/ 0;
} catch (e) {
  print('Przechwycono wyjątek: $e');
} finally {
  print('To jest zawsze wykonywane.'); // Kod czyszczący lub końcowe kroki
}
```
Przykładowe wyjście:
```
Przechwycono wyjątek: IntegerDivisionByZeroException
To jest zawsze wykonywane.
```

### Biblioteki Stron Trzecich
Chociaż podstawowa biblioteka Darta jest solidna do obsługi błędów, można również używać pakietów stron trzecich, takich jak `dartz` do programowania funkcyjnego, które wprowadzają takie pojęcia jak `Either` i `Option`, które można wykorzystać do obsługi błędów. Oto przykład użycia `dartz` do obsługi błędów:

1. Dodaj `dartz` do pliku `pubspec.yaml` w sekcji zależności:
```yaml
dependencies:
  dartz: ^0.10.0
```

2. Użyj `Either` do eleganckiej obsługi błędów w swoim kodzie Dart:
```dart
import 'package:dartz/dartz.dart';

Either<String, int> divide(int dzielnik, int dzielnik) {
  if (dzielnik == 0) {
    return Left('Nie można dzielić przez zero.');
  } else {
    return Right(dzielnik ~/ dzielnik);
  }
}

void main() {
  final result = divide(100, 0);
  result.fold(
    (left) => print('Błąd: $left'), 
    (right) => print('Wynik: $right')
  );
}
```
Przykładowe wyjście: `Błąd: Nie można dzielić przez zero.`

Część `Left` zazwyczaj reprezentuje błąd, a część `Right` sukces. Ten wzorzec pozwala na obsługę błędów w bardziej funkcyjny sposób, oferując przejrzystość i kontrolę nad zarządzaniem błędami.
