---
date: 2024-01-20 17:52:41.876850-07:00
description: "A impress\xE3o de sa\xEDda de depura\xE7\xE3o envolve exibir valores\
  \ intermedi\xE1rios para entender o comportamento do programa. Programadores o fazem\
  \ para encontrar e\u2026"
lastmod: '2024-03-13T22:44:46.627804-06:00'
model: gpt-4-1106-preview
summary: "A impress\xE3o de sa\xEDda de depura\xE7\xE3o envolve exibir valores intermedi\xE1\
  rios para entender o comportamento do programa."
title: "Exibindo sa\xEDdas de depura\xE7\xE3o"
weight: 33
---

## How to:
Em Haskell, vamos usar a função `print` para saída de depuração. Veja como:

```Haskell
main :: IO ()
main = do
  let x = 5
  print x  -- Imprime o valor de x
  let y = 7
  print (x + y)  -- Imprime a soma de x e y
```

Saída esperada:

```
5
12
```

## Deep Dive
Haskell, sendo uma linguagem funcional, normalmente desencoraja efeitos colaterais como a impressão de saída, mas reconhece sua utilidade para depuração. Inicialmente, você pode pensar em usar `putStrLn`, mas isso só funciona para `String`. A função `print` é mais geral porque funciona para qualquer valor que seja uma instância de `Show`.

Alternativas incluem o uso de bibliotecas de depuração, como `Debug.Trace`, que oferece a função `trace` para inserir pontos de depuração sem modificar a estrutura de tipos de seu programa.

Detalhes de implementação importantes: a função `print` é essencialmente um atalho para `putStrLn . show`, que primeiro converte o valor em uma `String` e então o imprime na saída padrão.

## See Also
Para expandir seu conhecimento, confira estes links:
- Documentação da função `print`: https://hackage.haskell.org/package/base-4.16.1.0/docs/Prelude.html#v:print
- Documentação de `Debug.Trace`: https://hackage.haskell.org/package/base/docs/Debug-Trace.html
- Haskell Wiki sobre depuração: https://wiki.haskell.org/Debugging
