---
title:                "Arbeta med CSV"
aliases:
- sv/kotlin/working-with-csv.md
date:                  2024-02-03T19:20:33.824753-07:00
model:                 gpt-4-0125-preview
simple_title:         "Arbeta med CSV"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/kotlin/working-with-csv.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Vad & Varför?

Att arbeta med CSV (Comma-Separated Values) innebär att läsa från och skriva data till CSV-filer, ett vanligt format för att lagra tabelldata i klartext. Programmerare manipulerar CSV-filer för att enkelt utbyta data mellan olika applikationer, databaser eller för att underlätta uppgifter inom databehandling och analys.

## Hur:

Kotlin, som är ett statiskt typat programmeringsspråk som körs på JVM, inkluderar inte ett inbyggt bibliotek för hantering av CSV-filer. Du kan dock använda Java-klasserna `BufferedReader` och `FileWriter` för grundläggande operationer, eller dra nytta av populära tredjepartsbibliotek som `kotlinx.serialization` och `opencsv` för mer avancerad funktionalitet.

### Att läsa en CSV-fil med BufferedReader:

```kotlin
import java.io.BufferedReader
import java.io.FileReader

fun main() {
    val path = "data.csv"
    val br = BufferedReader(FileReader(path))
    br.useLines { lines ->
        lines.forEach { line ->
            val cols = line.split(',')
            println(cols)
        }
    }
}
```

_Exempel på utskrift:_

```
[Name, Age, City]
[John Doe, 30, New York]
[Jane Smith, 25, London]
```

### Att skriva till en CSV-fil med FileWriter:

```kotlin
import java.io.FileWriter

fun main() {
    val data = listOf(
        listOf("Name", "Age", "City"),
        listOf("John Doe", "30", "New York"),
        listOf("Jane Smith", "25", "London")
    )

    FileWriter("output.csv").use { writer ->
        data.forEach { row ->
            writer.write(row.joinToString(",") + "\n")
        }
    }
}
```

Detta kommer att skapa eller skriva över `output.csv` med den angivna datan.

### Att använda kotlinx.serialization för CSV-serialisering:

Lägg tillst först beroendet till din `build.gradle.kts`:

```kotlin
implementation("org.jetbrains.kotlinx:kotlinx-serialization-csv:0.3.0")
```

_Notera: Se till att du har rätt version och konfiguration för repositoriet._

Definiera sedan din dataklass och använd `Csv`-formatet för serialisering:

```kotlin
import kotlinx.serialization.Serializable
import kotlinx.serialization.csv.Csv
import kotlinx.serialization.encodeToString

@Serializable
data class Person(val name: String, val age: Int, val city: String)

fun main() {
    val csvFormat = Csv { delimiter = ',' }
    val data = listOf(
        Person("John Doe", 30, "New York"),
        Person("Jane Smith", 25, "London")
    )

    val csvData = csvFormat.encodeToString(data)
    println(csvData)
}
```

_Exempel på utskrift:_

```
John Doe,30,New York
Jane Smith,25,London
```

### Att använda OpenCSV för avancerade operationer:

Lägg till OpenCSV till ditt projekts beroenden:

```kotlin
implementation("com.opencsv:opencsv:5.6")
```

Att läsa och skriva med OpenCSV:

```kotlin
import com.opencsv.CSVReader
import com.opencsv.CSVWriter
import java.io.FileReader
import java.io.FileWriter

fun main() {
    // Läsa CSV
    CSVReader(FileReader("data.csv")).use { csvReader ->
        val entries = csvReader.readAll()
        entries.forEach { println(it.toList()) }
    }

    // Skriva CSV
    CSVWriter(FileWriter("output.csv")).use { csvWriter ->
        val entries = listOf(
            arrayOf("Name", "Age", "City"),
            arrayOf("John Doe", "30", "New York"),
            arrayOf("Jane Smith", "25", "London")
        )
        csvWriter.writeAll(entries)
    }
}
```

Dessa kodsnuttar demonstrerar den flexibilitet Kotlin erbjuder när det gäller att arbeta med CSV-filer, vilket gör att du kan välja den metod som bäst passar dina projektbehov.
