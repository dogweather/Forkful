---
title:                "Mettre en majuscule une chaîne"
aliases:
- /fr/kotlin/capitalizing-a-string/
date:                  2024-02-03T19:05:38.354320-07:00
model:                 gpt-4-0125-preview
simple_title:         "Mettre en majuscule une chaîne"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/kotlin/capitalizing-a-string.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Quoi et pourquoi ?

En programmation, mettre en majuscule une chaîne de caractères consiste à convertir son premier caractère en majuscule s'il ne l'est pas déjà, ce qui est utile pour formater les entrées des utilisateurs ou afficher du texte dans une interface utilisateur de manière plus standardisée ou conviviale. Les programmeurs effectuent cette opération pour garantir la cohérence des données ou pour répondre à des exigences de formatage spécifiques au sein de leurs applications logicielles.

## Comment faire :

En Kotlin, les chaînes de caractères peuvent être mises en majuscules en utilisant les fonctions de la bibliothèque standard sans nécessiter de bibliothèques tierces. L'approche de Kotlin pour manipuler les chaînes rend ces opérations simples et concises.

### Mettre toute la chaîne en majuscules :

```kotlin
val message = "hello, world!"
val capitalizedMessage = message.uppercase()

println(capitalizedMessage) // Sortie : HELLO, WORLD!
```

### Mettre en majuscule uniquement le premier caractère :

Depuis Kotlin 1.5, la fonction `capitalize()` est obsolète et remplacée par une combinaison de `replaceFirstChar` et d'une lambda qui vérifie s'il s'agit d'une lettre minuscule pour la transformer en majuscule.

```kotlin
val greeting = "hello, world!"
val capitalizedGreeting = greeting.replaceFirstChar {
    if (it.isLowerCase()) it.titlecase() else it.toString()
}

println(capitalizedGreeting) // Sortie : Hello, world!
```

Cette approche maintient le reste de la phrase dans sa forme originale tout en changeant uniquement la première lettre en majuscule.
