---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 18:07:39.600736-07:00
description: "Arredondar n\xFAmeros \xE9 o processo de ajustar os d\xEDgitos de um\
  \ n\xFAmero para reduzir sua precis\xE3o de acordo com certas regras, seja em dire\xE7\
  \xE3o ao n\xFAmero\u2026"
lastmod: '2024-03-13T22:44:47.044203-06:00'
model: gpt-4-0125-preview
summary: "Arredondar n\xFAmeros \xE9 o processo de ajustar os d\xEDgitos de um n\xFA\
  mero para reduzir sua precis\xE3o de acordo com certas regras, seja em dire\xE7\xE3\
  o ao n\xFAmero inteiro mais pr\xF3ximo ou a um n\xFAmero especificado de casas decimais."
title: "Arredondamento de n\xFAmeros"
weight: 13
---

## Como Fazer:
Arredondar números em C pode ser realizado usando várias funções, mas a abordagem mais comum envolve as funções `floor()`, `ceil()` e `round()`. Estas funções fazem parte da biblioteca padrão de matemática, então você precisará incluir `math.h` em seu programa.

```c
#include <stdio.h>
#include <math.h>

int main() {
    double num = 9.527;

    // Usando floor() para arredondar para baixo
    double floorResult = floor(num);
    printf("floor(9.527) = %.0f\n", floorResult);

    // Usando ceil() para arredondar para cima
    double ceilResult = ceil(num);
    printf("ceil(9.527) = %.0f\n", ceilResult);

    // Usando round() para arredondar para o inteiro mais próximo
    double roundResult = round(num);
    printf("round(9.527) = %.0f\n", roundResult);

    // Arredondando para um número especificado de casas decimais envolve multiplicação e divisão
    double twoDecimalPlaces = round(num * 100) / 100;
    printf("Arredondando para duas casas decimais: %.2f\n", twoDecimalPlaces);

    return 0;
}
```

Saída:
```
floor(9.527) = 9
ceil(9.527) = 10
round(9.527) = 10
Arredondando para duas casas decimais: 9.53
```

## Aprofundamento
Arredondar números tem raízes históricas profundas na matemática e computação, integral tanto aos aspectos teóricos quanto aplicados. Em C, embora `floor()`, `ceil()` e `round()` ofereçam funcionalidade básica, a essência de arredondar floats para inteiros ou casas decimais específicas é mais matizada devido à representação binária dos números de ponto flutuante. Esta representação pode levar a resultados inesperados devido à forma como números que não podem ser precisamente representados em binário (como 0.1) são tratados.

Essas funções fazem parte da biblioteca padrão C, definidas em `<math.h>`. Ao arredondar números, especialmente para cálculos financeiros ou de engenharia precisos, deve-se considerar as implicações do uso de números de ponto flutuante binário. Alternativas às funções incorporadas em C para arredondamentos altamente precisos ou específicos para decimais podem incluir a implementação de funções de arredondamento personalizadas ou o uso de bibliotecas projetadas para aritmética de precisão arbitrária, como GMP ou MPFR, embora essas introduzam complexidade e dependências adicionais.

Na prática, escolher a abordagem correta para o arredondamento em C envolve equilibrar a necessidade de precisão, desempenho e praticidade, com uma compreensão aguçada dos requisitos específicos do domínio da aplicação que está sendo desenvolvida.
