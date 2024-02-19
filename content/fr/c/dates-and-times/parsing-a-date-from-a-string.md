---
aliases:
- /fr/c/parsing-a-date-from-a-string/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 17:59:56.696295-07:00
description: "Analyser une date \xE0 partir d'une cha\xEEne en C implique de convertir\
  \ des repr\xE9sentations textuelles de dates en un format que les programmes peuvent\u2026"
lastmod: 2024-02-18 23:09:09.367177
model: gpt-4-0125-preview
summary: "Analyser une date \xE0 partir d'une cha\xEEne en C implique de convertir\
  \ des repr\xE9sentations textuelles de dates en un format que les programmes peuvent\u2026"
title: "Analyser une date \xE0 partir d'une cha\xEEne de caract\xE8res"
---

{{< edit_this_page >}}

## Quoi & Pourquoi ?

Analyser une date à partir d'une chaîne en C implique de convertir des représentations textuelles de dates en un format que les programmes peuvent manipuler et analyser plus efficacement. Cela est crucial pour des tâches telles que l'arithmétique des dates, les comparaisons et le formatage pour différents locales, car cela permet aux programmeurs de gérer l'entrée des utilisateurs ou les entrées de jeu de données de manière standardisée.

## Comment faire :

C ne fournit pas de moyen intégré pour analyser les dates à partir de chaînes directement, nous avons donc souvent recours à la fonction `strptime` disponible dans la bibliothèque `<time.h>` pour les systèmes POSIX. Cette fonction nous permet de spécifier le format attendu de la chaîne d'entrée et de l'analyser dans une `struct tm`, qui représente la date et l'heure du calendrier décomposées en ses composants.

Voici un exemple simple de comment utiliser `strptime` pour analyser une date à partir d'une chaîne :

```c
#include <time.h>
#include <stdio.h>

int main() {
    const char *dateStr = "2023-04-01";
    struct tm tm;
    char buf[255];

    // Analyser la chaîne de date dans struct tm
    if (strptime(dateStr, "%Y-%m-%d", &tm) == NULL) {
        printf("Échec de l'analyse de la date.\n");
    } else {
        // Utiliser strftime pour imprimer la date dans un format lisible
        strftime(buf, sizeof(buf), "%A, %B %d, %Y", &tm);
        printf("Date analysée : %s\n", buf);
    }

    return 0;
}
```

La sortie d'échantillon pour ce programme serait :

```
Date analysée : samedi, avril 01, 2023
```

Il est essentiel de gérer les erreurs potentielles, telles que `strptime` ne parvenant pas à correspondre au modèle ou rencontrant une entrée inattendue.

## Approfondissement

La fonction `strptime`, bien qu'elle soit puissante, ne fait pas partie de la bibliothèque standard C et se trouve principalement sur des systèmes conformes à POSIX tels que Linux et UNIX. Cette limitation signifie que les programmes qui comptent sur `strptime` pour analyser des dates à partir de chaînes peuvent ne pas être portables sur des systèmes non-POSIX comme Windows sans couches de compatibilité supplémentaires ou des bibliothèques.

Historiquement, la gestion des dates et des heures en C nécessitait beaucoup de manipulations manuelles et de soins, surtout en considérant les différents locales et fuseaux horaires. Des alternatives modernes et des extensions à C, telles que la bibliothèque `<chrono>` de C++ et des bibliothèques tierces comme la bibliothèque de dates de Howard Hinnant pour C++, offrent des solutions plus robustes pour la manipulation des dates et heures, incluant l'analyse. Ces bibliothèques fournissent généralement un meilleur soutien pour une gamme plus large de formats de date, de fuseaux horaires et de mécanismes de gestion des erreurs, les rendant préférables pour de nouveaux projets nécessitant des capacités de manipulation de date et d'heure étendues.

Néanmoins, comprendre comment analyser des dates à partir de chaînes en C peut être bénéfique, en particulier lorsqu'on travaille sur ou maintient des projets qui doivent être compatibles avec des systèmes où ces outils modernes ne sont pas disponibles ou lorsque l'on travaille dans les contraintes d'environnements de programmation C stricts.
