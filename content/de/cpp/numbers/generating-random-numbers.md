---
date: 2024-01-27 20:33:01.243415-07:00
description: "Das Generieren von Zufallszahlen in der Programmierung beinhaltet das\
  \ Erstellen von Zahlenfolgen, die keine vorhersehbare Ordnung oder Muster aufweisen.\u2026"
lastmod: '2024-03-13T22:44:54.180655-06:00'
model: gpt-4-0125-preview
summary: Das Generieren von Zufallszahlen in der Programmierung beinhaltet das Erstellen
  von Zahlenfolgen, die keine vorhersehbare Ordnung oder Muster aufweisen.
title: Generierung von Zufallszahlen
weight: 12
---

## Wie geht das:
Um Zufallszahlen in C++ zu generieren, verwendet man typischerweise den `<random>`-Header, der in C++11 eingeführt wurde und eine breite Palette von Möglichkeiten bietet, Zufallszahlen aus verschiedenen Verteilungen zu generieren.

```C++
#include <iostream>
#include <random>

int main() {
    // Initialisiere eine Zufalls-Engine
    std::random_device rd;  
    std::mt19937 gen(rd()); 

    // Definiere den Bereich [0, 99] inklusive
    std::uniform_int_distribution<> distrib(0, 99); 

    // Generiere und drucke 5 Zufallszahlen innerhalb des definierten Bereichs
    for(int n=0; n<5; ++n)
        std::cout << distrib(gen) << ' ';
    return 0;
}
```

Dieses Code-Beispiel initialisiert einen Mersenne Twister Zufallszahlengenerator mit einem Seed von `std::random_device`. Anschließend wird eine gleichmäßige Integer-Verteilung im Bereich [0, 99] definiert und schließlich werden 5 Zufallszahlen aus dieser Verteilung ausgegeben.

Die Ausgabe könnte so aussehen, aber beachten Sie, dass jede Ausführung wahrscheinlich unterschiedliche Ergebnisse liefert:

```
45 67 32 23 88
```

## Tieferer Einblick:
Historisch gesehen, beruhte die Generierung von Zufallszahlen in C++ stark auf der `rand()`-Funktion und der `srand()`-Funktion für die Seedung, die im `<cstdlib>`-Header zu finden sind. Allerdings wurde dieser Ansatz oft für seine mangelnde Gleichmäßigkeit und Vorhersagbarkeit in der Verteilung der generierten Zahlen kritisiert.

Die Einführung des `<random>`-Headers in C++11 markierte eine deutliche Verbesserung und bot ein ausgefeiltes System zur Erzeugung von Zufallszahlen. Die bereitgestellten Mittel umfassen eine Vielzahl von Motoren (wie `std::mt19937` für Mersenne Twister) und Verteilungen (wie `std::uniform_int_distribution` für die gleichmäßige Verteilung von Ganzzahlen), die kombiniert werden können, um den spezifischen Bedürfnissen des Programmierers zu entsprechen und führen zu vorhersehbarerem Verhalten, besserer Leistung und größerer Flexibilität.

Während die `<random>`-Bibliothek viel besser ist als der ältere `rand()`-Ansatz, ist es erwähnenswert, dass das Generieren von wahrhaft zufälligen Zahlen - insbesondere für kryptografische Zwecke - noch weitere Überlegungen erfordert. Für kryptografische Anwendungen sollten stattdessen speziell für die Sicherheit entworfene Bibliotheken verwendet werden, die oft Hardware-Entropiequellen nutzen.
