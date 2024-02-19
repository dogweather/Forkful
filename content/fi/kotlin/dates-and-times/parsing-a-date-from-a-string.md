---
aliases:
- /fi/kotlin/parsing-a-date-from-a-string/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:14:33.369339-07:00
description: "P\xE4iv\xE4m\xE4\xE4r\xE4n j\xE4sent\xE4minen merkkijonosta tarkoittaa\
  \ tekstist\xE4 Date-objektiksi muuntamista. T\xE4m\xE4 toiminto on olennainen sovelluksille,\
  \ jotka k\xE4sittelev\xE4t\u2026"
lastmod: 2024-02-18 23:09:07.585091
model: gpt-4-0125-preview
summary: "P\xE4iv\xE4m\xE4\xE4r\xE4n j\xE4sent\xE4minen merkkijonosta tarkoittaa tekstist\xE4\
  \ Date-objektiksi muuntamista. T\xE4m\xE4 toiminto on olennainen sovelluksille,\
  \ jotka k\xE4sittelev\xE4t\u2026"
title: "P\xE4iv\xE4m\xE4\xE4r\xE4n j\xE4sennys merkkijonosta"
---

{{< edit_this_page >}}

## Mikä & Miksi?
Päivämäärän jäsentäminen merkkijonosta tarkoittaa tekstistä Date-objektiksi muuntamista. Tämä toiminto on olennainen sovelluksille, jotka käsittelevät käyttäjien syöttämiä päivämääriä tai ulkoisista tietoaineistoista peräisin olevia päivämääriä, mahdollistaen niiden helpomman käsittelyn ja muotoilun tarpeen mukaan.

## Kuinka:
Kotlin tukee päivämäärän jäsentämistä `java.time`-paketin avulla, joka otettiin käyttöön Java 8:ssa. Tässä on yksinkertainen lähestymistapa käyttäen `LocalDateTime`-luokkaa ja tiettyä kaavaa:

```kotlin
import java.time.LocalDateTime
import java.time.format.DateTimeFormatter

fun parseDateFromString(dateString: String): LocalDateTime {
    val formatter = DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss")
    return LocalDateTime.parse(dateString, formatter)
}

fun main() {
    val dateString = "2023-04-01 12:00:00"
    val date = parseDateFromString(dateString)
    println(date)  // Tuloste: 2023-04-01T12:00
}
```

Joustavuuden lisäämiseksi, tai käsiteltäessä päivämääriä ulkoisista lähteistä kuten APIeista, saatat käyttää myös kolmannen osapuolen kirjastoa, kuten Joda-Time (vaikka se on vähemmän yleistä nyt, kun `java.time` on robusti). Kuitenkin JDK:n tarjoaman modernin lähestymistavan noudattaminen on suositeltavaa useimmissa Kotlin-sovelluksissa.

Jotta voisit jäsentää päivämäärän Kotlinissa käyttämättä kolmansien osapuolten kirjastoja, voit myös hyödyntää `SimpleDateFormat`-luokkaa versioissa ennen Java 8:aa tai Androidin API-tasoilla, joilla ei ole `java.time`-tukea:

```kotlin
import java.text.SimpleDateFormat

fun parseDateUsingSimpleDateFormat(dateString: String): java.util.Date {
    val formatter = SimpleDateFormat("yyyy-MM-dd HH:mm:ss")
    return formatter.parse(dateString)
}

fun main() {
    val dateString = "2023-04-01 12:00:00"
    val date = parseDateUsingSimpleDateFormat(dateString)
    println(date)  // Tuloste vaihtelee aikavyöhykkeesi mukaan, esim., lauantai huhtikuun 01 12:00:00 GMT 2023
}
```

Muista aina asettaa aikavyöhyke, kun käytät `SimpleDateFormat`-luokkaa, jotta välttyisit odottamattomilta eroilta jäsentämissä päivämäärissä.
