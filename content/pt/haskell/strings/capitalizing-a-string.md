---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:05:17.825846-07:00
description: "Capitalizar uma string envolve transformar a primeira letra de uma string\
  \ dada em mai\xFAscula, enquanto garante que as restantes letras permane\xE7am em\u2026"
lastmod: '2024-03-13T22:44:46.609175-06:00'
model: gpt-4-0125-preview
summary: "Capitalizar uma string envolve transformar a primeira letra de uma string\
  \ dada em mai\xFAscula, enquanto garante que as restantes letras permane\xE7am em\
  \ min\xFAscula."
title: Capitalizando uma string
weight: 2
---

## Como fazer:
Em Haskell, você pode capitalizar uma string usando a biblioteca padrão sem a necessidade de quaisquer bibliotecas de terceiros.

```haskell
import Data.Char (toUpper, toLower)

capitalize :: String -> String
capitalize "" = ""
capitalize (head:tail) = toUpper head : map toLower tail

-- Uso de exemplo:
main = putStrLn $ capitalize "hello world"
```

Saída:
```
Hello world
```

Para cenários mais complexos ou facilidade de uso, você pode querer usar uma biblioteca de terceiros, como `text`, que é popular para manipulação eficiente de strings em Haskell.

Primeiro, você precisa adicionar `text` às dependências do seu projeto. Então, você pode usar suas funções para capitalizar uma string da seguinte forma:

```haskell
import qualified Data.Text as T
import Data.Char (toUpper)

capitalizeText :: T.Text -> T.Text
capitalizeText text = case T.uncons text of
    Nothing -> T.empty
    Just (first, rest) -> T.cons (toUpper first) (T.toLower rest)

-- Uso de exemplo com a biblioteca text:
main = putStrLn $ T.unpack $ capitalizeText (T.pack "hello world")
```

Saída:
```
Hello world
```

Ambos estes exemplos demonstram formas simples, porém efetivas, de capitalizar uma string em Haskell, com ou sem bibliotecas de terceiros.
