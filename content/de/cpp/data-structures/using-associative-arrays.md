---
changelog:
- 2024-01-30, gpt-4-0125-preview, translated from English
date: 2024-01-30 19:10:31.633648-07:00
description: "Assoziative Arrays, bekannt als `std::map` oder `std::unordered_map`\
  \ in C++, schlie\xDFen die L\xFCcke zwischen Array-Indizes und realen Daten, indem\
  \ sie es\u2026"
lastmod: '2024-03-13T22:44:54.177491-06:00'
model: gpt-4-0125-preview
summary: "Assoziative Arrays, bekannt als `std::map` oder `std::unordered_map` in\
  \ C++, schlie\xDFen die L\xFCcke zwischen Array-Indizes und realen Daten, indem\
  \ sie es Ihnen erm\xF6glichen, aussagekr\xE4ftige Schl\xFCssel zu verwenden."
title: Verwendung von assoziativen Arrays
weight: 15
---

## Wie geht das:
In C++ werden assoziative Arrays mit den Headern `<map>` und `<unordered_map>` lebensfähig. Lassen Sie uns anhand von Beispielen beide in Aktion sehen.

### Verwendung von `std::map`
`std::map` hält Elemente basierend auf dem Schlüssel sortiert. So fangen Sie an:

```C++
#include <iostream>
#include <map>
#include <string>

int main() {
    std::map<std::string, int> AltersMap;
    
    // Werte einfügen
    AltersMap["Alice"] = 30;
    AltersMap["Bob"] = 25;
    
    // Werte zugreifen
    std::cout << "Bobs Alter: " << AltersMap["Bob"] << std::endl;
    
    // Durch eine Map iterieren
    for(const auto &paar : AltersMap) {
        std::cout << paar.first << " ist " << paar.second << " Jahre alt." << std::endl;
    }
    
    return 0;
}
```

### Verwendung von `std::unordered_map`
Wenn die Reihenfolge keine Rolle spielt, aber die Leistung, ist `std::unordered_map` Ihr Freund und bietet eine schnellere durchschnittliche Komplexität für Einfügungen, Suchvorgänge und Löschungen.

```C++
#include <iostream>
#include <unordered_map>
#include <string>

int main() {
    std::unordered_map<std::string, double> ProduktPreis;
    
    // Werte einfügen
    ProduktPreis["Milch"] = 2.99;
    ProduktPreis["Brot"] = 1.99;
    
    // Werte zugreifen
    std::cout << "Milchpreis: $" << ProduktPreis["Milch"] << std::endl;
    
    // Durch eine unordered_map iterieren
    for(const auto &paar : ProduktPreis) {
        std::cout << paar.first << " kostet $" << paar.second << std::endl;
    }
    
    return 0;
}
```

## Tiefer eintauchen
Assoziative Arrays in C++, insbesondere `std::map` und `std::unordered_map`, gehen nicht nur um das Speichern von Elementen. Sie bieten eine Grundlage für komplexeres Datenmanagement, indem sie Operationen wie Suche, Einfügen und Entfernen in effizienten Zeitkomplexitäten ermöglichen (logarithmisch für `std::map` und durchschnittlich konstante Zeit für `std::unordered_map`). Diese Effizienz stammt von den zugrundeliegenden Datenstrukturen: einem ausbalancierten Baum für `std::map` und einer Hashtabelle für `std::unordered_map`.

Historisch gesehen, bevor diese Teil der Standardbibliothek waren, mussten Programmierer ihre eigenen Versionen implementieren oder auf Drittanbieter-Bibliotheken zurückgreifen, was zu Inkonsistenzen und potenziellen Ineffizienzen führte. Die Aufnahme von Maps in die Standardbibliothek von C++ hat nicht nur deren Einsatz standardisiert, sondern sie auch für unterschiedliche Compiler und Plattformen leistungsoptimiert.

Obwohl beide mächtig sind, hängt die Wahl zwischen einem `std::map` und einem `std::unordered_map` von den Besonderheiten Ihres Anwendungsfalls ab. Benötigen Sie geordnete Daten und macht Ihnen ein leichter Leistungsabfall nichts aus? Dann entscheiden Sie sich für `std::map`. Wenn Sie auf Geschwindigkeit aus sind und die Reihenfolge keine Rolle spielt, ist `std::unordered_map` wahrscheinlich die bessere Wahl.

Es ist jedoch wichtig zu beachten, dass bei der Arbeit mit komplexen Datenstrukturen immer Kompromisse eingegangen werden. In einigen Nischenfällen könnten andere Datenstrukturen oder sogar Drittanbieter-Bibliotheken eine bessere Leistung oder Funktionalität bieten, die besser auf Ihre speziellen Bedürfnisse zugeschnitten ist. Wägen Sie immer Ihre Optionen basierend auf den Anforderungen Ihres Projekts ab.
