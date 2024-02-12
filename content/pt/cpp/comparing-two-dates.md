---
title:                "Comparando duas datas"
aliases:
- pt/cpp/comparing-two-dates.md
date:                  2024-01-20T17:32:45.133861-07:00
model:                 gpt-4-1106-preview
simple_title:         "Comparando duas datas"

tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/cpp/comparing-two-dates.md"
---

{{< edit_this_page >}}

## O Que & Porquê?
Comparar datas é verificar a relação temporal entre elas - qual é mais cedo ou mais tarde. Programadores fazem isso para ordenar eventos, validar períodos, e controlar a lógica que depende de tempo.

## Como Fazer:
```C++
#include <iostream>
#include <ctime>

int main() {
    // Duas datas diferentes
    std::tm time1 = {};
    std::tm time2 = {};

    // Definir a primeira data: 10 de Maio de 2022
    time1.tm_year = 122; // Ano desde 1900
    time1.tm_mon = 4;    // Mês (0-11)
    time1.tm_mday = 10;  // Dia do mês (1-31)

    // Definir a segunda data: 15 de Março de 2023
    time2.tm_year = 123; // Ano desde 1900
    time2.tm_mon = 2;    // Mês (0-11)
    time2.tm_mday = 15;  // Dia do mês (1-31)

    // Converter para tipo time_t
    time_t time1_t = std::mktime(&time1);
    time_t time2_t = std::mktime(&time2);

    if (difftime(time1_t, time2_t) > 0) {
        std::cout << "A primeira data é mais recente.\n";
    } else if (difftime(time1_t, time2_t) < 0) {
        std::cout << "A segunda data é mais recente.\n";
    } else {
        std::cout << "As datas são iguais.\n";
    }

    return 0;
}
```

Saída esperada:
```
A segunda data é mais recente.
```

## Mergulho Profundo
Antes do C++11, o manejo de data e hora não era padronizado e bibliotecas de terceiros eram comuns. Agora, C++ tem `<chrono>`, moderna e tipo-seguro. Alternativas incluem o uso de `<ctime>` (antigo `<time.h>`), como no exemplo acima, ou bibliotecas de terceiros como Boost.DateTime.

Comparar datas usando `<chrono>`:
```C++
#include <iostream>
#include <chrono>
#include <date/date.h>

int main() {
    using namespace date;
    using namespace std::chrono;

    // Duas datas com `<chrono>` e a biblioteca "date"
    auto date1 = 2022_y/may/10;
    auto date2 = 2023_y/march/15;

    if (date1 > date2) {
        std::cout << "A primeira data é mais recente.\n";
    } else if (date1 < date2) {
        std::cout << "A segunda data é mais recente.\n";
    } else {
        std::cout << "As datas são iguais.\n";
    }

    return 0;
}
```

A biblioteca `<chrono>` por si só não oferece uma forma direta de criar datas facilmente, por isso usamos a lib externa "date". Essa é uma das razões pelas quais muitos ainda preferem `<ctime>`.

## Veja Também
- Documentação do C++ `<chrono>`: https://en.cppreference.com/w/cpp/header/chrono
- Biblioteca Boost.DateTime: https://www.boost.org/doc/libs/release/libs/date_time/
- "date" library, uma extensão para `<chrono>`: https://github.com/HowardHinnant/date 
- CPPReference sobre `<ctime>`: https://en.cppreference.com/w/cpp/header/ctime
