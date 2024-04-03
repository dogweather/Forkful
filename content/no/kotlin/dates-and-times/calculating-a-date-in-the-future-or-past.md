---
date: 2024-01-20 17:31:34.551703-07:00
description: "\xC5 beregne en dato i fremtiden eller fortiden handler om \xE5 tilf\xF8\
  ye eller trekke fra dager, m\xE5neder eller \xE5r fra en n\xE6rv\xE6rende dato.\
  \ Programutviklere gj\xF8r\u2026"
lastmod: '2024-03-13T22:44:40.764398-06:00'
model: gpt-4-1106-preview
summary: "\xC5 beregne en dato i fremtiden eller fortiden handler om \xE5 tilf\xF8\
  ye eller trekke fra dager, m\xE5neder eller \xE5r fra en n\xE6rv\xE6rende dato."
title: Beregning av en dato i fremtiden eller fortiden
weight: 26
---

## Slik gjør du:
```Kotlin
import java.time.LocalDate
import java.time.temporal.ChronoUnit

fun main() {
    val today = LocalDate.now()
    val tenDaysLater = today.plusDays(10)
    val twoWeeksEarlier = today.minusWeeks(2)

    println("I dag: $today")
    println("Om ti dager: $tenDaysLater")
    println("For to uker siden: $twoWeeksEarlier")
}
```

Sample output:
```
I dag: 2023-04-01
Om ti dager: 2023-04-11
For to uker siden: 2023-03-18
```

## Dypdykk
I gamle dager måtte programmerere regne ut datoforandringer manuelt, med mange fallgruver som skuddår og varierende månedslengder. Java 8 introduserte `java.time`-pakken, som Kotlin også benytter, gjør dette enklere og tryggere. Alternativer inkluderer Joda-Time biblioteket før Java 8 og threeten-backport for eldre Java-versjoner. Den interne implementasjonen håndterer alle de kompliserte delene av datoberegning, som tidssoner og kalenderspesifikke regler.

Du kan bruke forskjellige metoder i `LocalDate` for å tilpasse datoen din, som `plusDays`, `minusWeeks` eller `plusMonths`. Kotlin tillater også å bruke `minus`- og `plus`-funksjonene med `Duration` og `Period` for å representere tidsmengder.

## Se Også
- Offisielle Kotlin-dokumenter om dato- og tids-håndtering: [Kotlinlang Documentation](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.time/)
- `java.time`-pakken i Java 8: [Oracle Docs](https://docs.oracle.com/javase/8/docs/api/java/time/package-summary.html)
- Joda-Time, et alternativ før `java.time`: [Joda-Time](http://www.joda.org/joda-time/)
- Threeten-backport, for eldre Java-versjoner: [ThreeTen-Backport](http://www.threeten.org/threetenbp/)
