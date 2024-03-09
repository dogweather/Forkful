---
title:                "Pesquisando e substituindo texto"
date:                  2024-03-08T21:56:38.810348-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## O quê & Por quê?

Buscar e substituir texto em Dart envolve examinar strings para encontrar padrões ou sequências de caracteres e substituí-los por novo conteúdo. Essa operação é fundamental para tarefas como validação de dados, formatação de saída, análise de entrada do usuário, ou até mesmo manipulação de URLs e caminhos de arquivos, tornando as aplicações mais dinâmicas e responsivas às necessidades do usuário.

## Como fazer:

Dart oferece métodos robustos para buscar e substituir texto diretamente por meio de sua classe `String`, sem a necessidade de bibliotecas externas. Veja como você pode fazer isso:

### Busca e Substituição Básicas

Para buscar uma substring e substituí-la por outra string, você pode usar `replaceAll`:

```dart
String textoExemplo = "Olá, Dart! Dart é ótimo.";
String textoModificado = textoExemplo.replaceAll("Dart", "Flutter");
print(textoModificado); // Saída: Olá, Flutter! Flutter é ótimo.
```

### Usando Expressões Regulares

Para necessidades de busca e substituição mais complexas, Dart utiliza expressões regulares através da classe `RegExp`. Isso permite a correspondência de padrões e substituição em strings:

```dart
String textoExemplo = "Dart 2023, Flutter 2023";
String textoModificado = textoExemplo.replaceAll(RegExp(r'\d+'), "2024");
print(textoModificado); // Saída: Dart 2024, Flutter 2024
```

Este exemplo encontra todas as instâncias de um ou mais dígitos (`\d+`) na string e as substitui por "2024".

### Busca Insensível a Maiúsculas e Minúsculas

Para realizar uma busca que não diferencia maiúsculas de minúsculas, você pode modificar o construtor `RegExp` para ignorar a diferença:

```dart
String textoExemplo = "Bem-vindo ao Dart, a linguagem de programação.";
String textoModificado = textoExemplo.replaceAll(RegExp(r'dart', caseSensitive: false), "Flutter");
print(textoModificado); // Saída: Bem-vindo ao Flutter, a linguagem de programação.
```

### Substituindo com uma Função

Para substituições dinâmicas baseadas na própria correspondência, Dart permite passar uma função para `replaceAllMapped`. Esta função pode executar operações ou cálculos nas sequências correspondidas:

```dart
String textoExemplo = "Incremente 5 por 1 para obter 6.";
String textoIncrementado = textoExemplo.replaceAllMapped(RegExp(r'\d+'), (Match m) => (int.parse(m[0]!) + 1).toString());
print(textoIncrementado); // Saída: Incremente 6 por 1 para obter 7.
```

Isso substitui cada sequência de dígitos pelo seu valor incrementado. Cada correspondência é analisada como um inteiro, incrementada e, em seguida, convertida de volta para uma string para substituição.

As capacidades de manipulação de strings do Dart, particularmente para busca e substituição de texto, tornam-no uma ferramenta poderosa para processar e preparar dados dentro de suas aplicações. Seja usando substituições de string diretas ou aproveitando o poder das expressões regulares, Dart oferece a flexibilidade e desempenho necessários para uma manipulação de texto eficaz.
