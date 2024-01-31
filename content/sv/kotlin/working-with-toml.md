---
title:                "Att arbeta med TOML"
date:                  2024-01-26T04:23:56.123907-07:00
model:                 gpt-4-0125-preview
simple_title:         "Att arbeta med TOML"

tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/kotlin/working-with-toml.md"
---

{{< edit_this_page >}}

## Vad & Varför?
TOML står för Toms Uppenbara, Minimala Språk. Det används för konfigurationsfiler eftersom det är lätt att läsa och skriva för människor, samtidigt som det är lätt att tolka för maskiner. Utvecklare väljer TOML för att undvika röran med XML och knepigheten med JSON när de hanterar konfigurationer.

## Hur man gör:
För att hantera TOML i Kotlin kan du använda ett bibliotek som `ktoml`. Låt oss först lägga till beroendet i din `build.gradle.kts`:

```kotlin
dependencies {
    implementation("com.akuleshov7:ktoml:0.2.5")
}
```

Nu låt oss tolka lite TOML:

```kotlin
import com.akuleshov7.ktoml.file.TomlFileReader

fun main() {
    val tomlInnehåll = TomlFileReader.readAndParseFile("config.toml")
    
    val databasKonfig = tomlInnehåll.getTable("database")
    val värd = databasKonfig.getString("host")
    val port = databasKonfig.getLong("port")

    println("Databas Värd: $värd")
    println("Databas Port: $port")
}
```

Antar att `config.toml` ser ut så här:

```toml
[database]
host = "localhost"
port = 5432
```

Exempelutskrift skulle vara:

```
Databas Värd: localhost
Databas Port: 5432
```

## Fördjupning
TOML, som kreerades av GitHub-medsgrundare Tom Preston-Werner 2013, syftade till att vara mer rakt på sak än YAML och mer typsäkert än JSON. Det har blivit en succé, särskilt med Rusts `Cargo` och Gos modulsystem. Alternativ? YAML har fler funktioner, JSON översätts direkt till objekt i många programmeringsspråk, och det finns alltid goda gamla XML. När det gäller implementering är ktoml, under Apache 2.0-licens, ett rent Kotlin-bibliotek och drar inte med sig Java-bibliotek, och erbjuder även DSL:er för att skriva TOML, inte bara läsa.

## Se även
- TOML GitHub: https://github.com/toml-lang/toml
- ktoml GitHub: https://github.com/akuleshov7/ktoml
- TOML vs. YAML vs. JSON: https://blog.logrocket.com/comparing-configuration-files-yaml-toml-json/
