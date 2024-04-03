---
date: 2024-01-20 17:31:27.092630-07:00
description: "Das Berechnen eines zuk\xFCnftigen oder vergangenen Datums hei\xDFt\
  \ einfach, ein Datum basierend auf einem anderen Datum zu ermitteln. Programmierer\
  \ nutzen das\u2026"
lastmod: '2024-03-13T22:44:53.859412-06:00'
model: gpt-4-1106-preview
summary: "Das Berechnen eines zuk\xFCnftigen oder vergangenen Datums hei\xDFt einfach,\
  \ ein Datum basierend auf einem anderen Datum zu ermitteln."
title: "Berechnung eines zuk\xFCnftigen oder vergangenen Datums"
weight: 26
---

## So geht's:
```Kotlin
import java.time.LocalDate
import java.time.temporal.ChronoUnit

fun main() {
    val heute = LocalDate.now()
    val zukunft = heute.plusDays(10)
    val vergangenheit = heute.minusWeeks(2)

    println("Heute: $heute")
    println("Zukunft (+10 Tage): $zukunft")
    println("Vergangenheit (-2 Wochen): $vergangenheit")
}
```
Sample Output:
```
Heute: 2023-04-07
Zukunft (+10 Tage): 2023-04-17
Vergangenheit (-2 Wochen): 2023-03-24
```

## Deep Dive
In der Geschichte der Programmierung gab es immer wieder neue Herausforderungen bei der Datum- und Zeitverwaltung, da Dinge wie Zeitzonen und Schaltjahre beachtet werden müssen. In Kotlin erledigt das 'java.time' Paket, eingeführt in Java 8, viele dieser Probleme elegant. Vor Java 8 gab es 'java.util.Date' und 'java.util.Calendar', aber diese Klassen waren schwerfällig und fehleranfällig.

Alternativen zu 'java.time' sind Joda-Time und die ThreeTenABP-Bibliothek für Android. Beide bieten ähnliche Funktionen in Sachen Datums- und Zeitberechnung.

## Siehe Auch
- [ChronoUnit Dokumentation](https://docs.oracle.com/javase/8/docs/api/java/time/temporal/ChronoUnit.html)
- [Joda-Time Projekt](https://www.joda.org/joda-time/)
- [ThreeTenABP für Android](https://github.com/JakeWharton/ThreeTenABP)
