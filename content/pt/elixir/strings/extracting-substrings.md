---
aliases:
- /pt/elixir/extracting-substrings/
date: 2024-01-20 17:45:25.152230-07:00
description: "Extrair substrings significa pegar peda\xE7os espec\xEDficos de uma\
  \ string. Programadores fazem isso para manipular, analisar dados ou simplesmente\
  \ para\u2026"
lastmod: 2024-02-18 23:08:57.833331
model: gpt-4-1106-preview
summary: "Extrair substrings significa pegar peda\xE7os espec\xEDficos de uma string.\
  \ Programadores fazem isso para manipular, analisar dados ou simplesmente para\u2026"
title: Extraindo substrings
---

{{< edit_this_page >}}

## O Que & Por Quê?
Extrair substrings significa pegar pedaços específicos de uma string. Programadores fazem isso para manipular, analisar dados ou simplesmente para destacar informações importantes dentro de um texto maior.

## Como Fazer:
```elixir
string_original = "Olá, mundo Elixir!"
# Extraindo substrings pela posição
substring1 = String.slice(string_original, 0, 3) # "Olá"
substring2 = String.slice(string_original, 5, 5) # "mundo"

IO.puts(substring1) # Saída: Olá
IO.puts(substring2) # Saída: mundo

# Usando padrões para limites de corte
{substring3, _} = String.split(string_original, "mundo")
IO.puts(substring3) # Saída: Olá, 
```

## Aprofundamento
Historicamente, a manipulação de strings sempre foi vital na programação. Em linguagens mais antigas, era um processo manual e propenso a erros. Com o Elixir, que foi lançado oficialmente em 2011, manipular strings é mais seguro e expressivo graças ao uso de padrões e funções bem construídas no módulo `String`. Alternativas incluem usar expressões regulares ou até outras funções como `String.trim/2` e `String.replace/3` para ajustes mais finos. A implementação no Elixir beneficia-se da máquina virtual Erlang (BEAM) e sua habilidade em lidar com dados binários, o que torna a operação de extrair substrings eficiente e rápida mesmo com texto grande.

## Veja Também
- [Documentação oficial do Elixir sobre Strings](https://hexdocs.pm/elixir/String.html)
- [Guia de Programação Elixir](https://elixir-lang.org/getting-started/binaries-strings-and-char-lists.html)
