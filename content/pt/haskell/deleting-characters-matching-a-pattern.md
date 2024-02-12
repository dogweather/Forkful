---
title:                "Excluindo caracteres que correspondem a um padrão"
aliases:
- pt/haskell/deleting-characters-matching-a-pattern.md
date:                  2024-01-20T17:42:17.469328-07:00
model:                 gpt-4-1106-preview
simple_title:         "Excluindo caracteres que correspondem a um padrão"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/haskell/deleting-characters-matching-a-pattern.md"
---

{{< edit_this_page >}}

## O Que & Porquê?

Eliminar caracteres que correspondem a um padrão é o processo de remover seletivamente certos caracteres de uma string com base em critérios definidos. Por exemplo, podem-se remover todos os dígitos ou espaços de uma string. Programadores fazem isso para limpar dados, validar input, ou para preparar strings para processamento adicional.

## Como fazer:

```Haskell
import Data.Char (isSpace, isDigit)
import Data.List (partition)

-- Remove caracteres que são dígitos
removeDigitos :: String -> String
removeDigitos = filter (not . isDigit)

-- Remove espaços em branco
removeEspacos :: String -> String
removeEspacos = filter (not . isSpace)

-- Exemplo de uso
main :: IO ()
main = do
    let texto = "Haskell 2023, a linguagem funcional!"
    putStrLn $ removeDigitos texto
    putStrLn $ removeEspacos texto
```

Saída de exemplo:
```
Haskell , a linguagem funcional!
Haskell2023,alinguagemfuncional!
```

## Aprofundamento

Historicamente, operar em strings sempre foi parte essencial das tarefas de computação, desde a criação de mecanismos de busca a linguagens como Perl que são famosas pelo seu poderoso suporte a expressões regulares. Em Haskell, embora não haja um suporte tão imediato para regex quanto em Perl, a linguagem oferece funções puras e de alta ordem, como `filter`, para manipulação de strings de maneira concisa e expressiva.

Alternativas incluem o uso de expressões regulares com o pacote `regex-tdfa`, que oferece uma maior flexibilidade e potência para padrões mais complexos. Porém, isso adiciona complexidade e pode ser exagero para tarefas simples.

Implementar a remoção de caracteres é direto usando `filter`, particionando a string original com `partition` ou utilizando list comprehensions. Haskell oferece uma vantagem através de suas funções de ordem superior, tornando essas operações simples e com performance otimizada devido à preguiça inerente da linguagem, que avalia expressões somente quando necessárias.

## Veja Também

- [Haskell docs on filter](https://hackage.haskell.org/package/base-4.16.1.0/docs/Prelude.html#v:filter)
- [Learn You a Haskell for Great Good! - Functors, Applicative Functors and Monoids](http://learnyouahaskell.com/functors-applicative-functors-and-monoids)
- [Haddock Documentation for regex-tdfa](https://hackage.haskell.org/package/regex-tdfa)
