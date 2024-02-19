---
aliases:
- /fr/cpp/comparing-two-dates/
date: 2024-01-20 17:32:37.045179-07:00
description: "Comparer deux dates, c'est v\xE9rifier laquelle vient avant ou apr\xE8\
  s l'autre, ou si elles sont identiques. Les programmeurs font cela pour trier des\u2026"
lastmod: 2024-02-18 23:09:09.174532
model: gpt-4-1106-preview
summary: "Comparer deux dates, c'est v\xE9rifier laquelle vient avant ou apr\xE8s\
  \ l'autre, ou si elles sont identiques. Les programmeurs font cela pour trier des\u2026"
title: Comparer deux dates
---

{{< edit_this_page >}}

## What & Why (Quoi et Pourquoi) ?
Comparer deux dates, c'est vérifier laquelle vient avant ou après l'autre, ou si elles sont identiques. Les programmeurs font cela pour trier des évènements, valider des périodes ou gérer des réservations.

## How to (Comment faire) :
```C++
#include <iostream>
#include <chrono>

int main() {
    // On crée deux dates en utilisant std::chrono
    std::chrono::system_clock::time_point date1 = std::chrono::system_clock::now();
    std::chrono::system_clock::time_point date2 = date1 + std::chrono::hours(24); // Ajoute 24 heures à la date1

    // On compare les dates
    if (date1 < date2) {
        std::cout << "date1 est plus tôt que date2" << std::endl;
    } else if (date1 > date2) {
        std::cout << "date1 est plus tard que date2" << std::endl;
    } else {
        std::cout << "date1 est la même que date2" << std::endl;
    }

    return 0;
}
```
Sortie attendue : `date1 est plus tôt que date2`

## Deep Dive (Plongée en profondeur) :
Historiquement, comparer des dates en C++ était compliqué avant l'introduction de `<chrono>` en C++11. On utilisait `<ctime>` qui est moins type-safe et un peu rustique. `<chrono>` offre une précision et une facilité accrues grâce à des types comme `time_point` et `duration`.

Il existe des alternatives, comme des bibliothèques tierces (par exemple, Boost.DateTime), mais `<chrono>` est suffisant pour la plupart des besoins et c'est standard en C++ depuis 2011.

L'implémentation dépend du système d'exploitation et du matériel, mais généralement, elle mesure le temps en ticks depuis un point (comme l'Epoch UNIX). Les comparaisons se font en vérifiant simplement ces ticks.

## See Also (Voir aussi) :
- [cppreference.com: Chrono library overview](https://en.cppreference.com/w/cpp/chrono)
- [cplusplus.com: Date and Time utilities](http://www.cplusplus.com/reference/ctime/)
- [Boost.DateTime documentation](https://www.boost.org/doc/libs/1_75_0/doc/html/date_time.html)
