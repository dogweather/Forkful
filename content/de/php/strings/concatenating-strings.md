---
date: 2024-01-20 17:35:10.623643-07:00
description: "String-Konkatenation verbindet einfach zwei oder mehr Strings zu einem.\
  \ Programmierer nutzen das, um dynamische Textausgaben zu erzeugen oder Daten aus\u2026"
lastmod: '2024-03-13T22:44:53.964604-06:00'
model: gpt-4-1106-preview
summary: String-Konkatenation verbindet einfach zwei oder mehr Strings zu einem.
title: "Zeichenketten verkn\xFCpfen"
weight: 3
---

## How to:
PHP nutzt den Punkt (`.`), um Strings zu verketten. Hier ein paar Schnipsel:

```PHP
<?php
$anfang = 'Hallo ';
$ende = 'Welt!';
$begrüßung = $anfang . $ende;
echo $begrüßung; // Ausgabe: Hallo Welt!
?>
```
Variablen direkt in doppelten Anführungszeichen:

```PHP
<?php
$name = 'Peter';
echo "Guten Tag, $name!"; // Ausgabe: Guten Tag, Peter!
?>
```

String-Konkatenation mit Zuweisung:

```PHP
<?php
$text = 'PHP ';
$text .= 'ist ';
$text .= 'super!';
echo $text; // Ausgabe: PHP ist super!
?>
```

## Deep Dive
String-Konkatenation in PHP ist ein grundlegendes Feature, das seit den Anfängen dabei ist. Bevor PHP 4 gab es keine speziellen Operatoren dafür; Entwickler mussten Funktionen wie `strcat()` in C verwenden. 

Alternativen zur Konkatenation:
- `sprintf()` oder `printf()` für formatierte Strings.
- Heredoc-Syntax für komplexe und vielfältige Strings.
- Ab PHP 8 die nullsichere Konkatenation: `$a ??= 'default';`.

Implementation:
- Geschwindigkeit: Konkatenation ist schnell und effizient, aber bei sehr großen Strings sollte man auf Performanz achten.
- Speicher: PHP kopiert bei jeder Konkatenation den String, also Achtung bei Speicherüberlegungen.

## See Also
- PHP-Handbuch zur String-Konkatenation: [php.net/manual/de/language.operators.string.php](https://www.php.net/manual/de/language.operators.string.php)
- Leitfaden für gute Praktiken in PHP: [phptherightway.com](https://phptherightway.com)
