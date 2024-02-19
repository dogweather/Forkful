---
aliases:
- /de/kotlin/finding-the-length-of-a-string/
date: 2024-01-20 17:47:35.832577-07:00
description: "Die L\xE4nge eines Strings zu finden, hei\xDFt, zu bestimmen, wie viele\
  \ Zeichen er enth\xE4lt. Wir brauchen das, um Textdaten zu validieren, zu schneiden\
  \ oder\u2026"
lastmod: 2024-02-18 23:09:04.816682
model: gpt-4-1106-preview
summary: "Die L\xE4nge eines Strings zu finden, hei\xDFt, zu bestimmen, wie viele\
  \ Zeichen er enth\xE4lt. Wir brauchen das, um Textdaten zu validieren, zu schneiden\
  \ oder\u2026"
title: "Ermittlung der Zeichenkettenl\xE4nge"
---

{{< edit_this_page >}}

## Was & Warum?
Die Länge eines Strings zu finden, heißt, zu bestimmen, wie viele Zeichen er enthält. Wir brauchen das, um Textdaten zu validieren, zu schneiden oder einfach um zu wissen, wie viel Inhalt vorhanden ist.

## How to:
Hier ein schnelles Beispiel, wie man die Länge eines Strings in Kotlin findet:

```kotlin
fun main() {
    val begruessung = "Hallo Welt!"
    println("Die Länge des Strings ist: ${begruessung.length}")
}

// Ausgabe:
// Die Länge des Strings ist: 11
```

## Deep Dive
In Kotlin läuft es unter der Haube so ab, dass die `.length`-Eigenschaft eines Strings dessen `length`-Feld aus der Java-Stringklasse abruft. Historisch stammt diese Eigenschaft aus Java, da Kotlin darauf aufbaut und problemlos mit Java-Code interoperiert.

Alternativen? Man kann auch manuell durch den String iterieren und zählen – aber warum das Rad neu erfinden? Kotlin bringt bereits alles Nötige mit.

Einen wichtigen Punkt gibt es allerdings: Unicode. Bei Zeichen, die als Surrogate Pairs repräsentiert werden, kann `.length` irreführend sein, da es die Anzahl der `Char`-Einheiten zurückgibt und nicht die tatsächliche Anzahl der Codepunkte. Für die meisten Anwendungsfälle ist dies aber ein Randthema.

## See Also
- Kotlin-Standardbibliothek zur String-Behandlung: [https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/)
- Unicode in Kotlin verstehen: [https://kotlinlang.org/docs/characters.html](https://kotlinlang.org/docs/characters.html)
