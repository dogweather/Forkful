---
title:                "Fehlerbehandlung"
date:                  2024-03-08T21:55:37.033305-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Was & Warum?
Fehlerbehandlung in Dart geht darum, Ausnahmen, die während der Ausführung des Programms auftreten, vorherzusehen und zu verwalten, um die Zuverlässigkeit und Benutzerfreundlichkeit zu erhöhen. Programmierer implementieren Fehlerbehandlung, um Abstürze zu verhindern und den Benutzern aussagekräftiges Feedback zu geben, um eine reibungslosere, sicherere Anwendungserfahrung zu gewährleisten.

## Wie man:
Dart unterstützt zwei Arten von Fehlern: *Kompilierzeit*-Fehler und *Laufzeit*-Fehler. Kompilierzeitfehler werden vom Dart-Analyzer erkannt, bevor der Code ausgeführt wird, während Laufzeitfehler oder Ausnahmen während der Ausführung auftreten. So gehst du mit Ausnahmen in Dart um:

### Try-Catch
Verwende `try-catch`, um Ausnahmen zu erfassen und zu verhindern, dass sie deine Anwendung abstürzen lassen:

```dart
try {
  var result = 100 ~/ 0; // Versuch der Division durch Null, löst eine Ausnahme aus
} catch (e) {
  print('Eine Ausnahme gefangen: $e'); // Behandelt die Ausnahme
}
```
Beispielausgabe: `Eine Ausnahme gefangen: IntegerDivisionByZeroException`

### Spezifische Ausnahme
Um spezifische Ausnahmen zu behandeln, nenne die Ausnahme nach `catch`:

```dart
try {
  var result = 100 ~/ 0;
} on IntegerDivisionByZeroException {
  print('Kann nicht durch Null teilen.'); // Behandelt spezifisch die Division-durch-Null-Ausnahmen
}
```
Beispielausgabe: `Kann nicht durch Null teilen.`

### Stack Trace
Um einen Stack Trace zur Fehlersuche zu erhalten, verwende einen zweiten Parameter im Catch-Block:

```dart
try {
  var result = 100 ~/ 0;
} catch (e, s) {
  print('Ausnahme: $e');
  print('Stack Trace: $s'); // Gibt Stack Trace zur Fehlersuche aus
}
```

### Finally
Verwende `finally`, um Code nach try/catch auszuführen, unabhängig davon, ob eine Ausnahme geworfen wurde:

```dart
try {
  var result = 100 ~/ 0;
} catch (e) {
  print('Eine Ausnahme gefangen: $e');
} finally {
  print('Das wird immer ausgeführt.'); // Aufräumcode oder finale Schritte
}
```
Beispielausgabe:
```
Eine Ausnahme gefangen: IntegerDivisionByZeroException
Das wird immer ausgeführt.
```

### Drittanbieter-Bibliotheken
Obwohl Dart's Kernbibliothek robust für die Fehlerbehandlung ist, kannst du auch Drittanbieter-Pakete wie `dartz` für funktionale Programmierung verwenden, die Konzepte wie `Either` und `Option` einführen, die für die Fehlerbehandlung verwendet werden können. Hier ist ein Beispiel, wie man `dartz` für die Fehlerbehandlung verwendet:

1. Füge `dartz` zu deiner `pubspec.yaml`-Datei unter den Abhängigkeiten hinzu:
```yaml
dependencies:
  dartz: ^0.10.0
```

2. Verwende `Either` für eine elegante Fehlerbehandlung in deinem Dart-Code:
```dart
import 'package:dartz/dartz.dart';

Either<String, int> divide(int Dividende, int Divisor) {
  if (Divisor == 0) {
    return Left('Kann nicht durch Null teilen.');
  } else {
    return Right(Dividende ~/ Divisor);
  }
}

void main() {
  final result = divide(100, 0);
  result.fold(
    (left) => print('Fehler: $left'), 
    (right) => print('Ergebnis: $right')
  );
}
```
Beispielausgabe: `Fehler: Kann nicht durch Null teilen.`

Der `Left`-Teil repräsentiert normalerweise den Fehler, und der `Right`-Teil repräsentiert den Erfolg. Dieses Muster ermöglicht eine Fehlerbehandlung auf funktionale Weise und bietet Klarheit und Kontrolle über das Fehlermanagement.
