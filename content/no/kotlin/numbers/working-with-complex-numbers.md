---
date: 2024-01-26 04:42:52.970110-07:00
description: "Komplekse tall utvider v\xE5rt tallsystem til \xE5 inkludere kvadratroten\
  \ av negative tall, hvor den 'imagin\xE6re' enheten i er lik kvadratroten av -1.\u2026"
lastmod: '2024-03-13T22:44:40.743975-06:00'
model: gpt-4-0125-preview
summary: "Komplekse tall utvider v\xE5rt tallsystem til \xE5 inkludere kvadratroten\
  \ av negative tall, hvor den 'imagin\xE6re' enheten i er lik kvadratroten av -1."
title: "\xC5 jobbe med komplekse tall"
weight: 14
---

## Hvordan:
La oss definere en grunnleggende klasse for komplekse tall i Kotlin:

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

## Dypdykk
Komplekse tall ble først nevnt på 1500-tallet, for å løse kube-ligninger som manglet reelle løsninger. Ingeniørfag og fysikk har enormt stor fordel av komplekse tall for å analysere vekselstrømskretser og bølgeformer. Du kunne alternativt bruke et bibliotek som Kotlin sitt `koma` eller `ejml` for tungt arbeid.

Operasjoner på komplekse tall speiler reelle tall, men med oppmerksomhet til den imaginære enheten. Multiplikasjon, for eksempel, følger distribusjonsegenskapen, og husker at `i^2 = -1`. Denne imaginære enheten gjør det mulig for oss å representere flerdimensjonale tall, avgjørende i ulike vitenskapelige beregninger.

## Se også
Kotlin Matematikkbiblioteker:

- [koma](https://koma.kyonifer.com/): Et vitenskapelig databehandlingsbibliotek for Kotlin.

Videre lesning om Komplekse Tall:

- [Wikipedia: Komplekse Tall](https://no.wikipedia.org/wiki/Komplekst_tall)
