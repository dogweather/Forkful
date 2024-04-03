---
date: 2024-01-26 03:45:39.791884-07:00
description: "Das Runden von Zahlen bedeutet, die Dezimalstellen auf eine festgelegte\
  \ Genauigkeit abzuschneiden, oft auf ganze Zahlen. Programmierer runden, um\u2026"
lastmod: '2024-03-13T22:44:53.967373-06:00'
model: gpt-4-0125-preview
summary: Das Runden von Zahlen bedeutet, die Dezimalstellen auf eine festgelegte Genauigkeit
  abzuschneiden, oft auf ganze Zahlen.
title: Zahlen runden
weight: 13
---

## Wie geht das:
PHP bietet einige Möglichkeiten, Zahlen zu runden: `round()`, `ceil()` und `floor()`. So funktionieren sie:

```php
echo round(3.14159);   // Gibt 3 zurück
echo round(3.14159, 2); // Gibt 3.14 zurück

echo ceil(3.14159);    // Gibt 4 zurück, rundet immer auf

echo floor(3.14159);   // Gibt 3 zurück, rundet immer ab
```

## Vertiefung
Das Runden von Zahlen ist seit der Antike in Mathematik und Berechnung essentiell, um mit unpraktischen unendlichen Dezimalstellen umzugehen. In PHP kann `round()` einen Genauigkeitsparameter und Modus nehmen, der sein Verhalten beeinflusst – `PHP_ROUND_HALF_UP`, `PHP_ROUND_HALF_DOWN` usw. bestimmen, wie es sich verhält, wenn es auf ein ".5" Szenario trifft. Genauigkeit ist der Schlüssel in Finanzanwendungen, wo das Runden rechtlich reguliert sein könnte, was beeinflusst, wie `round()` im Code implementiert wird.

Alternativen zu integrierten Funktionen beinhalten benutzerdefinierte Rundungsmethoden oder BC Math Funktionen für Rechnungen mit beliebiger Genauigkeit, die nützlich sind für Szenarien, die mehr Kontrolle benötigen oder mit sehr großen Zahlen umgehen, wo die native Genauigkeit scheitern könnte.

## Siehe auch
Erforsche mehr im PHP-Handbuch:
- [PHP `round` Funktion](https://php.net/manual/de/function.round.php)
- [PHP `ceil` Funktion](https://php.net/manual/de/function.ceil.php)
- [PHP `floor` Funktion](https://php.net/manual/de/function.floor.php)
- [BC Math für Rechnungen mit beliebiger Genauigkeit](https://php.net/manual/de/book.bc.php)
