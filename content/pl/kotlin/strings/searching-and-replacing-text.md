---
title:                "Wyszukiwanie i zamiana tekstu"
date:                  2024-01-20T17:58:19.150246-07:00
model:                 gpt-4-1106-preview
simple_title:         "Wyszukiwanie i zamiana tekstu"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/kotlin/searching-and-replacing-text.md"
---

{{< edit_this_page >}}

## Co i Dlaczego?

Wyszukiwanie i zamiana tekstu to proces znajdowania ciągów znaków i ich podmieniania na inne. Programiści to robią, by szybko aktualizować kod, dane czy ulepszać programy.

## Jak to zrobić:

```kotlin
fun main() {
    val text = "Kotlin to super język!"
    val searchText = "super"
    val replaceWith = "fantastyczny"
    
    val updatedText = text.replace(searchText, replaceWith)
    println(updatedText) // Kotlin to fantastyczny język!
}
```

## W głębi tematu

Historia wyszukiwania i zamiany tekstu sięga pierwszych edytorów tekstu. Pojawiła się konieczność szybkiego poprawiania tekstów, co doprowadziło do powstania komendy `find and replace`. W Kotlinie, podobnie jak w innych współczesnych językach, operacje te są banalne, a funkcje wbudowane ułatwiają pracę.

Alternatywy dla `replace()` to regex (wyrażenia regularne), które pozwalają na bardziej złożone wyszukiwanie. Możesz użyć `Regex` w Kotlinie, by sprawdzić pasowanie wzorca, jak poniżej:

```kotlin
fun main() {
    val regex = Regex("[a-zA-Z]+ to [a-z]+ język!")
    val text = "Kotlin to super język!"
    val isMatch = regex.containsMatchIn(text)
    
    println(if (isMatch) "Pasuje!" else "Nie pasuje!") // Pasuje!
}
```

Na poziomie implementacji, należy pamiętać o wydajności przy obsłudze dużych zbiorów danych – tutaj już `replace()` może nie wystarczyć i lepiej sięgnąć po biblioteki lub algorytmy dedykowane przeszukiwaniu tekstu, jak KMP (Knuth-Morris-Pratt).

## Zobacz także

- [Dokumentacja Kotlin - replace](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.text/replace.html)
- [Przewodnik po wyrażeniach regularnych](https://www.regular-expressions.info/)
- [Algorytm KMP](https://en.wikipedia.org/wiki/Knuth–Morris–Pratt_algorithm)
