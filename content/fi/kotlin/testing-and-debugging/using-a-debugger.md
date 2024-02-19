---
aliases:
- /fi/kotlin/using-a-debugger/
date: 2024-01-26 03:50:23.101377-07:00
description: "Sukeltaminen debuggerin maailmaan on kaikkea muuta kuin koodisi l\xE4\
  pik\xE4ynti\xE4 askel askeleelta, koneiston py\xF6ritt\xE4mist\xE4 ja niiden kiusallisten\
  \ virheiden\u2026"
lastmod: 2024-02-18 23:09:07.579637
model: gpt-4-0125-preview
summary: "Sukeltaminen debuggerin maailmaan on kaikkea muuta kuin koodisi l\xE4pik\xE4\
  ynti\xE4 askel askeleelta, koneiston py\xF6ritt\xE4mist\xE4 ja niiden kiusallisten\
  \ virheiden\u2026"
title: "Debuggerin k\xE4ytt\xF6"
---

{{< edit_this_page >}}

## Mikä ja miksi?
Sukeltaminen debuggerin maailmaan on kaikkea muuta kuin koodisi läpikäyntiä askel askeleelta, koneiston pyörittämistä ja niiden kiusallisten virheiden kiinniottamista itse teosta. Ohjelmoijat käyttävät debuggereita, koska ne ovat etsivätyökaluja, jotka auttavat meitä selvittämään, missä asiat menevät pieleen repimättä hiuksiamme päästä.

## Kuinka:
Tässä on pieni maistiainen Kotlinin debuggaamisesta IntelliJ IDEA:ssa - IDEiden Sherlock Holmes:

```kotlin
fun main() {
    val mysteryNumber = 42
    var arvaus = 0

    while (arvaus != mysteryNumber) {
        println("Arvaa numero: ")
        arvaus = readLine()?.toIntOrNull() ?: continue // Ohita huonot syötteet

        // Aseta tässä kohtaa katkaisupiste seurataksesi 'arvaus'-muuttujan toimintaa
        if (arvaus < mysteryNumber) {
            println("Liian matala!")
        } else if (arvaus > mysteryNumber) {
            println("Liian korkea!")
        }
    }

    println("Oikein! Mysteerinumero oli $mysteryNumber")
}
```

Debuggerin tuloste:
```
Arvaa numero: 
10
Liian matala!
Arvaa numero: 
50
Liian korkea!
Arvaa numero: 
42
Oikein! Mysteerinumero oli 42
```

## Syväsukellus
Debuggerit ovat olleet pelissä mukana jo 50-luvulta lähtien. Tuolloin ne olivat melko primitiivisiä, ja debuggaus saattoi koskea enemmän laitteistoa kuin ohjelmistoa. Nykyään debuggeri, kuten IntelliJ IDEA:ssa, antaa meidän asettaa katkaisupisteitä, käydä läpi koodia rivi riviltä ja tarkastella muuttujien tilaa vapaa-ajallamme.

Vaikka IntelliJ:n debuggeri on erittäin kätevä Kotlinille, se ei ole ainoa kala meressä. Tarjolla on vaihtoehtoja, kuten Logcat Android-kehitykseen tai komentorivityökalut, kuten jdb minimalisteille. Tässä suurin taika on pääosin JVM Tool Interface (JVMTI):ssa, joka antaa debuggerien olla vuorovaikutuksessa Java Virtuaalikoneen kanssa, pitäen Kotlin-kehittäjät lennossa mukana.

## Katso myös
- IntelliJ IDEA Debugger -dokumentaatio: [https://jetbrains.com/idea/](https://www.jetbrains.com/idea/features/debugger.html)
