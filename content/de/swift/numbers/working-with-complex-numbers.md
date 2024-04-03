---
date: 2024-01-26 04:45:46.646232-07:00
description: "Komplexe Zahlen bestehen aus einem Realteil und einem Imagin\xE4rteil\
  \ (wie 3 + 4i). Programmierer verwenden sie in Swift f\xFCr Aufgaben wie Signalverarbeitung,\u2026"
lastmod: '2024-03-13T22:44:54.219684-06:00'
model: gpt-4-0125-preview
summary: "Komplexe Zahlen bestehen aus einem Realteil und einem Imagin\xE4rteil (wie\
  \ 3 + 4i)."
title: Umgang mit komplexen Zahlen
weight: 14
---

## Wie geht das:
Swift hat keine eingebaute Unterstützung für komplexe Zahlen, aber wir können unsere eigene erstellen:

```Swift
struct ComplexNumber {
    var real: Double
    var imaginary: Double

    func add(_ other: ComplexNumber) -> ComplexNumber {
        return ComplexNumber(real: real + other.real, imaginary: imaginary + other.imaginary)
    }

    // Zusätzliche Methoden wie Subtraktion, Multiplikation usw.
}

let first = ComplexNumber(real: 2, imaginary: 3)
let second = ComplexNumber(real: 1, imaginary: 4)
let result = first.add(second)
print("Ergebnis: \(result.real) + \(result.imaginary)i")
// Beispiel-Ausgabe: Ergebnis: 3.0 + 7.0i
```

## Tiefergehend
Komplexe Zahlen tauchten im 16. Jahrhundert in algebraischen Gleichungen auf. Sie sind wesentlich in Quantenmechanik, Regelungstechnik und vielen anderen Bereichen. Apples Swift hat keine Standardbibliothek für komplexe Zahlen, anders als Sprachen wie Python oder C++. Alternativen zum eigenen Programmieren umfassen die Nutzung des Numerics-Pakets, das Unterstützung für komplexe Zahlen bietet oder das Einbinden der C++-Komplexbibliothek mit der Interoperabilität von Swift.

## Siehe auch
- Swift Numerics: [https://github.com/apple/swift-numerics](https://github.com/apple/swift-numerics)
