---
aliases:
- /de/kotlin/using-a-debugger/
date: 2024-01-26 03:49:54.318756-07:00
description: "Sich in einen Debugger einzuarbeiten bedeutet, Schritt f\xFCr Schritt\
  \ durch den Code zu gehen, die Abl\xE4ufe zu beobachten und diese l\xE4stigen Fehler\
  \ auf\u2026"
lastmod: 2024-02-18 23:09:04.831281
model: gpt-4-0125-preview
summary: "Sich in einen Debugger einzuarbeiten bedeutet, Schritt f\xFCr Schritt durch\
  \ den Code zu gehen, die Abl\xE4ufe zu beobachten und diese l\xE4stigen Fehler auf\u2026"
title: Einsatz eines Debuggers
---

{{< edit_this_page >}}

## Was & Warum?
Sich in einen Debugger einzuarbeiten bedeutet, Schritt für Schritt durch den Code zu gehen, die Abläufe zu beobachten und diese lästigen Fehler auf frischer Tat zu ertappen. Programmierer nutzen Debugger, weil sie die Detektivwerkzeuge sind, die uns helfen herauszufinden, wo die Dinge schiefgehen, ohne uns die Haare raufen zu müssen.

## Wie:
Hier ist ein kleiner Vorgeschmack darauf, wie man in Kotlin mit IntelliJ IDEA debuggt - dem Sherlock Holmes der IDEs:

```kotlin
fun main() {
    val mysteryNumber = 42
    var guess = 0

    while (guess != mysteryNumber) {
        println("Rate die Zahl: ")
        guess = readLine()?.toIntOrNull() ?: continue // Ignoriere schlechte Eingaben

        // Setze hier einen Haltepunkt, um 'guess' in Aktion zu sehen
        if (guess < mysteryNumber) {
            println("Zu niedrig!")
        } else if (guess > mysteryNumber) {
            println("Zu hoch!")
        }
    }

    println("Du hast es! Die geheimnisvolle Zahl war $mysteryNumber")
}
```

Debugger-Ausgabe:
```
Rate die Zahl: 
10
Zu niedrig!
Rate die Zahl: 
50
Zu hoch!
Rate die Zahl: 
42
Du hast es! Die geheimnisvolle Zahl war 42
```

## Tiefer eintauchen
Debugger sind seit den 50er Jahren im Spiel. Damals waren sie ziemlich primitiv, und das Debugging konnte mehr mit der Hardware als mit der Software zu tun haben. Heutzutage ermöglicht uns ein Debugger wie der in IntelliJ IDEA, Haltepunkte zu setzen, Schritt für Schritt durch den Code zu gehen und zu unserer Freizeit den Zustand von Variablen zu inspizieren.

Obwohl der Debugger von IntelliJ für Kotlin super praktisch ist, ist er nicht der einzige Fisch im Meer. Es gibt eine Reihe von Alternativen wie Logcat für die Android-Entwicklung oder Befehlszeilen-Tools wie jdb für die Minimalisten. Die Magie unter der Haube handelt hier größtenteils von der JVM Tool Interface (JVMTI), die es Debuggern erlaubt, mit der Java Virtual Machine zu interagieren und Kotlin-Entwickler im Loop zu halten.

## Siehe auch
- IntelliJ IDEA Debugger-Dokumentation: [https://jetbrains.com/idea/](https://www.jetbrains.com/idea/features/debugger.html)
