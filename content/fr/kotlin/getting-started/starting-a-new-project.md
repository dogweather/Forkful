---
aliases:
- /fr/kotlin/starting-a-new-project/
date: 2024-01-20 18:04:00.609836-07:00
description: "D\xE9marrer un nouveau projet, c'est mettre la premi\xE8re pierre \xE0\
  \ votre \xE9difice num\xE9rique. Les programmeurs le font pour concr\xE9tiser une\
  \ id\xE9e, apprendre une\u2026"
lastmod: 2024-02-18 23:09:08.781592
model: gpt-4-1106-preview
summary: "D\xE9marrer un nouveau projet, c'est mettre la premi\xE8re pierre \xE0 votre\
  \ \xE9difice num\xE9rique. Les programmeurs le font pour concr\xE9tiser une id\xE9\
  e, apprendre une\u2026"
title: Lancement d'un nouveau projet
---

{{< edit_this_page >}}

## Quoi et pourquoi ?
Démarrer un nouveau projet, c'est mettre la première pierre à votre édifice numérique. Les programmeurs le font pour concrétiser une idée, apprendre une technologie ou simplement pour le plaisir de créer quelque chose de neuf.

## Comment faire :
Pour lancer un nouveau projet Kotlin, suivez ces étapes :

Installez IntelliJ IDEA, un environnement de développement intégré (IDE) populaire pour Kotlin. Téléchargez-le depuis : https://www.jetbrains.com/idea/download/

Ouvrez IntelliJ IDEA, sélectionnez “Create New Project”, choisissez Kotlin dans la liste des langages et optez pour un projet Gradle ou Maven, selon votre préférence.

Nommez votre projet et choisissez un emplacement pour le sauvegarder.

Une fois le projet créé, IntelliJ va configurer l'environnement et vous pouvez créer un nouveau fichier Kotlin, `main.kt`, avec le code suivant :

```kotlin
fun main() {
    println("Bonjour, monde du Kotlin !")
}
```

Exécutez le projet. Le résultat dans la console sera :

```
Bonjour, monde du Kotlin !
```

## Exploration approfondie
Kotlin, conçu par JetBrains et lancé en 2011, est un langage moderne qui cible la JVM, le JavaScript et Natif. Il est devenu langue officielle pour le développement Android en 2017. Une alternative est de démarrer avec Android Studio pour des projets Android ou avec le CLI Kotlin pour quelque chose de plus léger.

L'utilisation de Gradle ou Maven pour la gestion de projet en Kotlin est essentielle ; ils gèrent les dépendances, les builds et la documentation. Pensez à système de tuyauterie de votre projet.

Pour un projet JVM classique, Gradle requiert un fichier `build.gradle.kts` avec cette ligne de base :

```kotlin
plugins {
    kotlin("jvm") version "1.6.10"
}
```

Pour Maven, c’est le fichier `pom.xml` qui fait le travail. Vous verrez un bloc `<dependencies>` pour inclure la bibliothèque standard Kotlin.

## Voir également
Pour plus d'informations, voici quelques ressources :

- Documentation Kotlin officielle : https://kotlinlang.org/docs/home.html
- Tutoriels pour les débutants : https://play.kotlinlang.org/byExample/overview
- Configurations Gradle pour Kotlin : https://kotlinlang.org/docs/gradle.html
- Configurations Maven pour Kotlin : https://kotlinlang.org/docs/maven.html

Bonne programmation dans votre nouveauté Kotlin !
