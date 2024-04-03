---
date: 2024-01-20 17:47:34.339380-07:00
description: "Stringin pituuden selvitt\xE4minen tarkoittaa merkkijonon merkkien lukum\xE4\
  \xE4r\xE4n laskemista. Ohjelmoijat tekev\xE4t t\xE4m\xE4n, kun heid\xE4n t\xE4ytyy\
  \ k\xE4sitell\xE4 tekstin\u2026"
lastmod: '2024-03-13T22:44:56.521881-06:00'
model: gpt-4-1106-preview
summary: "Stringin pituuden selvitt\xE4minen tarkoittaa merkkijonon merkkien lukum\xE4\
  \xE4r\xE4n laskemista."
title: "Merkkijonon pituuden selvitt\xE4minen"
weight: 7
---

## Kuinka:
```kotlin
fun main() {
    val exampleString = "Hei maailma!"
    val length = exampleString.length
    println("Merkkijonon pituus on: $length")  // Output: Merkkijonon pituus on: 12
}
```

## Syväsukellus
Stringin pituuden selvittäminen on ollut perusominaisuutena ohjelmointikielissä jo varhain, koska sen avulla voidaan hallita ja validoida syötteitä. Kotlinissa `.length`-ominaisuus palauttaa `Int`-tyypin arvon, joka kertoo merkkijonon pituuden. Vaihtoehtoisesti, vanhemmissa kielissä kuten C:ssä, merkkijonon loppu tunnistetaan nolla-terminaattorilla, ja pituuden laskeminen vaatii toistoloopin. Javassa ja Kotlinissa tämä on yksinkertaistettu, ja suorituskykyn optimoinnin lisäksi kehittäjäkokemus on parantunut.

## Katso Myös
- Kotlinin virallinen dokumentaatio merkkijonoille: [Kotlin Strings](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/)
