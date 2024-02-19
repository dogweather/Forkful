---
aliases:
- /nl/kotlin/writing-tests/
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:13:11.932403-07:00
description: "Testen schrijven betekent code scripten om te checken of andere code\
  \ goed werkt. Programmeurs doen dit om vroegtijdig fouten op te sporen, tijd te\u2026"
lastmod: 2024-02-18 23:09:01.809600
model: gpt-4-0125-preview
summary: "Testen schrijven betekent code scripten om te checken of andere code goed\
  \ werkt. Programmeurs doen dit om vroegtijdig fouten op te sporen, tijd te\u2026"
title: Tests Schrijven
---

{{< edit_this_page >}}

## Wat & Waarom?
Testen schrijven betekent code scripten om te checken of andere code goed werkt. Programmeurs doen dit om vroegtijdig fouten op te sporen, tijd te besparen en te zorgen dat de software consistent doet wat het moet doen.

## Hoe:
Kotlin gebruikt JUnit voor het testen. Hier is hoe je een eenvoudige test schrijft en uitvoert:

```kotlin
import org.junit.Assert.assertEquals
import org.junit.Test

class CalculatorTest {
    
    @Test
    fun `voegt twee nummers samen`() {
        assertEquals(4, Calculator.add(2, 2))
    }
}

object Calculator {
    fun add(a: Int, b: Int) = a + b
}
```

Voer het uit. Als je uitvoer er zo uitziet, zit je goed:

```
Test geslaagd
```

## Diepere Duik
JUnit, het standaard framework voor testen in Kotlin, gaat terug tot Java. Alternatieve testframeworks zijn Spek en Kotest, elk met hun eigen syntax en functies. Testen schrijven omvat vaak het begrijpen van de SUT (System Under Test) structuur, afhankelijkheden nabootsen met MockK of vergelijkbaar, en het kennen van het verschil tussen unit-, integratie-, en functionele tests.

## Zie Ook
- JUnit 5 Gebruikersgids: [junit.org/junit5/docs/current/user-guide/](https://junit.org/junit5/docs/current/user-guide/)
- MockK Bibliotheek: [mockk.io](https://mockk.io)
- Spek Framework: [spekframework.org](https://spekframework.org)
- Kotest: [kotest.io](https://kotest.io)
