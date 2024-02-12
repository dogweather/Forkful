---
title:                "Arredondamento de números"
aliases:
- pt/kotlin/rounding-numbers.md
date:                  2024-01-26T03:45:44.465822-07:00
model:                 gpt-4-0125-preview
simple_title:         "Arredondamento de números"

tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/kotlin/rounding-numbers.md"
---

{{< edit_this_page >}}

## O Que e Por Quê?

Arredondar números significa ajustá-los ao número inteiro mais próximo ou a um grau especificado de precisão. Programadores fazem isso para melhorar a legibilidade, reduzir os requisitos de armazenamento ou porque o valor exato não é crítico para cálculos subsequentes.

## Como Fazer:

Em Kotlin, o arredondamento pode ser feito usando várias funções como `roundToInt()`, `roundToDouble()`, e usando `BigDecimal` para mais controle:

```kotlin
fun main() {
    val number1 = 3.14159
    println(number1.roundToInt()) // Saída: 3

    val number2 = 3.5
    println(number2.roundToInt()) // Saída: 4

    val number3 = 123.456
    println("%.2f".format(number3)) // Saída: 123.46
    
    val bigDecimal = number3.toBigDecimal().setScale(1, RoundingMode.HALF_EVEN)
    println(bigDecimal) // Saída: 123.5
}
```

## Aprofundando

Historicamente, arredondar números tem sido um conceito fundamental tanto em matemática quanto em computação, projetado para lidar com as limitações de precisão numérica. No início da computação, o arredondamento era crítico devido ao alto custo da memória.

Em Kotlin, o arredondamento é construído sobre as bibliotecas padrão Java. As opções para arredondamento incluem `Math.round()`, que arredonda para o número inteiro mais próximo, e `BigDecimal` para arredondamento personalizável, onde você pode especificar uma escala e um `RoundingMode`.

Cada `RoundingMode` tem políticas diferentes para lidar com empates (quando o dígito está exatamente no meio das opções de arredondamento). Por exemplo, `RoundingMode.HALF_UP` arredonda para o vizinho mais próximo, a menos que ambos os vizinhos estejam à mesma distância, caso em que arredonda para cima.

## Veja Também

- Documentação do Kotlin sobre [`BigDecimal`](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/java.math.-big-decimal/index.html)
- Documentação da Oracle sobre [`RoundingMode`](https://docs.oracle.com/javase/8/docs/api/java/math/RoundingMode.html)
- Padrão IEEE para Aritmética de Ponto Flutuante (IEEE 754) [Padrão IEEE 754](https://ieeexplore.ieee.org/document/4610935)
