---
date: 2024-01-26 00:55:13.205772-07:00
description: "Fehlerbehandlung in PHP bezieht sich auf das Verwalten und Reagieren\
  \ auf Bedingungen, die den normalen Ablauf eines Programms st\xF6ren, wie fehlende\
  \ Dateien\u2026"
lastmod: '2024-03-13T22:44:53.980045-06:00'
model: gpt-4-1106-preview
summary: "Fehlerbehandlung in PHP bezieht sich auf das Verwalten und Reagieren auf\
  \ Bedingungen, die den normalen Ablauf eines Programms st\xF6ren, wie fehlende Dateien\
  \ oder fehlerhafte Dateneingaben."
title: Fehlerbehandlung
weight: 16
---

## Wie geht das:
In PHP kannst du Fehler mithilfe von `try-catch`-Blöcken verwalten und den Prozess mit benutzerdefinierten Fehlerbehandlungen und Ausnahmen individuell anpassen.

```php
// Grundlegendes try-catch-Beispiel
try {
  // Etwas riskantes tun
  $file = fopen("nonexistentfile.txt", "r");
} catch (Exception $e) {
  // Den Fehler behandeln
  echo "Fehler: " . $e->getMessage();
}

// Einen benutzerdefinierten Fehlerbehandler einstellen
set_error_handler(function($severity, $message, $file, $line) {
  throw new ErrorException($message, 0, $severity, $file, $line);
});

// Ausnahmen verwenden
class MyException extends Exception {}

try {
  // Etwas tun und eine benutzerdefinierte Ausnahme auslösen
  throw new MyException("Benutzerdefinierter Fehler!");
} catch (MyException $e) {
  // Die benutzerdefinierte Ausnahme behandeln
  echo $e->getMessage();
}

// Beispiel-Ausgabe:
// Fehler: fopen(nonexistentfile.txt): failed to open stream: No such file or directory
// Benutzerdefinierter Fehler!
```

## Vertiefung
Früher waren PHP-Fehler mehr Warnungen und Hinweise, die die Ausführung des Skripts nicht stoppten. Mit der Reife der Sprache wurde eine robustere objektorientierte Fehlerbehandlung eingeführt, beginnend mit der Exception-Klasse in PHP 5. Später brachte PHP 7 Fehlerklassen heraus, welche Fehler und Ausnahmen endlich unterschieden.

Vor `try-catch`-Blöcken benutzte PHP `set_error_handler()`, um mit Fehlern umzugehen. `try-catch` ist sauberer und moderner. Aber benutzerdefinierte Fehlerbehandler haben immer noch ihren Platz, besonders bei Altcode oder wenn nicht-ausnahmebezogene Fehler abgefangen werden müssen.

Das `Throwable`-Interface in PHP 7+ bedeutet, dass egal, ob es sich um einen Fehler oder eine Ausnahme handelt, du beides abfangen kannst. Dies ist praktisch, weil du jetzt kritische Laufzeitfehler, die zuvor schwerer zu verfolgen waren, nicht verpasst.

Alternativen zu PHPs integrierten Mechanismen umfassen Bibliotheken und Frameworks, die mit eigenen Fehlerbehandlungssystemen kommen und mehr Funktionen wie Fehlerprotokollierung in Dateien oder das Anzeigen benutzerfreundlicher Fehlerseiten bieten.

## Siehe auch
- Offizielle PHP-Dokumentation zu Ausnahmen: https://www.php.net/manual/de/language.exceptions.php
- PHP The Right Way zur Fehlerberichterstattung: https://phptherightway.com/#error_reporting
- PHP-Handbuch zur Fehlerbehandlung: https://www.php.net/manual/de/book.errorfunc.php
