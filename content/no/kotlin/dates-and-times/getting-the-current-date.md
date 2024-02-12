---
title:                "Få dagens dato"
date:                  2024-02-03T19:10:18.788450-07:00
model:                 gpt-4-0125-preview
simple_title:         "Få dagens dato"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/no/kotlin/getting-the-current-date.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Hva og hvorfor?
I programmering er det å få tak i dagens dato en grunnleggende oppgave som gjør det mulig for utviklere å få tilgang til, vise eller manipulere dagens dato innenfor applikasjonene deres. Denne evnen er avgjørende for alt fra logging og tidsstempling av hendelser til beregninger basert på datoer.

## Hvordan:

### Bruke Standard Kotlin
Kotlin har ikke sitt eget dato- og klokkeslett-API, men stoler på Java Standard Library for denne funksjonaliteten. Slik kan du få tak i dagens dato:

```kotlin
import java.time.LocalDate

fun main() {
    val today = LocalDate.now()
    println("Dagens dato: $today")
}
```

**Eksempel på utdata:**
```
Dagens dato: 2023-04-05
```

### Bruke java.util.Date
For operasjoner som krever både dato og klokkeslett, kan du foretrekke `java.util.Date`.

```kotlin
import java.util.Date

fun main() {
    val currentDate = Date()
    println("Nåværende dato og tid: $currentDate")
}
```

**Eksempel på utdata:**
```
Nåværende dato og tid: Ons Apr 05 15:20:45 GMT 2023
```

### Bruke Joda-Time Biblioteket
Før Java 8 introduserte et nytt dato- og klokkeslett-API, var Joda-Time de facto standarden for dato-tidsoperasjoner i Java og Kotlin. Selv om det ikke lenger er nødvendig for mange prosjekter, kan noen fortsatt bruke det av arvegrunner eller personlig preferanse.

Legg til Joda-Time biblioteket i ditt prosjekts build.gradle fil:
```
implementation 'joda-time:joda-time:2.10.10'
```

```kotlin
import org.joda.time.LocalDate

fun main() {
    val today = LocalDate.now()
    println("Dagens dato: $today")
}
```

**Eksempel på utdata:**
```
Dagens dato: 2023-04-05
```

### Bruke ThreeTenABP for Android
For Android-utvikling anbefales det å bruke tilbakeportering av Java Time API via ThreeTen Android Backport Project for versjoner før Android API-nivå 26.

Legg til avhengigheten i appens build.gradle-fil:
```
implementation 'com.jakewharton.threetenabp:threetenabp:1.3.1'
```

Initialiser den i din Application klasse:
```kotlin
import android.app.Application
import com.jakewharton.threetenabp.AndroidThreeTen

class MyApp : Application() {
    override fun onCreate() {
        super.onCreate()
        AndroidThreeTen.init(this)
    }
}
```

Deretter kan du bruke den slik:
```kotlin
import org.threeten.bp.LocalDate

fun main() {
    val today = LocalDate.now()
    println("Dagens dato: $today")
}
```

**Eksempel på utdata:**
```
Dagens dato: 2023-04-05
```
