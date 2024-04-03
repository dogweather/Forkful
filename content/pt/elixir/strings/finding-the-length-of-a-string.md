---
date: 2024-01-20 17:47:15.037114-07:00
description: "Encontrar o comprimento de uma string \xE9 b\xE1sicamente medir quantos\
  \ caracteres ela possui. Programadores fazem isso para validar entradas, definir\
  \ limites\u2026"
lastmod: '2024-03-13T22:44:46.229337-06:00'
model: gpt-4-1106-preview
summary: "Encontrar o comprimento de uma string \xE9 b\xE1sicamente medir quantos\
  \ caracteres ela possui."
title: Descobrindo o comprimento de uma string
weight: 7
---

## Como Fazer:
```elixir
# 1. Usando a função String.length/1
comprimento = String.length("Olá, mundo!")
IO.puts(comprimento)  # Saída: 10

# 2. Contagem de caracteres Unicode válidos, não apenas bytes
comprimento_unicode = String.length("✈️🌍")
IO.puts(comprimento_unicode)  # Saída: 2
```

## Aprofundamento
Historicamente, a contagem de caracteres em uma string é uma operação comum em programação, mas ganhou complexidades com a adoção do padrão Unicode. No Elixir, a String é um módulo potente que lida com UTF-8, garantindo que a contagem de caracteres seja precisa, respeitando pontos de código Unicode e não simplesmente contando bytes. Alternativas como `byte_size/1` podem ser utilizadas quando a contagem de bytes é necessária ao invés de caracteres.

## Veja Também:
- [Documentação oficial do módulo String](https://hexdocs.pm/elixir/String.html)
- [Elixir School - Strings](https://elixirschool.com/pt/lessons/basics/strings/)
- [Entendendo Unicode e UTF-8](https://unicode.org/standard/WhatIsUnicode.html)
