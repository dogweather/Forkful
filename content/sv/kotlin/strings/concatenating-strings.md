---
aliases:
- /sv/kotlin/concatenating-strings/
date: 2024-01-20 17:35:19.671365-07:00
description: "Stringkonkatenering inneb\xE4r att s\xE4tta ihop textstr\xE4ngar till\
  \ en ny, l\xE4ngre str\xE4ng. Vi g\xF6r det f\xF6r att bygga meddelanden, skapa\
  \ dynamiska texter, eller\u2026"
lastmod: 2024-02-18 23:08:51.742113
model: gpt-4-1106-preview
summary: "Stringkonkatenering inneb\xE4r att s\xE4tta ihop textstr\xE4ngar till en\
  \ ny, l\xE4ngre str\xE4ng. Vi g\xF6r det f\xF6r att bygga meddelanden, skapa dynamiska\
  \ texter, eller\u2026"
title: "Sammanslagning av str\xE4ngar"
---

{{< edit_this_page >}}

## Vad & Varför?
Stringkonkatenering innebär att sätta ihop textsträngar till en ny, längre sträng. Vi gör det för att bygga meddelanden, skapa dynamiska texter, eller helt enkelt kombinera data för visning.

## Hur gör man:
```kotlin
fun main() {
    val hej = "Hej "
    val varlden = "världen!"
    val halsning = hej + varlden  // Använder '+' operator
    println(halsning) // Skriver ut "Hej världen!"

    val namn = "Sven"
    val meddelande = "$hej$namn!" // Använder string templates
    println(meddelande) // Skriver ut "Hej Sven!"

    val ord = listOf("Kotlin", "är", "roligt!")
    val mening = ord.joinToString(" ") // Använder joinToString-funktionen
    println(mening) // Skriver ut "Kotlin är roligt!"
}
```
## Fördjupning
Stringkonkatenering har funnits så länge vi har programmerat. I tidigare språk som C användes funktioner som `strcat()` men kunde skapa säkerhetsproblem om inte hanterat varsamt. I moderna språk som Kotlin görs det säkrare och enklare med operatorer och string templates.

När det gäller alternativ, kan bygga strängar med `StringBuilder` vara effektivare för längre eller komplexa strängoperationer. Kotlin hanterar stränginterpolering och konkatenering smart bakom kulisserna så att prestandan generellt är bra även utan `StringBuilder`.

Implementation kan variera mellan olika programmeringsspråk. Kotlin kompilerar strängkonkatenering till Java Bytecode som använder `StringBuilder` under huven vid behov för att effektivisera sammansättningen.

## Se också
- [Kotlin Dokumentation om String Templates](https://kotlinlang.org/docs/basic-syntax.html#string-templates)
- [Oracle Java docs om StringBuilder](https://docs.oracle.com/javase/8/docs/api/java/lang/StringBuilder.html)
- [StackOverflow diskussion om String Performance i Kotlin](https://stackoverflow.com/questions/4645020/performance-tuning-the-stringbuilder-in-java)
