---
date: 2024-01-27 20:34:17.772647-07:00
description: "Generowanie losowych liczb w programowaniu polega na tworzeniu liczb,\
  \ kt\xF3re nie wykazuj\u0105 \u017Cadnego przewidywalnego wzorca. Programi\u015B\
  ci robi\u0105 to z r\xF3\u017Cnych\u2026"
lastmod: '2024-03-13T22:44:35.360791-06:00'
model: gpt-4-0125-preview
summary: "Generowanie losowych liczb w programowaniu polega na tworzeniu liczb, kt\xF3\
  re nie wykazuj\u0105 \u017Cadnego przewidywalnego wzorca."
title: Generowanie liczb losowych
weight: 12
---

## Jak to zrobić:
Kotlin zapewnia prostą metodę generowania losowych liczb za pomocą swojej biblioteki standardowej. Oto jak możesz generować różne typy losowych wartości:

### Generowanie losowej liczby całkowitej
Aby wygenerować losową liczbę całkowitą w określonym zakresie:

```kotlin
import kotlin.random.Random

fun main() {
    val randomNumber = Random.nextInt(1, 100) // Generuje losową liczbę między 1 a 99
    println(randomNumber)
}
```

### Generowanie losowego Double
Podobnie, generowanie losowego double:

```kotlin
import kotlin.random.Random

fun main() {
    val randomDouble = Random.nextDouble(1.0, 10.0) // Generuje losowy double między 1.0 a 10.0
    println(randomDouble)
}
```

### Generowanie losowego Boolean
Aby wygenerować losową wartość logiczną (boolean):

```kotlin
import kotlin.random.Random

fun main() {
    val randomBoolean = Random.nextBoolean() // Generuje losowo prawda lub fałsz
    println(randomBoolean)
}
```

### Seeding dla reprodukowalnych wyników
W przypadkach, gdy potrzebujesz reprodukowalnych sekwencji losowych liczb (na przykład w testowaniu), możesz zasiać generator liczb losowych:

```kotlin
import kotlin.random.Random

fun main() {
    val seed = 12345L
    val random = Random(seed)
    val randomNumber = random.nextInt(1, 100)
    println(randomNumber)
}
```

## Dogłębna analiza
Podejście biblioteki standardowej Kotlin do generowania losowych liczb wykorzystuje pod spodem `java.util.Random`, zapewniając mieszankę łatwości użytkowania i wydajności. Jednakże, ważne jest, aby zauważyć, że te metody generują liczby pseudolosowe, co oznacza, że liczby wydają się losowe, ale są generowane za pomocą deterministycznego procesu.

Dla większości zastosowań, losowość zapewniana przez klasę `Random` w Kotlinie jest wystarczająca. Jednakże, dla aplikacji wymagających większego bezpieczeństwa, takich jak kryptografia, gdzie jakość losowości jest najważniejsza, należy rozważyć użycie `java.security.SecureRandom` zamiast tego. SecureRandom jest specjalnie zaprojektowany dla operacji kryptograficznych, zapewniając wyższą jakość losowości, choć potencjalnie kosztem wydajności.

Kotlin nie odkrywa koła na nowo, ale oferuje API przyjazne dla Kotlin nad mechanizmami generowania liczb losowych Java, czyniąc je bardziej idiomatycznymi i zwięzłymi do użycia w projektach Kotlin. Jak zawsze, kiedy mamy do czynienia z losowością, programiści powinni dokładnie rozważyć przypadek użycia, aby wybrać najbardziej odpowiednie narzędzie do zadania.
