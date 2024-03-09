---
title:                "Interpolando uma string"
date:                  2024-03-08T21:54:48.075967-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## O Que e Por Quê?

A interpolação de strings é o processo de injetar valores de variáveis diretamente em strings, muitas vezes para criar mensagens significativas sem concatenações complicadas. Programadores fazem isso para obter um código mais limpo, mais legível e para prevenir erros propensos a acontecer em concatenações complexas de strings.

## Como Fazer:

No Dart, a interpolação de strings é direta, utilizando o símbolo `$` para interpolar expressões diretamente dentro de literais de string:

```dart
void main() {
  String nome = 'Dart';
  int ano = 2023;
  // Interpolação simples de variável
  print('Aprendendo $nome em $ano!');
  // Saída: Aprendendo Dart em 2023!
  
  // Interpolando expressões
  print('Em dois anos, será ${ano + 2}.');
  // Saída: Em dois anos, será 2025.
}
```

No caso em que você tem expressões mais complexas ou quer realizar operações dentro da própria string, encerre a expressão em `${}`. Dart não possui bibliotecas de terceiros populares especificamente para interpolação de strings já que está bem equipado nativamente para lidar com cenários variados e complexos.
