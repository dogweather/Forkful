---
date: 2024-01-20 17:38:36.900227-07:00
description: "Converter uma string para min\xFAsculas \xE9 transformar todos os caracteres\
  \ alfab\xE9ticos dela em suas vers\xF5es min\xFAsculas. Programadores fazem isso\
  \ para\u2026"
lastmod: '2024-03-13T22:44:46.612850-06:00'
model: gpt-4-1106-preview
summary: "Converter uma string para min\xFAsculas \xE9 transformar todos os caracteres\
  \ alfab\xE9ticos dela em suas vers\xF5es min\xFAsculas."
title: "Convertendo uma string para min\xFAsculas"
weight: 4
---

## Como fazer:
Vamos usar a biblioteca `Data.Char` para converter strings para minúsculas em Haskell:

```haskell
import Data.Char (toLower)

-- Converte uma string para minúsculas
toLowerCase :: String -> String
toLowerCase = map toLower

-- Exemplo de uso
main = putStrLn (toLowerCase "Olá Mundo!")
```

Saída do exemplo:
```
olá mundo!
```

## Aprofundando
Haskell tem uma abordagem funcional interessante para operações como essa. Originalmente, a função `toLower` foi introduzida na biblioteca `Data.Char`, que faz parte do Prelude do Haskell, a biblioteca padrão que é automaticamente importada.

Alternativas para essa operação em Haskell poderiam envolver a escrita de uma função case-by-case manual, mas é desnecessário dada a existência da função pronta. Em termos de detalhes de implementação, `toLower` lida com o Unicode. No entanto, Haskell não realiza automaticamente a conversão de maiúsculas de títulos ou letras especiais que podem ter regras de caixa baixa específicas de localidade (às vezes necessárias para além do ASCII).

## Veja Também
Para explorar mais sobre strings e caracteres em Haskell:

- A documentação da biblioteca `Data.Char`: https://hackage.haskell.org/package/base-4.16.0.0/docs/Data-Char.html
- Haskell Wiki sobre strings: https://wiki.haskell.org/Working_with_strings
- Para um entendimento mais complexo de manipulação de texto Unicode em Haskell, a biblioteca `text`: https://hackage.haskell.org/package/text
