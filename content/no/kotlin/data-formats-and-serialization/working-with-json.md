---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:23:12.322101-07:00
description: "Arbeid med JSON (JavaScript Object Notation) i Kotlin involverer parsing\
  \ og generering av JSON-data. Programmerere gj\xF8r dette for \xE5 enkelt utveksle\
  \ data\u2026"
lastmod: '2024-03-13T22:44:40.773659-06:00'
model: gpt-4-0125-preview
summary: Arbeid med JSON (JavaScript Object Notation) i Kotlin involverer parsing
  og generering av JSON-data.
title: Arbeider med JSON
weight: 38
---

## Hvordan:
Kotlin inkluderer ikke innebygd støtte for JSON, men benytter seg av kraftige funksjoner fra tredjepartsbiblioteker som `Gson` fra Google og `Kotlinx.serialization` fra JetBrains. Her er hvordan du kan bruke begge til å arbeide med JSON.

### Bruke Gson
Legg til Gson-avhengigheten i din `build.gradle`-fil:
```kotlin
implementation 'com.google.code.gson:gson:2.8.9'
```

Parse en JSON-streng til et objekt og omvendt:
```kotlin
import com.google.gson.Gson

// Definer en dataklasse
data class User(val name: String, val age: Int)

fun main() {
    val gson = Gson()

    // Serialisere
    val json = gson.toJson(User("John Doe", 30))
    println(json)  // Utdata: {"name":"John Doe","age":30}

    // Deserialisere
    val user: User = gson.fromJson(json, User::class.java)
    println(user)  // Utdata: User(name=John Doe, age=30)
}
```

### Bruke Kotlinx.serialization
Først, inkluder avhengigheten i din `build.gradle`:
```kotlin
implementation "org.jetbrains.kotlinx:kotlinx-serialization-json:1.3.3"
```

Deretter, bruk `kotlinx-serialization`-pluginen øverst i byggscriptet ditt:
```kotlin
plugins {
    kotlin("jvm") version "1.6.10"
    kotlin("plugin.serialization") version "1.6.10"
}
```

Serialisering og deserialisering med Kotlinx.serialization:
```kotlin
import kotlinx.serialization.*
import kotlinx.serialization.json.*

// Definer en serialiserbar dataklasse
@Serializable
data class User(val name: String, val age: Int)

fun main() {
    // Serialisere
    val json = Json.encodeToString(User("Jane Doe", 28))
    println(json)  // Utdata: {"name":"Jane Doe","age":28}

    // Deserialisere
    val user = Json.decodeFromString<User>(json)
    println(user)  // Utdata: User(name=Jane Doe, age=28)
}
```

Både Gson og Kotlinx.serialization forenkler arbeid med JSON i Kotlin-applikasjoner, å velge den ene over den andre avhenger av dine spesifikke prosjektkrav og personlige preferanser.
