---
title:                "Utilizando arrays associativos"
aliases:
- /pt/c/using-associative-arrays/
date:                  2024-02-03T18:10:44.658219-07:00
model:                 gpt-4-0125-preview
simple_title:         "Utilizando arrays associativos"
tag:                  "Data Structures"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pt/c/using-associative-arrays.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## O Que & Por Que?

Arrays associativos, conhecidos em outras linguagens como mapas ou dicionários, são pares de chave-valor usados para a busca e manipulação eficiente de dados. Diferentemente dos arrays tradicionais que usam índices inteiros, os arrays associativos utilizam chaves, tornando o acesso aos dados mais intuitivo e flexível para os programadores.

## Como fazer:

C não possui suporte embutido para arrays associativos como algumas linguagens de mais alto nível, mas você pode simulá-los usando estruturas e hashing. Abaixo está um exemplo simplista usando uma combinação de uma struct e uma função de hashing simples para implementar um array associativo para armazenar e acessar inteiros por chaves de string.

Primeiro, defina uma estrutura para representar um único par chave-valor e outra para representar o próprio array associativo:

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define TABLE_SIZE 128

typedef struct {
    char* chave;
    int valor;
} ParChaveValor;

typedef struct {
    ParChaveValor* itens[TABLE_SIZE];
} ArrayAssoc;

unsigned int hash(char* chave) {
    unsigned long int valor = 0;
    unsigned int i = 0;
    unsigned int comprimento_chave = strlen(chave);

    for (; i < comprimento_chave; ++i) {
        valor = valor * 37 + chave[i];
    }

    valor = valor % TABLE_SIZE;

    return valor;
}

void initArray(ArrayAssoc* array) {
    for (int i = 0; i < TABLE_SIZE; ++i) {
        array->itens[i] = NULL;
    }
}

void inserir(ArrayAssoc* array, char* chave, int valor) {
    unsigned int slot = hash(chave);

    ParChaveValor* item = (ParChaveValor*)malloc(sizeof(ParChaveValor));
    item->chave = strdup(chave);
    item->valor = valor;

    array->itens[slot] = item;
}

int encontrar(ArrayAssoc* array, char* chave) {
    unsigned int slot = hash(chave);

    if (array->itens[slot]) {
        return array->itens[slot]->valor;
    }
    return -1;
}

int main() {
    ArrayAssoc a;
    initArray(&a);

    inserir(&a, "chave1", 1);
    inserir(&a, "chave2", 2);

    printf("%d\n", encontrar(&a, "chave1")); // Saída: 1
    printf("%d\n", encontrar(&a, "chave2")); // Saída: 2

    return 0;
}
```

Este exemplo demonstra operações básicas: inicializando um array associativo, inserindo pares chave-valor e encontrando valores pelas chaves. Note que este código não trata colisões e é destinado a fins educacionais.

## Aprofundando

O conceito de arrays associativos antecede a linguagem C, mas a natureza de baixo nível da linguagem não os suporta diretamente como tipos embutidos. Isso encoraja um entendimento mais profundo das estruturas de dados e algoritmos, incluindo mecanismos de hashing para mapeamento eficiente de chave-valor. Muitas bibliotecas e frameworks de C oferecem abordagens mais sofisticadas para implementar arrays associativos, como o `GHashTable` da GLib, que fornece uma implementação robusta completada com tratamento de colisões, redimensionamento dinâmico e suporte para tipos de chaves e valores arbitrários.

Embora a construção manual de arrays associativos em C possa ser vista como trabalhosa comparada a linguagens com suporte embutido, ela oferece insights inestimáveis sobre o funcionamento interno das estruturas de dados, aprimorando as habilidades de resolução de problemas e otimização dos programadores. No entanto, para códigos de produção ou aplicações mais complexas, aproveitar bibliotecas existentes como a GLib geralmente é uma abordagem mais prática e eficiente em termos de tempo.
