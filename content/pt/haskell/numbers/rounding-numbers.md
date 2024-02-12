---
title:                "Arredondamento de números"
aliases:
- /pt/haskell/rounding-numbers/
date:                  2024-01-26T03:44:49.932659-07:00
model:                 gpt-4-0125-preview
simple_title:         "Arredondamento de números"

tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/haskell/rounding-numbers.md"
---

{{< edit_this_page >}}

## O Que & Por Quê?

Arredondar números significa ajustá-los ao inteiro mais próximo ou à casa decimal especificada. Programadores arredondam números para controlar precisão, adaptar saídas para apresentação ao usuário, ou reduzir custos de computação para operações com ponto flutuante.

## Como fazer:

Haskell usa as funções `round`, `ceiling`, `floor` e `truncate` do `Prelude` para operações de arredondamento.

```haskell
import Prelude

main :: IO ()
main = do
  let num = 3.567
  print $ round num    -- 4
  print $ ceiling num  -- 4
  print $ floor num    -- 3
  print $ truncate num -- 3
  
  -- Arredondar para uma casa decimal específica não está no Prelude.
  -- Aqui está uma função personalizada:
  let roundTo n f = (fromInteger $ round $ f * (10^n)) / (10.0^^n)
  print $ roundTo 1 num -- 3.6
```

## Aprofundamento

Historicamente, arredondar é significativo na análise numérica e ciência da computação porque é crucial para minimizar a acumulação de erro em computações, particularmente antes das representações de ponto flutuante serem padronizadas com IEEE 754.

Para que arredondar? `round` te leva ao inteiro mais próximo—para cima ou para baixo. `ceiling` e `floor` sempre arredondam para cima ou para baixo até o inteiro mais próximo, respectivamente, enquanto `truncate` simplesmente descarta os pontos decimais.

Alternativas a estas funções podem envolver lógica personalizada, como nosso `roundTo`, ou você pode incorporar bibliotecas (como Data.Fixed) para requisitos mais complexos.

Cuidado com resultados inesperados devido à forma como Haskell lida com casos de meio termo em `round` (ele arredonda para o número par mais próximo).

## Veja Também

- Documentação do Haskell Prelude para funções de arredondamento: https://hackage.haskell.org/package/base-4.16.1.0/docs/Prelude.html
- A Wiki do Haskell sobre aritmética de ponto flutuante: https://wiki.haskell.org/Floating_point_arithmetic
- Norma IEEE 754-2008 para mais informações sobre como o ponto flutuante é tratado em muitas linguagens: https://ieeexplore.ieee.org/document/4610935
