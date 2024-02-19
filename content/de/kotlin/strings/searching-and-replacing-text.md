---
aliases:
- /de/kotlin/searching-and-replacing-text/
date: 2024-01-20 17:58:00.793158-07:00
description: "Suchen und Ersetzen ist die Aktion, Textmuster in einem String zu finden\
  \ und sie durch neue Inhalte zu ersetzen. Programmierer nutzen diese Funktion, um\u2026"
lastmod: 2024-02-18 23:09:04.810376
model: gpt-4-1106-preview
summary: "Suchen und Ersetzen ist die Aktion, Textmuster in einem String zu finden\
  \ und sie durch neue Inhalte zu ersetzen. Programmierer nutzen diese Funktion, um\u2026"
title: Suchen und Ersetzen von Text
---

{{< edit_this_page >}}

## Was & Warum?
Suchen und Ersetzen ist die Aktion, Textmuster in einem String zu finden und sie durch neue Inhalte zu ersetzen. Programmierer nutzen diese Funktion, um Daten zu korrigieren, zu aktualisieren oder spezifische Muster in einer großen Menge von Text effizient zu bearbeiten.

## How to:
```kotlin
fun main() {
    val text = "Hallo Welt! Kotlin ist toll. Kotlin macht Spaß."
    val searchText = "Kotlin"
    val replaceWith = "Java"

    val newText = text.replace(searchText, replaceWith)
    println(newText) // Ausgabe: Hallo Welt! Java ist toll. Java macht Spaß.
}
```

## Tiefere Einblicke
Die Suche und Ersetzung von Text kommt aus den Anfängen der Datenverarbeitung, als Texteditoren aufkamen. Früher musste man Textzeilenweise verarbeiten; heute nutzen wir reguläre Ausdrücke und String-Methoden in Programmiersprachen. In Kotlin ist die `replace`-Funktion der Standardweg: sie ist einfach und effektiv. Alternativen wären das Arbeiten mit `StringBuilder` oder manuelle Schleifen, um spezifischere Anpassungen durchzuführen oder Performance zu optimieren.

## Siehe Auch
- Kotlin Dokumentation zur `replace`-Funktion: https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.text/replace.html
- Regex Hilfe in Kotlin: https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.text/-regex/
- Textbearbeitung in Kotlin: https://kotlinlang.org/docs/collections-transformations.html#map-elements
