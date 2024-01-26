---
title:                "Code in Funktionen organisieren"
date:                  2024-01-26T01:10:55.622364-07:00
model:                 gpt-4-1106-preview
simple_title:         "Code in Funktionen organisieren"
programming_language: "Javascript"
category:             "Javascript"
tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/javascript/organizing-code-into-functions.md"
---

{{< edit_this_page >}}

## Was & Warum?
Code in Funktionen zu organisieren unterteilt Aufgaben in wiederverwendbare Teile, macht den Code sauberer und leichter wartbar. Wir tun dies, um Redundanz zu reduzieren, das Testen zu erleichtern und die Lesbarkeit zu verbessern.

## Wie man es macht:

```javascript
// Definiere eine Funktion zur Berechnung der Fläche eines Rechtecks
function calculateArea(width, height) {
  return width * height;
}

// Rufe die Funktion auf und gebe das Ergebnis aus
let area = calculateArea(5, 3);
console.log(area); // Ausgabe: 15
```

```javascript
// Bündele verwandte Funktionalitäten mithilfe von Funktionen
function greet(name) {
  console.log(`Hallo, ${name}!`);
}

function farewell(name) {
  console.log(`Auf Wiedersehen, ${name}!`);
}

greet('Alice'); // Ausgabe: Hallo, Alice!
farewell('Bob'); // Ausgabe: Auf Wiedersehen, Bob!
```

## Tiefergehender Einblick
Historisch gesehen fehlte imperativen Programmiersprachen wie frühen Versionen von BASIC oder Assembly die Abstraktion, die Funktionen bieten. Im Laufe der Zeit führte das Konzept des modularen Codes in Sprachen wie C zu der Idee, dass das Unterteilen von Code in Einheiten (Funktionen oder Prozeduren) zu einer besseren Organisation und klareren Logik führt.

In JavaScript haben wir neben einfachen Funktionen seit ES6 (2015) auch Pfeilfunktionen, die eine prägnantere Syntax bieten und sich gut für nicht-methodische Funktionen eignen.

Alternativen und Erweiterungen bei der Organisation von Code in JavaScript umfassen objektorientierte Ansätze mit Klassen oder funktionale Programmierparadigmen, die Funktionen als First-Class-Citizens behandeln.

In Bezug auf die Implementierung unterstützen JavaScript-Funktionen Closures, die einen Weg bieten, den Zugang zum Scope einer Funktion nach deren Ausführung zu behalten, was für die Kapselung und das Erstellen von Fabrikfunktionen unter anderem Muster leistungsstark ist.

## Siehe auch
- MDN Web Docs zu Funktionen: https://developer.mozilla.org/de/docs/Web/JavaScript/Guide/Functions
- JavaScript Design Patterns: https://addyosmani.com/resources/essentialjsdesignpatterns/book/
- Clean Code JavaScript: https://github.com/ryanmcdermott/clean-code-javascript