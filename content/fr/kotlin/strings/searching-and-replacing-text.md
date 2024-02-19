---
aliases:
- /fr/kotlin/searching-and-replacing-text/
date: 2024-01-20 17:58:10.587492-07:00
description: "Chercher et remplacer du texte, c'est un peu comme jouer \xE0 cache-cache\
  \ dans une for\xEAt de mots pour d\xE9nicher une phrase et la transformer en quelque\
  \ chose\u2026"
lastmod: 2024-02-18 23:09:08.764577
model: gpt-4-1106-preview
summary: "Chercher et remplacer du texte, c'est un peu comme jouer \xE0 cache-cache\
  \ dans une for\xEAt de mots pour d\xE9nicher une phrase et la transformer en quelque\
  \ chose\u2026"
title: Recherche et remplacement de texte
---

{{< edit_this_page >}}

## What & Why?
Chercher et remplacer du texte, c'est un peu comme jouer à cache-cache dans une forêt de mots pour dénicher une phrase et la transformer en quelque chose de nouveau. Les programmeurs font ça pour corriger des fautes, mettre à jour des données ou automatiser l'édition de code.

## How to:
En Kotlin, on va droit au but. Pour chercher et remplacer, on utilise souvent `replace()`:

```kotlin
fun main() {
    val texte = "Bonjour le monde!"
    val texteRemplace = texte.replace("Bonjour", "Salut")
    println(texteRemplace) // Affiche : Salut le monde!
}
```

Testons avec les expressions régulières :

```kotlin
fun main() {
    val texte = "Les Kotliners sont ici! Et les Kotliners programment en Kotlin."
    val regex = Regex("Kotliners")
    val resultat = texte.replace(regex, "Développeurs")
    println(resultat) // Affiche : Les Développeurs sont ici! Et les Développeurs programment en Kotlin.
}
```

Facile, rapide, efficace.

## Deep Dive
Historiquement, chercher et remplacer existait bien avant Kotlin – pensons à `sed` en Unix. Kotlin rend ça plus agréable grâce à sa syntaxe concise et claire.

Alternatives ? On pourrait utiliser les `Pattern` et `Matcher` de Java, mais c'est plus bavard. Avec Kotlin, `replace()` et les expressions régulières (Regex) font le job proprement.

Pour les détails d'implémentation, sachez que sous le capot, `replace()` travaille avec la classe `StringBuilder` pour la modification des chaînes, ce qui est assez efficace.

## See Also
- Official Guide on Regular Expressions in Kotlin: [https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.text/-regex/](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.text/-regex/)
