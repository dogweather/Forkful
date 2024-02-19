---
aliases:
- /pt/kotlin/using-an-interactive-shell-repl/
date: 2024-01-26 04:15:44.795715-07:00
description: "Um REPL (Read-Eval-Print Loop - Ciclo de Ler-Avaliar-Imprimir) \xE9\
  \ um ambiente de programa\xE7\xE3o de computadores interativo e simples. Os programadores\u2026"
lastmod: 2024-02-18 23:08:58.108226
model: gpt-4-0125-preview
summary: "Um REPL (Read-Eval-Print Loop - Ciclo de Ler-Avaliar-Imprimir) \xE9 um ambiente\
  \ de programa\xE7\xE3o de computadores interativo e simples. Os programadores\u2026"
title: Usando um shell interativo (REPL)
---

{{< edit_this_page >}}

## O Que & Por Que?
Um REPL (Read-Eval-Print Loop - Ciclo de Ler-Avaliar-Imprimir) é um ambiente de programação de computadores interativo e simples. Os programadores utilizam-no para testes rápidos de codificação, experimentação de trechos de código ou aprendizado da sintaxe de uma linguagem sem a necessidade de criar uma aplicação completa.

## Como Fazer:
Iniciar o REPL do Kotlin é muito fácil. Abra seu terminal e digite `kotlinc`. Você entrará no shell do Kotlin. Vamos tentar definir uma variável e imprimir seu valor:

```kotlin
Bem-vindo à versão do Kotlin 1.7.10 (JRE 1.8.0_292-b10)
Digite :help para ajuda, :quit para sair
>>> val saudacao = "Olá, REPL do Kotlin!"
>>> println(saudacao)
Olá, REPL do Kotlin!
```

## Mergulho Profundo
O REPL do Kotlin estreou com a linguagem para incentivar a experimentação. É semelhante ao shell interativo do Python, mas adaptado para a sintaxe e peculiaridades do Kotlin. Alternativas? Ambientes interativos em IDEs, como IntelliJ IDEA, e playgrounds online do Kotlin. O REPL funciona compilando o código em tempo real, fornecendo feedback instantâneo – crucial para aprendizado e depuração.

## Veja Também
- Documentação do Kotlin sobre REPL: [https://kotlinlang.org/docs/command-line.html#run-the-repl](https://kotlinlang.org/docs/command-line.html#run-the-repl)
- Experimente Kotlin no navegador: [https://play.kotlinlang.org](https://play.kotlinlang.org)
- Plugin Kotlin Playground da JetBrains para IntelliJ IDEA.
