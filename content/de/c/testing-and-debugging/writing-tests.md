---
title:                "Tests schreiben"
aliases:
- /de/c/writing-tests/
date:                  2024-02-03T18:14:31.931127-07:00
model:                 gpt-4-0125-preview
simple_title:         "Tests schreiben"
tag:                  "Testing and Debugging"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/c/writing-tests.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Was & Warum?
Tests in C zu schreiben, bedeutet, kleinere Hilfsprogramme oder Funktionen zu erstellen, die automatisch die Funktionalität Ihres Codes überprüfen. Programmierer tun dies, um sicherzustellen, dass ihre Software wie erwartet funktioniert, um Fehler frühzeitig zu erkennen und um zukünftige Code-Modifikationen ohne unerwünschte Nebenwirkungen zu erleichtern.

## Wie:
Obwohl C nicht über ein integriertes Test-Framework wie einige andere Sprachen verfügt, können Sie dennoch effektive Tests schreiben, indem Sie assert.h für einfache Behauptungen verwenden oder Drittanbieter-Frameworks wie CUnit oder Unity für strukturiertere Tests integrieren. Hier ist ein grundlegendes Beispiel mit assert.h, um eine Funktion zu testen, die zwei Ganzzahlen addiert:

```c
#include <assert.h>
#include "meine_mathematik.h"

void test_addition() {
    assert(add(1, 2) == 3);
    assert(add(-1, -2) == -3);
    assert(add(0, 0) == 0);
    printf("Alle Additionstests bestanden.\n");
}

int main() {
    test_addition();
    return 0;
}
```

In `meine_mathematik.h` könnten Sie haben:

```c
// Einfache Additionsfunktion
int add(int a, int b) {
    return a + b;
}
```

Das Ausführen der Testfunktion in Ihrer `main`-Funktion gibt aus:

```
Alle Additionstests bestanden.
```

Für eine umfassendere Testeinrichtung mit einem Framework wie Unity würden Sie das Framework in Ihr Projekt integrieren und dann ähnlich Testfälle schreiben, jedoch unter Nutzung der Framework-API für Behauptungen und Testdurchführungen.

## Tiefergehende Betrachtung
Das Testen in C war historisch gesehen ein manueller und etwas ad hoc Prozess aufgrund der Low-Level-Natur der Sprache und des Fehlens eines standardisierten Test-Frameworks. Dieser manuelle Ansatz führte oft zu weniger gründlichen Testpraktiken im Vergleich zu Sprachen mit integrierter Testunterstützung. Da die C-Sprache entscheidend für die Entwicklung grundlegender Softwaresysteme war, führte dieser Mangel an formellen Testframeworks dazu, dass die C-Gemeinschaft Drittanbieter-Lösungen wie CUnit und Unity entwickelte.

Diese Werkzeuge, obwohl extern zur standardmäßigen C-Bibliothek, bieten Funktionalitäten ähnlich den Test-Frameworks in anderen Sprachen, und bieten eine strukturierte Möglichkeit, Tests zu definieren, durchzuführen und zu bewerten. Sie helfen, die Lücke zwischen dem leistungsstarken Systemzugang von C und der modernen Entwicklungspraxis des automatisierten Tests zu schließen. Es ist erwähnenswert, dass, obwohl diese Werkzeuge den Testprozess in C erheblich verbessern, sie eine Lernkurve mit sich bringen und die Komplexität der Projekteinrichtung im Vergleich zu Sprachen mit integrierter Testunterstützung erhöhen können. Daher ist für Projekte, bei denen Zuverlässigkeit und Wartbarkeit von größter Bedeutung sind, die Investition in die Einrichtung einer angemessenen Testumgebung in C gut gerechtfertigt, selbst angesichts möglicher Alternativen.
