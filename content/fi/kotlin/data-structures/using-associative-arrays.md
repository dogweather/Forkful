---
changelog:
- 2024-01-30, gpt-4-0125-preview, translated from English
date: 2024-01-30 19:11:39.647937-07:00
description: "Assosiatiiviset taulukot eli mapit Kotlinissa ovat kokoelmia, jotka\
  \ tallentavat avain-arvo -pareja. Ohjelmoijat k\xE4ytt\xE4v\xE4t niit\xE4 dataan\
  \ tehokkaasti\u2026"
lastmod: '2024-03-13T22:44:56.523701-06:00'
model: gpt-4-0125-preview
summary: Assosiatiiviset taulukot eli mapit Kotlinissa ovat kokoelmia, jotka tallentavat
  avain-arvo -pareja.
title: "Assosiatiivisten taulukoiden k\xE4ytt\xF6"
weight: 15
---

## Kuinka tehdään:
Mapin luominen ja käyttäminen Kotlinissa on suoraviivaista. Tässä nopea opas kuinka se tehdään:

```Kotlin
fun main() {
    // Muutettavan mapin luominen
    val fruits = mutableMapOf("a" to "Apple", "b" to "Banana")

    // Alkioiden lisääminen
    fruits["o"] = "Orange" // Käyttäen indeksointioperaatiota
    fruits.put("g", "Grape") // Käyttäen put-metodia

    // Alkioiden hakeminen
    println(fruits["a"])  // Tuloste: Apple
    println(fruits["b"])  // Tuloste: Banana

    // Alkioiden poistaminen
    fruits.remove("b")
    
    // Mapin iterointi
    for ((key, value) in fruits) {
        println("$key -> $value")
    }
    // Näyte tulostus:
    // a -> Apple
    // o -> Orange
    // g -> Grape
}
```

## Syväsukellus
Kotlinin mapit tulevat suoraan sen yhteentoimivuudesta Javan kanssa, jossa mapit ovat olennainen osa kokoelmia. Kuitenkin, Kotlin parantaa niiden käytettävyyttä tarjoamalla sekä muutettavat (`MutableMap`) että vain-luku (`Map`) rajapinnat, toisin kuin Javan yhtenäinen `Map` rajapinta. Tämä ero tekee selväksi, onko kokoelma tarkoitettu muokattavaksi vai ei.

Merkitsevä yksityiskohta Kotlinin map-toteutuksessa on muutettavien ja muuttumattomien mapojen selvä ero, mikä korostaa kielen keskittymistä muuttumattomuuteen ja säieturvallisuuteen.

Vaikka mapit ovat erittäin hyödyllisiä, Kotlin tarjoaa myös muita kokoelmia, kuten listoja ja settejä, joilla kullakin on oma käyttötarkoituksensa. Esimerkiksi listat ylläpitävät järjestystä ja sallivat duplikaatit, tehden niistä ihanteellisia alkioiden hakemiseen indeksin perusteella, kun taas setit varmistavat yksilöllisyyden mutta eivät ylläpidä järjestystä. Mapin, listan tai setin käyttö riippuu sovelluksesi erityisvaatimuksista, kuten avainpohjaisen pääsyn tai järjestyksen säilyttämisen tarpeesta.

Parempien vaihtoehtojen suhteen, jos suorituskyky on kriittistä, erityisesti suurien kokoelmien kanssa, kannattaa harkita erikoistuneiden, tehokkaampien tietorakenteiden käyttöä ulkopuolisista kirjastoista, jotka on optimoitu erityisiin käyttötarkoituksiin, kuten samanaikaiseen pääsyyn tai lajitteluun.
