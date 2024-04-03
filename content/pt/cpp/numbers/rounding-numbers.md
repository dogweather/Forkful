---
date: 2024-01-26 03:43:13.205364-07:00
description: "Arredondar n\xFAmeros significa ajustar um valor para o inteiro mais\
  \ pr\xF3ximo ou uma precis\xE3o especificada. Desenvolvedores fazem isso para simplificar,\u2026"
lastmod: '2024-03-13T22:44:46.874616-06:00'
model: gpt-4-0125-preview
summary: "Arredondar n\xFAmeros significa ajustar um valor para o inteiro mais pr\xF3\
  ximo ou uma precis\xE3o especificada."
title: "Arredondamento de n\xFAmeros"
weight: 13
---

## Como:
C++ oferece várias maneiras de arredondar números, como `floor()`, `ceil()`, e `round()`:

```C++
#include <iostream>
#include <cmath> // para funções de arredondamento

int main() {
    double num = 3.14;

    std::cout << "floor: " << std::floor(num) << "\n"; // Saída: floor: 3
    std::cout << "ceil: " << std::ceil(num) << "\n";   // Saída: ceil: 4
    std::cout << "round: " << std::round(num) << "\n"; // Saída: round: 3

    // Para precisão fixa, como arredondar para duas decimais:
    double precise_num = 3.146;
    double multiplicador = 100.0;
    double arredondado = std::round(precise_num * multiplicador) / multiplicador;

    std::cout << "arredondado para duas decimais: " << arredondado << "\n"; // Saída: arredondado para duas decimais: 3.15

    return 0;
}
```

## Mergulho Profundo
Antes do C++11, o arredondamento dependia de técnicas manuais ou bibliotecas não-padrão. Hoje, `<cmath>` fornece métodos robustos. `floor()` arredonda para baixo, `ceil()` arredonda para cima, enquanto `round()` vai para o inteiro mais próximo, lidando até com empates (casos de 0.5) arredondando para o número par.

Entender o comportamento dessas funções é crucial; por exemplo, números negativos podem confundir (`std::round(-2.5)` resulta em `-2.0`).

Alternativas? Converter para um int depois de adicionar 0.5 para números positivos era um truque clássico, mas erra com negativos e não é agnóstico de tipo. Bibliotecas como Boost podem oferecer abordagens mais refinadas, enquanto extensões de linguagem ou intrínsecos do compilador podem otimizar para hardware específico.

## Veja Também
- Referência C++ para `<cmath>`: https://en.cppreference.com/w/cpp/header/cmath
- Padrão IEEE para Aritmética de Pontos Flutuantes (IEEE 754): https://ieeexplore.ieee.org/document/4610935
- Biblioteca de Conversão Numérica Boost: https://www.boost.org/doc/libs/release/libs/numeric/conversion/
