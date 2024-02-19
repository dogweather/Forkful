---
aliases:
- /de/cpp/printing-debug-output/
date: 2024-01-20 17:52:08.685338-07:00
description: "Debug-Ausgaben zu drucken, hei\xDFt, Informationen zur Laufzeit auszugeben,\
  \ um Fehler zu finden oder Programmabl\xE4ufe zu verstehen. Es ist wie das Schummeln\u2026"
lastmod: 2024-02-18 23:09:05.191697
model: gpt-4-1106-preview
summary: "Debug-Ausgaben zu drucken, hei\xDFt, Informationen zur Laufzeit auszugeben,\
  \ um Fehler zu finden oder Programmabl\xE4ufe zu verstehen. Es ist wie das Schummeln\u2026"
title: Debug-Ausgaben drucken
---

{{< edit_this_page >}}

## Was & Warum?
Debug-Ausgaben zu drucken, heißt, Informationen zur Laufzeit auszugeben, um Fehler zu finden oder Programmabläufe zu verstehen. Es ist wie das Schummeln bei einer Puzzlesuche: Man bekommt Hinweise, wo die Teile hingehören.

## So geht's:
``` C++
#include <iostream>

int main() {
    // Variable zum Demonstrieren der Debug-Ausgabe
    int bedeutendeVariable = 42;

    // Debug-Ausgabe auf der Konsole
    std::cout << "Debug: bedeutendeVariable hat den Wert " << bedeutendeVariable << std::endl;

    // Weitere Logik hier…
    // ...

    return 0;
}
```
Erwartete Ausgabe:
```
Debug: bedeutendeVariable hat den Wert 42
```

## Deep Dive:
Früher nutzten Programmierer einfache `printf()`-Befehle für Debug-Meldungen. Mit der Einführung von C++ Streams wurde `std::cout` zum Standard für Ausgaben. Alternativ kann man `std::cerr` nutzen, um Fehlermeldungen auf dem Standardfehlerausgabe-Stream zu drucken. Die Implementierung ist einfach: Es reicht, geeignete Nachrichten an den gewünschten Stream zu senden. Allerdings sollte man diese Ausgaben vor der Veröffentlichung entfernen oder durch ein professionelles Logging-Framework ersetzen.

## Siehe Auch:
- CPP Reference zur I/O-Bibliothek: 
https://en.cppreference.com/w/cpp/header/iostream
- Guidelines für effektives Logging: 
https://www.vogella.com/tutorials/Logging/article.html
- Unterschied zwischen `std::cout` und `std::cerr`:
https://stackoverflow.com/questions/213907/c-stdendl-vs-n
