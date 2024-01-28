---
title:                "Nutzung einer interaktiven Shell (REPL)"
date:                  2024-01-26T04:12:02.092219-07:00
model:                 gpt-4-0125-preview
simple_title:         "Nutzung einer interaktiven Shell (REPL)"
programming_language: "C++"
category:             "C++"
tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/cpp/using-an-interactive-shell-repl.md"
---

{{< edit_this_page >}}

## Was & Warum?
Ein REPL (Read-Eval-Print-Loop) ist eine einfache, interaktive Programmierumgebung. Programmierer nutzen es für Echtzeit-Sprachexperimente, schnelle Aufgaben oder um neue Konzepte ohne den Overhead der Erstellung von vollwertigen Anwendungen zu verstehen.

## Wie:
C++ verfügt nicht über eine integrierte REPL, aber Werkzeuge wie Cling bieten diese Möglichkeit. So verwenden Sie Cling, um die Summe zweier Zahlen zu berechnen:

```C++
#include <iostream>

int main() {
    int a = 5;
    int b = 7;
    std::cout << "Die Summe ist: " << a + b << std::endl;
    return 0;
}

// Ausgabe:
// Die Summe ist: 12
```

Starten Sie Cling und geben Sie den Code Zeile für Zeile ein, wobei Sie die Ausgabe nach jedem Befehl beobachten. Es ist ein sofortiges Feedback, ohne Kompilierung.

## Tiefergehend
REPLs sind üblich für Sprachen wie Python oder Lisp und existieren seit den 1960er Jahren. Für C++, eine kompilierte Sprache, passt das Konzept nicht so natürlich, weshalb Werkzeuge wie Cling existieren - sie interpretieren C++ on the fly. Alternativen umfassen Online-Compiler oder kleinskalige Testprogramme, die traditionell kompiliert werden. Cling basiert auf LLVM und Clang und bietet eine Brücke, damit C++ auf interpretierte Weise verwendet werden kann.

## Siehe auch
- [Cling](https://root.cern/cling/): Ein interaktiver C++-Interpreter, aufgebaut auf den LLVM- und Clang-Bibliotheken.
- [Jupyter Notebooks](https://jupyter.org/): Bietet eine interaktive Shell innerhalb einer Notizbuchumgebung, unterstützt C++ durch den xeus-cling-Kernel.
- [LLVM](https://llvm.org/): Eine Sammlung von modularen und wiederverwendbaren Compiler- und Werkzeugkettentechnologien, auf denen Cling aufbaut.
