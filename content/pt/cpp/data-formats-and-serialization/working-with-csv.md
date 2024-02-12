---
title:                "Trabalhando com CSV"
aliases:
- pt/cpp/working-with-csv.md
date:                  2024-02-03T19:19:01.868413-07:00
model:                 gpt-4-0125-preview
simple_title:         "Trabalhando com CSV"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/cpp/working-with-csv.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## O quê e Por quê?

Trabalhar com arquivos CSV (Valores Separados por Vírgula) é sobre processar e manipular dados armazenados em um formato de texto simples, onde cada linha do texto representa uma linha em uma tabela, e vírgulas separam as colunas individuais. Programadores utilizam isso para importar, exportar e gerenciar dados entre diferentes sistemas devido à ampla aceitação do CSV como um formato de intercâmbio de dados leve e legível por humanos.

## Como fazer:

### Lendo um arquivo CSV usando a Biblioteca Padrão do C++:

```cpp
#include <fstream>
#include <iostream>
#include <sstream>
#include <vector>

int main() {
    std::ifstream file("data.csv");
    std::string line;
    
    while (std::getline(file, line)) {
        std::stringstream lineStream(line);
        std::string cell;
        std::vector<std::string> parsedRow;
        
        while (std::getline(lineStream, cell, ',')) {
            parsedRow.push_back(cell);
        }
        
        // Processar parsedRow aqui
        for (const auto& val : parsedRow) {
            std::cout << val << "\t";
        }
        std::cout << std::endl;
    }
    
    return 0;
}
```

### Escrevendo em um arquivo CSV:

```cpp
#include <fstream>
#include <vector>

int main() {
    std::ofstream file("output.csv");
    std::vector<std::vector<std::string>> dados = {
        {"Nome", "Idade", "Cidade"},
        {"John Doe", "29", "Nova York"},
        {"Jane Smith", "34", "Los Angeles"}
    };
    
    for (const auto& linha : dados) {
        for (size_t i = 0; i < linha.size(); i++) {
            file << linha[i];
            if (i < linha.size() - 1) file << ",";
        }
        file << "\n";
    }
    
    return 0;
}
```

### Usando uma biblioteca de terceiros: `csv2`:

Enquanto a Biblioteca Padrão do C++ fornece as ferramentas básicas para trabalhar com arquivos e strings, utilizar bibliotecas de terceiros pode simplificar o processamento de CSV. Uma dessas bibliotecas é a `csv2`, conhecida por sua facilidade de uso e eficiência.

- Instalação: Geralmente instalada via gerenciadores de pacotes como Conan ou diretamente de seu repositório no GitHub.

Exemplo usando `csv2` para ler um arquivo CSV:

```cpp
#include <csv2/reader.hpp>
#include <iostream>

int main() {
    csv2::Reader<csv2::delimiter<','>, csv2::quote_character<'"'>, csv2::first_row_is_header<true>> csv;
    if (csv.mmap("data.csv")) {
        const auto cabeçalho = csv.header();
        for (const auto linha : csv) {
            for (const auto célula : linha) {
                std::cout << célula.second << "\t"; // Exibir o valor de cada célula
            }
            std::cout << std::endl;
        }
    }
    return 0;
}
```

A saída de amostra para operações de leitura pode parecer assim (assumindo um arquivo CSV simples de três colunas):

```
John    29    Nova York    
Jane    34    Los Angeles
```

Estes exemplos visam cobrir operações fundamentais com CSV em C++. Para cenários mais complexos, como lidar com arquivos grandes ou transformações de dados complexas, pode ser justificada uma exploração adicional em bibliotecas ou ferramentas especializadas.
