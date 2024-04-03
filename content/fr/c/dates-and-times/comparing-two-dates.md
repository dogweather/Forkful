---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 17:53:35.687116-07:00
description: "Comparer deux dates en C implique de d\xE9terminer la relation chronologique\
  \ entre elles - si une date pr\xE9c\xE8de l'autre ou si elles sont identiques. Cette\u2026"
lastmod: '2024-03-13T22:44:58.385917-06:00'
model: gpt-4-0125-preview
summary: "Comparer deux dates en C implique de d\xE9terminer la relation chronologique\
  \ entre elles - si une date pr\xE9c\xE8de l'autre ou si elles sont identiques."
title: Comparer deux dates
weight: 27
---

## Comment faire :
C n'a pas de type intégré pour les dates, nécessitant l'utilisation de la bibliothèque `time.h` pour travailler avec les structures de date et de temps. La structure `tm` et la fonction `difftime()` sont couramment utilisées pour comparer les dates. Voici un exemple montrant comment comparer deux dates :

```c
#include <stdio.h>
#include <time.h>

int main() {
    struct tm date1 = {0};
    struct tm date2 = {0};
    double secondes;

    // Première date (AAAA, MM, JJ)
    date1.tm_year = 2023 - 1900; // Année depuis 1900
    date1.tm_mon = 3 - 1;        // Mois [0-11]
    date1.tm_mday = 15;          // Jour du mois [1-31]

    // Deuxième date (AAAA, MM, JJ)
    date2.tm_year = 2023 - 1900;
    date2.tm_mon = 4 - 1;
    date2.tm_mday = 14;

    // Convertir en format time_t
    time_t time1 = mktime(&date1);
    time_t time2 = mktime(&date2);

    // Comparer
    secondes = difftime(time1, time2);

    if (secondes == 0) {
        printf("Les dates sont identiques.\n");
    } else if (secondes > 0) {
        printf("La première date vient après la seconde.\n");
    } else {
        printf("La première date vient avant la seconde.\n");
    }

    return 0;
}
```

La sortie pourrait être :

```text
La première date vient avant la seconde.
```

Ce programme initialise deux structures `tm` avec des dates spécifiques, les convertit au format `time_t` à l'aide de `mktime()`, et les compare enfin à l'aide de `difftime()`, qui retourne la différence en secondes (sous forme de `double`) entre les deux temps.

## Plongée Profonde
Dans les premiers jours du C, les opérations de date et de temps nécessitaient des calculs manuels, tenant souvent compte des années bissextiles, du nombre variable de jours dans les mois, et même des secondes intercalaires. L'introduction de `time.h` dans la norme ANSI C a apporté une standardisation à la gestion du temps en C, simplifiant les opérations de date et de temps.

Utiliser `time.h` pour la comparaison de dates est simple mais comporte des limitations. La structure `tm` ne tient pas compte des fuseaux horaires ou de l'heure d'été, et `difftime()` ne fournit que la différence en secondes, manquant de granularité plus fine pour certaines applications.

Pour les applications nécessitant des opérations de date-heure plus robustes, y compris le support pour les fuseaux horaires, les transitions de l'heure d'été, et des intervalles de temps plus précis, des bibliothèques telles que `date.h` (une bibliothèque de date Howard Hinnant, non incluse dans la bibliothèque standard) offrent une alternative moderne à `time.h`. Ces bibliothèques fournissent des outils plus complets pour la manipulation de date-heure en C++, bénéficiant de décennies d'évolution dans la conception des langages de programmation. Pour les programmeurs en C, l'utilisation de ces bibliothèques externes ou la gestion méticuleuse des subtilités des calculs de date-heure directement reste nécessaire pour atteindre une manipulation précise et culturellement consciente de la date-heure.
