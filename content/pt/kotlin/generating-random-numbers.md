---
title:                "Geração de números aleatórios"
aliases:
- pt/kotlin/generating-random-numbers.md
date:                  2024-01-27T20:34:17.358717-07:00
model:                 gpt-4-0125-preview
simple_title:         "Geração de números aleatórios"

tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/kotlin/generating-random-numbers.md"
---

{{< edit_this_page >}}

## O Que e Por Quê?

Gerar números aleatórios em programação é sobre criar números que não têm qualquer padrão previsível. Programadores fazem isso por várias razões, incluindo simulações, teste de algoritmos, jogos e aplicações de segurança, onde a imprevisibilidade é chave para alcançar resultados realistas ou seguros.

## Como fazer:

Kotlin fornece uma maneira direta de gerar números aleatórios através de sua biblioteca padrão. Veja como você pode gerar diferentes tipos de valores aleatórios:

### Gerando um Inteiro Aleatório

Para gerar um inteiro aleatório dentro de um intervalo específico:

```kotlin
import kotlin.random.Random

fun main() {
    val randomNumber = Random.nextInt(1, 100) // Gera um número aleatório entre 1 e 99
    println(randomNumber)
}
```

### Gerando um Double Aleatório

De maneira similar, gerando um double aleatório:

```kotlin
import kotlin.random.Random

fun main() {
    val randomDouble = Random.nextDouble(1.0, 10.0) // Gera um double aleatório entre 1.0 e 10.0
    println(randomDouble)
}
```

### Gerando um Boolean Aleatório

Para gerar um valor booleano aleatório:

```kotlin
import kotlin.random.Random

fun main() {
    val randomBoolean = Random.nextBoolean() // Gera verdadeiro ou falso aleatoriamente
    println(randomBoolean)
}
```

### Semeadura para Resultados Reproduzíveis

Em casos onde você precisa de sequências reproduzíveis de números aleatórios (por exemplo, em testes), você pode semear o gerador de números aleatórios:

```kotlin
import kotlin.random.Random

fun main() {
    val seed = 12345L
    val random = Random(seed)
    val randomNumber = random.nextInt(1, 100)
    println(randomNumber)
}
```

## Aprofundando

A abordagem da biblioteca padrão do Kotlin para gerar números aleatórios utiliza por baixo dos panos o `java.util.Random` do Java, garantindo uma mistura de facilidade de uso e performance. No entanto, é crucial notar que esses métodos geram números pseudoaleatórios, o que significa que os números parecem aleatórios, mas são gerados usando um processo determinístico.

Para a maioria das aplicações, a aleatoriedade fornecida pela classe `Random` do Kotlin é suficiente. No entanto, para aplicações mais sensíveis à segurança, como a criptografia, onde a qualidade da aleatoriedade é primordial, deve-se considerar o uso de `java.security.SecureRandom` em vez disso. SecureRandom é especificamente projetado para operações criptográficas, fornecendo uma qualidade de aleatoriedade superior, embora com uma possível troca de performance.

Kotlin não reinventa a roda, mas oferece uma API amigável ao Kotlin sobre os mecanismos de geração de números aleatórios do Java, tornando-o mais idiomático e conciso para uso em projetos Kotlin. Como sempre, ao lidar com aleatoriedade, os programadores devem considerar cuidadosamente o caso de uso para escolher a ferramenta mais apropriada para o trabalho.
