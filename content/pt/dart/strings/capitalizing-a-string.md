---
title:                "Capitalizando uma string"
date:                  2024-03-08T21:53:52.918660-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## O Quê & Porquê?

Colocar em maiúscula uma string envolve modificar a primeira letra de uma palavra ou de uma frase inteira para maiúscula, mantendo o resto dos caracteres como estão. Programadores frequentemente utilizam essa técnica para formatar entradas de usuário ou exibir texto para assegurar consistência ou aderir a regras gramaticais em interfaces de usuário.

## Como Fazer:

### Usando Métodos Incorporados do Dart

O Dart fornece métodos simples e diretos para manipulação de strings. Para colocar uma palavra ou uma frase em maiúscula, você normalmente pegaria o primeiro caractere, converteria ele para maiúsculo, e depois o concatenaria com o resto da string. Aqui está como você poderia implementar isso:

```dart
String capitalize(String text) {
  if (text.isEmpty) return text;
  return text[0].toUpperCase() + text.substring(1).toLowerCase();
}

void main() {
  var exemplo = "ola mundo";
  print(capitalize(exemplo)); // Saída: Ola mundo
}
```

### Colocando em Maiúscula Cada Palavra

Para colocar em maiúscula a primeira letra de cada palavra em uma string, você poderia dividir a string em palavras, colocar cada uma em maiúscula, e depois juntá-las novamente:

```dart
String capitalizeWords(String text) {
  return text.split(' ').map(capitalize).join(' ');
}

void main() {
  var exemplo = "ola entusiastas do dart";
  print(capitalizeWords(exemplo)); // Saída: Ola Entusiastas Do Dart
}
```

### Usando Bibliotecas de Terceiros

Enquanto a biblioteca padrão do Dart cobre as necessidades básicas, certas tarefas podem ser realizadas de forma mais conveniente usando pacotes de terceiros. Uma escolha popular para recursos de manipulação de string ampliados, incluindo capitalização, é o pacote [`recase`](https://pub.dev/packages/recase). Após adicioná-lo ao `pubspec.yaml` do seu projeto, você pode facilmente colocar strings em maiúscula entre outras funcionalidades:

```dart
import 'package:recase/recase.dart';

void main() {
  var exemplo = "ola mundo";
  var rc = ReCase(exemplo);

  print(rc.titleCase); // Saída: Ola Mundo
}
```

Usando `recase`, você pode colocar em maiúscula palavras individuais, frases inteiras, ou até seguir outras convenções de maiúsculas sem manusear manualmente as transformações de string.
