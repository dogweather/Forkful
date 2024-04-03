---
changelog:
- 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-08 21:53:59.740307-07:00
description: "Converter uma string para letras min\xFAsculas \xE9 uma opera\xE7\xE3\
  o fundamental que envolve transformar todos os caracteres de uma string dada em\
  \ seus equivalentes\u2026"
lastmod: '2024-03-13T22:44:46.267421-06:00'
model: gpt-4-0125-preview
summary: "Converter uma string para letras min\xFAsculas \xE9 uma opera\xE7\xE3o fundamental\
  \ que envolve transformar todos os caracteres de uma string dada em seus equivalentes\
  \ em min\xFAscula."
title: "Convertendo uma string para letras min\xFAsculas"
weight: 4
---

## Como fazer:
No Dart, você pode converter uma string para minúscula usando o método `toLowerCase()` fornecido pela classe `String`. Este método retorna uma nova string com todos os caracteres em maiúscula convertidos para minúscula. Vamos ver como isso funciona com um exemplo simples:

```dart
void main() {
  String originalString = "Hello, World!";
  String lowerCaseString = originalString.toLowerCase();

  print(lowerCaseString);  // Saída: hello, world!
}
```

O Dart não requer bibliotecas externas para tarefas básicas de manipulação de string, incluindo a conversão para minúscula, visto que a classe `String` da biblioteca padrão é bastante abrangente. No entanto, para manipulações mais complexas envolvendo regras específicas de localidade, você pode considerar o pacote `intl`, que fornece facilidades de internacionalização e localização, incluindo a conversão de caixa baseada em localidade:

Para usar o `intl`, adicione-o ao seu arquivo `pubspec.yaml`:

```yaml
dependencies:
  intl: ^0.17.0
```

Então, você pode usar o método `toLocaleLowerCase()` para converter uma string para minúscula com base em localidades específicas:

```dart
import 'package:intl/intl.dart';

void main() {
  String originalString = "İstanbul";
  
  // Localidade Turca
  print(Intl.withLocale('tr', () => originalString.toLowerCase())); // Saída: istanbul
  
  // Localidade Padrão (en)
  print(originalString.toLowerCase()); // Saída: i̇stanbul
}
```

Neste exemplo, observe como a localidade turca lida corretamente com o 'i' sem ponto, destacando a importância das transformações conscientes de localidade em aplicações internacionalizadas.
