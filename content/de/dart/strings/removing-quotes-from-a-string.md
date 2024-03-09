---
title:                "Anführungszeichen aus einem String entfernen"
date:                  2024-03-08T21:55:52.712770-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## Was & Warum?
Das Entfernen von Anführungszeichen aus einem String in Dart bedeutet, die doppelten (") oder einfachen (') Anführungszeichen am Anfang und Ende eines Strings zu entfernen, was für die Datenbereinigung oder die Vorbereitung von Strings für die weitere Verarbeitung nützlich ist. Programmierer tun dies, um Dateneingaben zu normalisieren, Uniformität in der Datenspeicherung zu gewährleisten oder wenn sie mit APIs interagieren, die Daten in zitierten Formaten zurückgeben können.

## Wie:
Dart bietet unkomplizierte Möglichkeiten, Anführungszeichen aus einem String zu entfernen, indem eingebaute String-Methoden verwendet werden, ohne dass Drittanbieter-Bibliotheken erforderlich sind.

### Beispiel 1: Verwendung von `replaceFirst` und `replaceAll`
Wenn Sie mit Strings arbeiten, die mit Anführungszeichen beginnen und enden, können Sie die Methoden `replaceFirst` und `replaceAll` verwenden, um sie zu entfernen.

```dart
String quotedString = '"Hallo, Welt!"';
String singleQuotedString = '\'Dart Programmierung\'';

// Entfernen doppelter Anführungszeichen
String noDoubleQuotes = quotedString.replaceFirst('"', '').replaceAll('"', '');
print(noDoubleQuotes); // Ausgabe: Hallo, Welt!

// Entfernen einzelner Anführungszeichen
String noSingleQuotes = singleQuotedString.replaceFirst('\'', '').replaceAll('\'', '');
print(noSingleQuotes); // Ausgabe: Dart Programmierung
```

### Beispiel 2: Verwendung von `substring`
Diese Methode ist nützlich, wenn Sie sicher sind, dass die Anführungszeichen ganz am Anfang und am Ende des Strings stehen.

```dart
String quotedString = '"Flutter Entwicklung"';
// Überprüfen, ob es mit Anführungszeichen beginnt und endet, bevor Sie sie entfernen, um Fehler zu vermeiden
if (quotedString.startsWith('"') && quotedString.endsWith('"')) {
  quotedString = quotedString.substring(1, quotedString.length - 1);
}
print(quotedString); // Ausgabe: Flutter Entwicklung
```

### Beispiel 3: Benutzerdefinierte Erweiterungsmethode
Für mehr Wiederverwendbarkeit, insbesondere wenn Ihr Projekt häufiges Entfernen von Anführungszeichen beinhaltet, sollten Sie eine benutzerdefinierte Erweiterung für `String` erstellen.

```dart
extension UnquoteString on String {
  String unquote() {
    var str = this;
    if (str.startsWith('"') && str.endsWith('"') || str.startsWith('\'') && str.endsWith('\'')) {
      str = str.substring(1, str.length - 1);
    }
    return str;
  }
}

void main() {
  String doubleQuoted = '"Das ist Dart"';
  String singleQuoted = '\'Das ist fantastisch\'';
  print(doubleQuoted.unquote()); // Ausgabe: Das ist Dart
  print(singleQuoted.unquote()); // Ausgabe: Das ist fantastisch
}
```

Diese Ansätze sollten Ihnen helfen, Anführungszeichen aus Strings in Dart effektiv zu entfernen, was Ihre Datenverarbeitungs- und Vorbereitungsworkflows verbessert.
