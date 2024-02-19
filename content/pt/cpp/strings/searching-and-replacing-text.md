---
aliases:
- /pt/cpp/searching-and-replacing-text/
date: 2024-01-20 17:57:32.096500-07:00
description: "Procurar e substituir texto \xE9 a arte de achar certas palavras ou\
  \ frases e troc\xE1-las por outras. Programadores fazem isso para corrigir erros,\
  \ atualizar\u2026"
lastmod: 2024-02-18 23:08:58.435469
model: gpt-4-1106-preview
summary: "Procurar e substituir texto \xE9 a arte de achar certas palavras ou frases\
  \ e troc\xE1-las por outras. Programadores fazem isso para corrigir erros, atualizar\u2026"
title: Pesquisando e substituindo texto
---

{{< edit_this_page >}}

## O Quê & Por Quê?
Procurar e substituir texto é a arte de achar certas palavras ou frases e trocá-las por outras. Programadores fazem isso para corrigir erros, atualizar código ou dados, e tornar o conteúdo consistente sem perder tempo.

## Como Fazer:
```C++
#include <iostream>
#include <string>
#include <algorithm>

int main() {
    std::string texto = "O sol na minha terra natal é intenso e quente.";
    
    // Procura e substitui a palavra 'sol' pela palavra 'lua'
    std::string palavraProcurada = "sol";
    std::string novaPalavra = "lua";
    size_t posicao = texto.find(palavraProcurada);
    
    if (posicao != std::string::npos) {
        texto.replace(posicao, palavraProcurada.length(), novaPalavra);
    }
    
    std::cout << texto << std::endl; // "O lua na minha terra natal é intenso e quente."
    
    return 0;
}
```

## Mergulho Profundo:
Procurar e substituir textos é fundamental desde os primórdios da edição de texto, sendo essencial em editores como sed e vim. Alternativas modernas incluem expressões regulares para substituições complexas e funções como `std::regex_replace` em C++. A implementação manual pode usar `std::string::find` e `std::string::replace`, mas é importante lidar com a possibilidade da string procurada não ser encontrada, para evitar substituições incorretas.

## Veja Também:
- [cppreference.com - std::string::find](https://en.cppreference.com/w/cpp/string/basic_string/find)
- [cppreference.com - std::string::replace](https://en.cppreference.com/w/cpp/string/basic_string/replace)
- [cplusplus.com - Regular Expressions in C++](http://www.cplusplus.com/reference/regex/)
