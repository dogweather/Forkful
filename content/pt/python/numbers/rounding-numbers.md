---
date: 2024-01-26 03:46:14.077472-07:00
description: "Arredondar n\xFAmeros significa ajust\xE1-los para que fiquem mais pr\xF3\
  ximos de um valor mais simples ou significativo. Programadores arredondam n\xFA\
  meros para\u2026"
lastmod: '2024-03-13T22:44:46.148678-06:00'
model: gpt-4-0125-preview
summary: "Arredondar n\xFAmeros significa ajust\xE1-los para que fiquem mais pr\xF3\
  ximos de um valor mais simples ou significativo."
title: "Arredondamento de n\xFAmeros"
weight: 13
---

## Como Fazer:
Aqui está o essencial sobre arredondamento de números em Python:

```python
# Arredondar um número para o inteiro mais próximo
print(round(8.67))  # Saída: 9

# Arredondar um número para um número especificado de casas decimais
print(round(8.67, 1))  # Saída: 8.7

# Números pares são arredondados para baixo e ímpares são arredondados para cima quando equidistantes
print(round(2.5))  # Saída: 2
print(round(3.5))  # Saída: 4
```

## Aprofundando
Em Python, a função `round()` não está apenas cortando decimais. Historicamente, Python, assim como muitas outras linguagens, segue o "arredondamento pela metade até o par" ou "arredondamento do banqueiro". Isso minimiza o erro cumulativo em somas ou médias, o que é importante em cálculos financeiros.

Para alternativas, você tem `math.floor()` e `math.ceil()` do módulo de matemática do Python, arrastando números para baixo ou para cima até o próximo número inteiro. Mas, se precisão é o que você procura, `quantize()` do módulo `decimal` permite especificar o comportamento de arredondamento.

Por baixo dos panos, `round()` lida com números de ponto flutuante binários. Como alguns decimais não podem ser expressos exatamente em binário, você pode se surpreender com coisas como `round(2.675, 2)` não se tornando `2.68` como esperado. Aí entram `decimal` ou `fractions` para alta precisão.

## Veja Também
- Documentação do Python sobre funções incorporadas: https://docs.python.org/3/library/functions.html#round
- Aritmética de ponto fixo e ponto flutuante decimal: https://docs.python.org/3/library/decimal.html
- Módulo de matemática do Python: https://docs.python.org/3/library/math.html
