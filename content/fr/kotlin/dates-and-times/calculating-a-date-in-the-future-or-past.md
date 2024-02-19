---
aliases:
- /fr/kotlin/calculating-a-date-in-the-future-or-past/
date: 2024-01-20 17:31:43.646671-07:00
description: "Calculer une date dans le futur ou le pass\xE9, c'est intentionnellement\
  \ ajuster la date et l'heure actuelles pour obtenir un moment pr\xE9cis. Les programmeurs\u2026"
lastmod: 2024-02-18 23:09:08.795638
model: gpt-4-1106-preview
summary: "Calculer une date dans le futur ou le pass\xE9, c'est intentionnellement\
  \ ajuster la date et l'heure actuelles pour obtenir un moment pr\xE9cis. Les programmeurs\u2026"
title: "Calcul d'une date future ou pass\xE9e"
---

{{< edit_this_page >}}

## What & Why? (Quoi et Pourquoi ?)

Calculer une date dans le futur ou le passé, c'est intentionnellement ajuster la date et l'heure actuelles pour obtenir un moment précis. Les programmeurs le font pour des rappels, des abonnements, des échéances et pour gérer les évènements programmés.

## How to: (Comment faire :)

Kotlin rend ce calcul super simple avec `LocalDateTime` et `Duration` de la bibliothèque `java.time`. Voici comment :

```kotlin
import java.time.LocalDateTime
import java.time.temporal.ChronoUnit

fun main() {
    val now = LocalDateTime.now()
    println("Now: $now")

    // Ajouter 10 jours
    val tenDaysLater = now.plusDays(10)
    println("10 days later: $tenDaysLater")

    // Retirer 3 semaines
    val threeWeeksEarlier = now.minusWeeks(3)
    println("3 weeks earlier: $threeWeeksEarlier")

    // Calculer une date précise dans le futur, par exemple 2 ans, 1 mois et 5 jours plus tard
    val specificFutureDate = now.plusYears(2).plusMonths(1).plusDays(5)
    println("Specific future date: $specificFutureDate")

    // Utiliser ChronoUnit pour ajouter des heures
    val inFiveHours = now.plus(5, ChronoUnit.HOURS)
    println("In five hours: $inFiveHours")
}
```

Sample output:

```
Now: 2023-04-12T15:37:52.042
10 days later: 2023-04-22T15:37:52.042
3 weeks earlier: 2023-03-22T15:37:52.042
Specific future date: 2025-05-17T15:37:52.042
In five hours: 2023-04-12T20:37:52.042
```

## Deep Dive (Plongée Profonde)

Avant `java.time`, Java utilisait `Date` et `Calendar` qui étaient difficiles à comprendre et à utiliser. `java.time` est plus intutitif et puissant. Cela fait partie de Joda-Time, une bibliothèque externe, qui a inspiré sa création.

En Kotlin, on pourrait aussi utiliser Anko, une bibliothèque qui étend les capacités d'Android, ou des fonctions d'extension pour rendre le code encore plus lisible.

Pour la performance et l'immuabilité, `LocalDateTime` est génial, car les instances sont immuables : lorsqu'on ajuste la date/heure, une nouvelle instance est créée.

## See Also (Voir Aussi)

- [Oracle java.time tutorial](https://docs.oracle.com/javase/tutorial/datetime/)
- [Joda-Time Library](https://www.joda.org/joda-time/)
- [Anko Library for Android](https://github.com/Kotlin/anko)
