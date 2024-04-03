---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:23:06.492430-07:00
description: "Ty\xF6skentely JSONin (JavaScript Object Notation) kanssa Kotlinitssa\
  \ liittyy JSON-datamuodon j\xE4sennys- ja luontitoimiin. Ohjelmoijat tekev\xE4t\
  \ t\xE4m\xE4n\u2026"
lastmod: '2024-03-13T22:44:56.552708-06:00'
model: gpt-4-0125-preview
summary: "Ty\xF6skentely JSONin (JavaScript Object Notation) kanssa Kotlinitssa liittyy\
  \ JSON-datamuodon j\xE4sennys- ja luontitoimiin."
title: "Ty\xF6skentely JSON:n kanssa"
weight: 38
---

## Kuinka:
Kotlin ei sisällä valmiiksi tukea JSONille, mutta se hyödyntää kolmansien osapuolien kirjastojen, kuten Googlen `Gson` ja JetBrainsin `Kotlinx.serialization`, tehokkaita ominaisuuksia. Tässä on ohjeet, kuinka voit käyttää molempia työskennelläksesi JSONin kanssa.

### Gsonin käyttö
Lisää Gson-riippuvuus `build.gradle` tiedostoosi:
```kotlin
implementation 'com.google.code.gson:gson:2.8.9'
```

JSON-muotoisen merkkijonon jäsennys olioksi ja päinvastoin:
```kotlin
import com.google.gson.Gson

// Määrittele data-luokka
data class User(val name: String, val age: Int)

fun main() {
    val gson = Gson()

    // Serialisointi
    val json = gson.toJson(User("John Doe", 30))
    println(json)  // Tuloste: {"name":"John Doe","age":30}

    // Deserialisointi
    val user: User = gson.fromJson(json, User::class.java)
    println(user)  // Tuloste: User(name=John Doe, age=30)
}
```

### Kotlinx.serializationin käyttö
Lisää ensin riippuvuus `build.gradle`-tiedostoosi:
```kotlin
implementation "org.jetbrains.kotlinx:kotlinx-serialization-json:1.3.3"
```

Tämän jälkeen sovella `kotlinx-serialization` -lisäosaa koodisi alkuun:
```kotlin
plugins {
    kotlin("jvm") version "1.6.10"
    kotlin("plugin.serialization") version "1.6.10"
}
```

Serialisointi ja deserialisointi Kotlinx.serializationin avulla:
```kotlin
import kotlinx.serialization.*
import kotlinx.serialization.json.*

// Määrittele sarjoitettava data-luokka
@Serializable
data class User(val name: String, val age: Int)

fun main() {
    // Serialisointi
    val json = Json.encodeToString(User("Jane Doe", 28))
    println(json)  // Tuloste: {"name":"Jane Doe","age":28}

    // Deserialisointi
    val user = Json.decodeFromString<User>(json)
    println(user)  // Tuloste: User(name=Jane Doe, age=28)
}
```

Sekä Gson että Kotlinx.serialization yksinkertaistavat JSONin käsittelyä Kotlin-sovelluksissa, ja kumpaa niistä käytetään, riippuu projektisi erityisvaatimuksista ja henkilökohtaisista mieltymyksistäsi.
