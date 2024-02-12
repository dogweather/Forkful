---
title:                "Verwendung von assoziativen Arrays"
aliases:
- /de/kotlin/using-associative-arrays/
date:                  2024-01-30T19:11:45.311584-07:00
model:                 gpt-4-0125-preview
simple_title:         "Verwendung von assoziativen Arrays"

tag:                  "Data Structures"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/kotlin/using-associative-arrays.md"
changelog:
  - 2024-01-30, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Was & Warum?

Assoziative Arrays, oder Maps, in Kotlin sind Sammlungen, die Schlüssel-Wert-Paare speichern. Programmierer nutzen sie, um Daten effizient zu organisieren und anhand eindeutiger Schlüssel abzurufen, was das Verwalten von Informationen erleichtert.

## Wie geht das:

Eine Map in Kotlin zu erstellen und zu verwenden, ist unkompliziert. Hier ist eine kurze Anleitung dazu:

```Kotlin
fun main() {
    // Eine veränderbare Map erstellen
    val fruits = mutableMapOf("a" to "Apfel", "b" to "Banane")

    // Elemente hinzufügen
    fruits["o"] = "Orange" // Mit Indexierungsoperation
    fruits.put("g", "Traube") // Mit put Methode

    // Elemente zugreifen
    println(fruits["a"])  // Ausgabe: Apfel
    println(fruits["b"])  // Ausgabe: Banane

    // Elemente entfernen
    fruits.remove("b")
    
    // Über Map iterieren
    for ((key, value) in fruits) {
        println("$key -> $value")
    }
    // Beispiel-Ausgabe:
    // a -> Apfel
    // o -> Orange
    // g -> Traube
}
```

## Tiefer eintauchen

Kotlins Maps stammen direkt aus seiner Interoperabilität mit Java, wo Maps ein wesentlicher Teil der Sammlungen sind. Allerdings verbessert Kotlin ihre Benutzbarkeit, indem es sowohl veränderbare (`MutableMap`) als auch schreibgeschützte (`Map`) Schnittstellen anbietet, im Gegensatz zu Javas einheitlicher `Map` Schnittstelle. Diese Unterscheidung macht klar, ob eine Sammlung für Modifikationen vorgesehen ist oder nicht.

Ein wesentliches Detail über Kotlins Map-Implementierung ist die explizite Unterscheidung zwischen veränderbaren und unveränderbaren Maps, was den Fokus der Sprache auf Unveränderlichkeit und Thread-Sicherheit betont.

Obwohl Maps hochgradig nützlich sind, bietet Kotlin auch andere Sammlungen wie Listen und Sets, die jeweils ihren eigenen Anwendungsfall haben. Beispielsweise bewahren Listen die Reihenfolge und erlauben Dubletten, was sie ideal für den Zugriff auf Elemente nach Index macht, während Sets Einzigartigkeit sicherstellen, aber keine Reihenfolge bewahren. Die Wahl zwischen der Verwendung einer Map, Liste oder eines Sets hängt von den spezifischen Anforderungen Ihrer Anwendung ab, wie die Notwendigkeit des schlüsselbasierten Zugriffs oder der Reihenfolgeerhaltung.

In Bezug auf bessere Alternativen, wenn Leistung entscheidend ist, besonders bei großen Sammlungen, erwägen Sie die Verwendung von spezialisierten, effizienteren Datenstrukturen, die von externen Bibliotheken bereitgestellt werden und für bestimmte Anwendungsfälle optimiert sind, wie beispielsweise den gleichzeitigen Zugriff oder das Sortieren.
