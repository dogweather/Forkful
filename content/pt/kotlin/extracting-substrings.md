---
title:                "Extraindo substrings"
aliases:
- pt/kotlin/extracting-substrings.md
date:                  2024-01-20T17:46:07.952590-07:00
model:                 gpt-4-1106-preview
simple_title:         "Extraindo substrings"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/kotlin/extracting-substrings.md"
---

{{< edit_this_page >}}

## O Quê & Por Quê?
Extrair substrings é pegar partes específicas de uma string. Programadores fazem isso quando precisam manipular ou analisar partes específicas de textos, como lidar com entradas de dados ou extrair informações relevantes.

## Como Fazer:
```Kotlin
fun main() {
    val texto = "Olá, programadores Kotlin!"
    val saudacao = texto.substring(0, 4)
    val foco = texto.substring(17, 23)
    
    println(saudacao)  // Output: Olá,
    println(foco)      // Output: Kotlin
}
```

## Mergulho Profundo:
Historicamente, manipular strings sempre foi uma parte crítica da programação, uma vez que muitos tipos de dados são expressos como texto. O método `substring` em Kotlin, que vem do Java, é um modo direto para realizar essa tarefa. Alternativas como o uso de expressões regulares (`Regex`) podem ser mais poderosas para padrões complexos, mas são exageradas para tarefas simples. Na implementação, o método `substring` pode ter impacto na performance se usado desmedidamente em strings muito grandes devido à criação de novos objetos de string em memória.

## Veja Também:
- Documentação oficial do Kotlin sobre String Operations: [Strings - Kotlin Programming Language](https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-string/)
- Kotlin Playground, onde você pode experimentar código Kotlin online: [Kotlin Playground](https://play.kotlinlang.org)
