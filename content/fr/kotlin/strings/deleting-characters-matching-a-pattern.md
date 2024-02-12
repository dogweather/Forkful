---
title:                "Suppression de caractères correspondant à un motif"
aliases:
- /fr/kotlin/deleting-characters-matching-a-pattern/
date:                  2024-01-20T17:42:41.113175-07:00
model:                 gpt-4-1106-preview
simple_title:         "Suppression de caractères correspondant à un motif"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/kotlin/deleting-characters-matching-a-pattern.md"
---

{{< edit_this_page >}}

## What & Why?
Supprimer des caractères correspondant à un motif, c'est filtrer une chaîne de texte en enlevant des éléments précis. Les développeurs font ça pour nettoyer des données, valider des entrées ou simplifier le traitement de texte.

## How to:
En Kotlin, vous pouvez utiliser la méthode `replace()` avec une expression régulière pour supprimer les caractères indésirables. Voici comment :

```kotlin
fun main() {
    val originalText = "Bonjour, comment ça va? 123!"
    val pattern = "[0-9]".toRegex() // On suppose qu'on veut supprimer tous les chiffres
    
    val cleanedText = originalText.replace(pattern, "")
    println(cleanedText) // Affiche : Bonjour, comment ça va? !
}
```

Et si vous voulez supprimer plusieurs motifs :

```kotlin
fun main() {
    val originalText = "Email : contact@example.com, Tél : 123-456-7890"
    val pattern = "[0-9@.-]".toRegex()
    
    val cleanedText = originalText.replace(pattern, "")
    println(cleanedText) // Affiche : Email : contactexamplecom, Tél : 
}
```

## Deep Dive:
Historiquement, les expressions régulières sont utilisées depuis les années 1950, alors que l'édition de texte était très primaire. En Kotlin, utiliser `replace()` avec Regex est la solution moderne pour manipuler les chaînes, mais vous pourriez également traverser et manipuler manuellement la chaîne si le contexte l'exige, bien que cela soit souvent moins efficace.

Les alternatives incluent l'utilisation de méthodes comme `filter` pour les cas plus simples :

```kotlin
fun main() {
    val originalText = "Ceci est 1 exemple!"
    val cleanedText = originalText.filter { it.isLetter() || it.isWhitespace() }
    println(cleanedText) // Affiche : Ceci est exemple
}
```

Concernant l'implémentation, quand vous créez une expression régulière en Kotlin avec `toRegex()`, vous avez la possibilité d'utiliser des drapeaux (flags) pour changer le comportement de l'analyse, comme ignorer la casse.

## See Also:
- Documentation Kotlin sur les expressions régulières: [Kotlin Regex](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.text/-regex/)
- Un guide sur les expressions régulières en général: [Regular Expressions Info](https://www.regular-expressions.info)
- Projet Kotlin GitHub pour explorer le code source: [Kotlin GitHub Repository](https://github.com/JetBrains/kotlin)
