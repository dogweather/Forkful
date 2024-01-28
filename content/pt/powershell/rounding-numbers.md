---
title:                "Arredondamento de números"
date:                  2024-01-26T03:46:17.864731-07:00
model:                 gpt-4-0125-preview
simple_title:         "Arredondamento de números"
programming_language: "PowerShell"
category:             "PowerShell"
tag:                  "Numbers"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/powershell/rounding-numbers.md"
---

{{< edit_this_page >}}

## O Que & Por Que?
Arredondar números consiste em ajustar um valor para o inteiro mais próximo ou para um ponto decimal especificado. Programadores arredondam números para simplificar dados, melhorar a legibilidade ou atender determinados requisitos matemáticos durante cálculos.

## Como fazer:
Você tem à disposição alguns cmdlets e métodos úteis no PowerShell para arredondamento:

- Método `Round()` da classe Math
```PowerShell
[Math]::Round(15.68) # Arredonda para 16
```
- Especificar decimais:
```PowerShell
[Math]::Round(15.684, 2) # Arredonda para 15.68
```
- `Ceiling()` e `Floor()`, para arredondar sempre para cima ou para baixo:
```PowerShell
[Math]::Ceiling(15.2) # Arredonda para cima para 16
[Math]::Floor(15.9) # Arredonda para baixo para 15
```

## Aprofundamento
Arredondar números não é algo novo; existe desde os tempos antigos, útil para comércio, ciência e controle do tempo. Falando sobre o PowerShell, `[Math]::Round()` segue o "Arredondamento do Banqueiro" por padrão, onde os 0.5 vão para o número par mais próximo, reduzindo o viés em operações estatísticas.

Você não está limitado apenas aos métodos `[Math]` porém. Quer mais controle? Confira `[System.Math]::Round(Number, Digits, MidpointRounding)` onde você pode definir como os pontos médios são tratados: para longe de zero ou para o par (também conhecido como Arredondamento do Banqueiro).

Outro aspecto: o objeto `System.Globalization.CultureInfo`. Ele ajuda com a formatação específica de localidade e preferências de arredondamento ao lidar com números internacionais.

## Veja Também
- Documentação oficial da Microsoft sobre métodos Math: [Link](https://learn.microsoft.com/pt-br/dotnet/api/system.math?view=net-7.0)
- Especificidades do arredondamento decimal no .NET: [Link](https://learn.microsoft.com/pt-br/dotnet/api/system.midpointrounding?view=net-7.0)
- Discussões sobre arredondamento no StackOverflow: [Link](https://stackoverflow.com/questions/tagged/rounding+powershell)
