---
title:                "Generierung von Zufallszahlen"
date:                  2024-01-27T20:34:39.636542-07:00
model:                 gpt-4-0125-preview
simple_title:         "Generierung von Zufallszahlen"

tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/php/generating-random-numbers.md"
---

{{< edit_this_page >}}

## Was & Warum?

Das Generieren von Zufallszahlen in PHP bedeutet, unvorhersehbare Werte innerhalb eines festgelegten Bereichs zu erzeugen, was für Aufgaben wie das Erstellen einzigartiger Benutzer-IDs, das Generieren von Passwörtern oder für den Einsatz in Simulationen und Spielen wesentlich ist. Programmierer verlassen sich auf Zufälligkeit, um Unvorhersehbarkeit und Variabilität in ihre Anwendungen zu bringen, was Prozesse wie Tests oder Benutzererfahrungen robuster und ansprechender macht.

## Wie:

PHP bietet mehrere Funktionen zum Generieren von Zufallszahlen, aber die am häufigsten verwendeten sind `rand()`, `mt_rand()` und für kryptografische Zwecke `random_int()`.

Um eine einfache Zufallszahl zwischen 0 und getrandmax() (dem größtmöglichen von `rand()` zurückgegebenen Wert) zu generieren, können Sie verwenden:

```PHP
echo rand();
```

Für einen spezifischeren Bereich, wie zwischen 1 und 100:

```PHP
echo rand(1, 100);
```

Jedoch ist `mt_rand()` eine bessere Wahl für Geschwindigkeit und Zufälligkeit:

```PHP
echo mt_rand(1, 100);
```

Die Ausgabe für beide könnte irgendetwas zwischen 1 und 100 sein, abhängig von der Zufälligkeit, z. B. `42`.

Für kryptografische oder Sicherheitskontexte, wo die Unvorhersehbarkeit entscheidend ist, ist `random_int()` die bevorzugte Wahl, da es kryptografisch sichere pseudo-zufällige Ganzzahlen generiert:

```PHP
echo random_int(1, 100);
```

Auch hier ist die Ausgabe eine zufällige Zahl zwischen 1 und 100, wie `84`, aber mit einer stärkeren Garantie für Zufälligkeit.

## Vertiefung

Die Funktion `rand()` ist seit den frühen Versionen von PHP vorhanden und diente als der ursprüngliche Ansatz zur Generierung von Zufallszahlen. Sie ist jedoch nicht die beste Wahl für Anwendungen, die einen hohen Grad an Zufälligkeit erfordern, aufgrund ihres relativ vorhersehbaren Algorithmus.

`mt_rand()`, eingeführt in PHP 4, basiert auf dem Mersenne-Twister-Algorithmus - weitaus überlegen in Bezug auf Geschwindigkeit und die Zufälligkeit, die es im Vergleich zu `rand()` generieren kann. Es wurde schnell zur bevorzugten Option für die meisten nicht-kryptografischen Bedürfnisse.

Für sicherheitssensible Anwendungen wurde `random_int()` in PHP 7 eingeführt, um kryptografisch sichere pseudo-zufällige Ganzzahlen zu generieren, indem es zufällige Bytes aus dem Zufallszahlengenerator des Systems verwendet. Es ist deutlich sicherer als `rand()` oder `mt_rand()`, was es zur besten Wahl für die Generierung von Token, Schlüsseln oder anderen Elementen macht, bei denen Vorhersehbarkeit zu Sicherheitsanfälligkeiten führen könnte.

Trotz dieser Verbesserungen ist es entscheidend, die richtige Funktion basierend auf dem Kontext der Anwendung zu wählen. Für den allgemeinen Gebrauch reicht `mt_rand()` aus, aber für alles, was angegriffen oder ausgenutzt werden könnte, ist `random_int()` der richtige Weg, da es sowohl Zufälligkeit als auch Sicherheit bietet.
