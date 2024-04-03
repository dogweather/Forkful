---
date: 2024-01-26 04:43:02.987590-07:00
description: "Komplexa tal ut\xF6kar v\xE5rt talsystem f\xF6r att inkludera kvadratr\xF6\
  tter av negativa tal, d\xE4r den 'imagin\xE4ra' enheten i motsvarar kvadratroten\
  \ av -1.\u2026"
lastmod: '2024-03-13T22:44:37.865338-06:00'
model: gpt-4-0125-preview
summary: "Komplexa tal ut\xF6kar v\xE5rt talsystem f\xF6r att inkludera kvadratr\xF6\
  tter av negativa tal, d\xE4r den 'imagin\xE4ra' enheten i motsvarar kvadratroten\
  \ av -1."
title: Att arbeta med komplexa tal
weight: 14
---

## Hur man gör:
Låt oss definiera en grundläggande klass för komplexa tal i Kotlin:

```kotlin
data class Complex(val real: Double, val imaginary: Double) {
    operator fun plus(other: Complex) = Complex(real + other.real, imaginary + other.imaginary)
    operator fun minus(other: Complex) = Complex(real - other.real, imaginary - other.imaginary)
    operator fun times(other: Complex) = Complex(
        real * other.real - imaginary * other.imaginary,
        real * other.imaginary + imaginary * other.real
    )
    
    override fun toString(): String = "($real + ${imaginary}i)"
}

fun main() {
    val a = Complex(1.0, 2.0)
    val b = Complex(3.0, 4.0)
    
    println("a + b = ${a + b}")  // Utdata: a + b = (4.0 + 6.0i)
    println("a - b = ${a - b}")  // Utdata: a - b = (-2.0 - 2.0i)
    println("a * b = ${a * b}")  // Utdata: a * b = (-5.0 + 10.0i)
}
```

## Fördjupning
Komplexa tal nämndes först på 1500-talet när det löste kubiska ekvationer som saknade reella lösningar. Teknik och fysik drar stor nytta av komplexa tal för att analysera växelströmskretsar och vågformer. Alternativt kan du använda ett bibliotek som Kotlin's `koma` eller `ejml` för arbete som kräver mer kraft.

Operationer på komplexa tal speglar de reella talen, men med uppmärksamhet på den imaginära enheten. Multiplikation följer till exempel distributiva egenskapen, med minnet av att `i^2 = -1`. Denna imaginära enhet gör det möjligt för oss att representera flerdimensionella tal, vilka är avgörande i olika vetenskapliga beräkningar.

## Se även
Kotlin Matematikbibliotek:

- [koma](https://koma.kyonifer.com/): Ett vetenskapligt beräkningsbibliotek för Kotlin.

Fördjupad läsning om Komplexa Tal:

- [Wikipedia: Komplexa Tal](https://en.wikipedia.org/wiki/Complex_number)
