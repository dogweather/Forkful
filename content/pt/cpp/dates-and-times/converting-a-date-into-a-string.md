---
date: 2024-01-20 17:36:15.831387-07:00
description: "Converter uma data em string significa transformar uma representa\xE7\
  \xE3o de data (geralmente um tipo espec\xEDfico como `std::chrono::system_clock::time_point`)\u2026"
lastmod: '2024-03-13T22:44:46.890730-06:00'
model: gpt-4-1106-preview
summary: "Converter uma data em string significa transformar uma representa\xE7\xE3\
  o de data (geralmente um tipo espec\xEDfico como `std::chrono::system_clock::time_point`)\
  \ em texto (string) que \xE9 leg\xEDvel por humanos."
title: Convertendo uma data em uma string
weight: 28
---

## Como Fazer:
```cpp
#include <iostream>
#include <iomanip>
#include <chrono>
#include <sstream>

int main() {
    // Pegando a data/hora atual usando chrono
    auto agora = std::chrono::system_clock::now();
    std::time_t tempo_atual = std::chrono::system_clock::to_time_t(agora);
    
    // Convertendo para string usando <iomanip>
    std::stringstream ss;
    ss << std::put_time(std::localtime(&tempo_atual), "%Y-%m-%d %H:%M:%S");
    
    // Exibindo a data/hora como string
    std::cout << "Data e hora atuais: " << ss.str() << std::endl;
    
    return 0;
}
```
Saída de exemplo:
```
Data e hora atuais: 2023-01-31 14:55:13
```

## Mergulho Profundo:
Converter datas em strings é uma necessidade antiga em programação. Inicialmente, lidávamos com datas por meio de estruturas `struct tm` da biblioteca de tempo C. Atualmente em C++, temos `std::chrono` que foi introduzido com C++11 e aperfeiçoado ao longo dos anos, mais recentemente em C++20. Alternativas históricas incluíam o uso de bibliotecas de terceiros como a Boost.DateTime.

Por detalhes de implementação, `std::put_time` da biblioteca `<iomanip>` é comumente usado para formatar datas em C++. Ainda assim, pode-se usar funções de estilo C como `strftime` para realizar tarefas similares. Atenção à portabilidade e à localização ao converter datas em strings: formatações e fusos horários podem variar. C++20 introduziu novas abordagens, como `std::format`, que simplifica ainda mais a formatação de strings, mas ainda não havia sido amplamente adotada até o conhecimento atual.

## Veja Também:
- Documentação oficial do CPP sobre `<chrono>`: https://en.cppreference.com/w/cpp/chrono
- Documentação oficial do CPP sobre `<iomanip>`: https://en.cppreference.com/w/cpp/io/manip
- Biblioteca Boost.DateTime: https://www.boost.org/doc/libs/release/libs/date_time/
- LearnCpp sobre conversão de datas para strings em C++: https://www.learncpp.com/cpp-tutorial/date-and-time/
