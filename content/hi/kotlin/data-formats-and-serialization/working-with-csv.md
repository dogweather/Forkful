---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:21:30.930803-07:00
description: "CSV (Comma-Separated Values) \u0915\u0947 \u0938\u093E\u0925 \u0915\u093E\
  \u092E \u0915\u0930\u0928\u093E \u0938\u093E\u0926\u093E \u092A\u093E\u0920 \u092E\
  \u0947\u0902 \u0924\u093E\u0932\u093F\u0915\u093E \u0921\u0947\u091F\u093E \u0938\
  \u0902\u0917\u094D\u0930\u0939\u0940\u0924 \u0915\u0930\u0928\u0947 \u0915\u0947\
  \ \u090F\u0915 \u0938\u093E\u092E\u093E\u0928\u094D\u092F \u092A\u094D\u0930\u093E\
  \u0930\u0942\u092A, CSV \u092B\u093C\u093E\u0907\u0932\u094B\u0902 \u0938\u0947\
  \ \u0921\u0947\u091F\u093E \u092A\u0922\u093C\u0928\u0947 \u0914\u0930 \u0909\u0938\
  \ \u092A\u0930 \u0932\u093F\u0916\u0928\u0947 \u0915\u093E \u0915\u093E\u092E\u2026"
lastmod: '2024-03-13T22:44:52.297369-06:00'
model: gpt-4-0125-preview
summary: "CSV (Comma-Separated Values) \u0915\u0947 \u0938\u093E\u0925 \u0915\u093E\
  \u092E \u0915\u0930\u0928\u093E \u0938\u093E\u0926\u093E \u092A\u093E\u0920 \u092E\
  \u0947\u0902 \u0924\u093E\u0932\u093F\u0915\u093E \u0921\u0947\u091F\u093E \u0938\
  \u0902\u0917\u094D\u0930\u0939\u0940\u0924 \u0915\u0930\u0928\u0947 \u0915\u0947\
  \ \u090F\u0915 \u0938\u093E\u092E\u093E\u0928\u094D\u092F \u092A\u094D\u0930\u093E\
  \u0930\u0942\u092A, CSV \u092B\u093C\u093E\u0907\u0932\u094B\u0902 \u0938\u0947\
  \ \u0921\u0947\u091F\u093E \u092A\u0922\u093C\u0928\u0947 \u0914\u0930 \u0909\u0938\
  \ \u092A\u0930 \u0932\u093F\u0916\u0928\u0947 \u0915\u093E \u0915\u093E\u092E \u0936\
  \u093E\u092E\u093F\u0932 \u0939\u0948\u0964 \u092A\u094D\u0930\u094B\u0917\u094D\
  \u0930\u093E\u092E\u0930\u094D\u0938 \u0935\u093F\u092D\u093F\u0928\u094D\u0928\
  \ \u0905\u0928\u0941\u092A\u094D\u0930\u092F\u094B\u0917\u094B\u0902, \u0921\u0947\
  \u091F\u093E\u092C\u0947\u0938\u094B\u0902 \u0915\u0947 \u092C\u0940\u091A \u0921\
  \u0947\u091F\u093E \u0915\u093E \u0906\u0938\u093E\u0928\u0940 \u0938\u0947 \u0906\
  \u0926\u093E\u0928-\u092A\u094D\u0930\u0926\u093E\u0928 \u0915\u0930\u0928\u0947\
  \ \u092F\u093E \u0921\u0947\u091F\u093E \u092A\u094D\u0930\u094B\u0938\u0947\u0938\
  \u093F\u0902\u0917 \u0914\u0930 \u0935\u093F\u0936\u094D\u0932\u0947\u0937\u0923\
  \ \u0915\u093E\u0930\u094D\u092F \u0938\u0941\u0935\u093F\u0927\u093E\u091C\u0928\
  \u0915 \u092C\u0928\u093E\u0928\u0947 \u0915\u0947 \u0932\u093F\u090F CSV \u092B\
  \u093C\u093E\u0907\u0932\u094B\u0902 \u0915\u093E \u092E\u0947\u0928\u093F\u092A\
  \u0941\u0932\u0947\u0936\u0928 \u0915\u0930\u0924\u0947 \u0939\u0948\u0902\u0964\
  ."
title: "CSV \u0915\u0947 \u0938\u093E\u0925 \u0915\u093E\u092E \u0915\u0930\u0928\u093E"
weight: 37
---

## कैसे करें:
कोटलिन, एक स्टैटिकली टाइप्ड प्रोग्रामिंग भाषा है जो JVM पर चलती है, लेकिन इसमें CSV फाइलों को संभालने के लिए एक निर्मित पुस्तकालय शामिल नहीं होता है। हालांकि, आप बेसिक ऑपरेशनों के लिए जावा `BufferedReader` और `FileWriter` क्लासों का उपयोग कर सकते हैं, या `kotlinx.serialization` और `opencsv` जैसी लोकप्रिय तीसरे पक्ष की लाइब्रेरीज का लाभ उठाकर अधिक उन्नत फंक्शनलिटी के लिए कर सकते हैं।

### BufferedReader का उपयोग करके CSV फ़ाइल पढ़ना:
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

_नमूना आउटपुट:_

```
[Name, Age, City]
[John Doe, 30, New York]
[Jane Smith, 25, London]
```

### FileWriter का उपयोग करके CSV फ़ाइल में लिखना:
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

इससे `output.csv` नामक फ़ाइल में दी गई डेटा के साथ बनाया जाएगा या उसे अधिलेखित किया जाएगा।

### kotlinx.serialization का उपयोग करके CSV Serialization:
सबसे पहले, अपनी `build.gradle.kts` में निर्भरता जोड़ें:

```kotlin
implementation("org.jetbrains.kotlinx:kotlinx-serialization-csv:0.3.0")
```

_नोट: आपके पास सही संस्करण और रेपोजिटरी कॉन्फ़िगरेशन होना जरूरी है।_

फिर, अपना डेटा क्लास परिभाषित करें और Serialization के लिए `Csv` प्रारूप का उपयोग करें:

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

_नमूना आउटपुट:_

```
John Doe,30,New York
Jane Smith,25,London
```

### OpenCSV का उपयोग करके उन्नत ऑपरेशंस:
अपनी प्रोजेक्ट की निर्भरताओं में OpenCSV जोड़ें:

```kotlin
implementation("com.opencsv:opencsv:5.6")
```

OpenCSV के साथ पढ़ने और लिखने:

```kotlin
import com.opencsv.CSVReader
import com.opencsv.CSVWriter
import java.io.FileReader
import java.io.FileWriter

fun main() {
    // CSV पढ़ना
    CSVReader(FileReader("data.csv")).use { csvReader ->
        val entries = csvReader.readAll()
        entries.forEach { println(it.toList()) }
    }

    // CSV लिखना
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

ये कोड स्निपेट्स कोटलिन की CSV फ़ाइलों के साथ काम करते समय की पेशकश की गई लचीलापन को दर्शाते हैं, जिससे आप अपनी परियोजना की आवश्यकताओं के लिए सर्वोत्तम विधि का चयन कर सकते हैं।
