---
title:                "Escrevendo um arquivo de texto"
date:                  2024-03-08T21:57:58.913275-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## O que & Por quê?
Escrever um arquivo de texto em Dart envolve criar ou modificar arquivos no disco para armazenar dados de forma legível. Programadores fazem isso para salvar dados de aplicativos, configurações, logs ou qualquer informação que deva persistir entre execuções do aplicativo ou compartilhar dados com outros aplicativos ou usuários.

## Como fazer:
A biblioteca principal do Dart fornece o pacote `dart:io` para manipulação de arquivos, permitindo que você escreva arquivos de texto sem a necessidade de bibliotecas de terceiros. Aqui está um exemplo simples de como escrever um arquivo de texto:

```dart
import 'dart:io';

void main() async {
  // Cria um novo arquivo chamado 'example.txt' no diretório atual.
  var file = File('example.txt');
  
  // Escreve uma string no arquivo.
  await file.writeAsString('Olá, Dart!');
  
  // Verifica o conteúdo.
  print(await file.readAsString()); // Saída: Olá, Dart!
}
```

Ao lidar com arquivos maiores ou fluxos de dados, você pode preferir escrever o conteúdo usando `openWrite`, que retorna um `IOSink` e permite escrever dados em pedaços:

```dart
import 'dart:io';

void main() async {
  var file = File('large_file.txt');
  var sink = file.openWrite();

  // Escreve várias linhas no arquivo.
  sink
    ..writeln('Linha 1: A rápida raposa marrom pula sobre o cão preguiçoso.')
    ..writeln('Linha 2: Dart é incrível!')
    ..close();

  // Espera pelo fechamento do sink para garantir que todos os dados sejam escritos no arquivo.
  await sink.done;

  // Lê e imprime o conteúdo do arquivo para verificar
  print(await file.readAsString());
}
```

Para operações de arquivo mais avançadas, incluindo adicionar a arquivos ou escrever bytes, você pode explorar mais profundamente os métodos da classe `File` fornecidos por `dart:io`. Além disso, ao trabalhar em projetos de grande escala ou mais complexos, considerar pacotes como `path` para lidar com caminhos de arquivo ou `shelf` para funcionalidades de servidor web pode ser benéfico, embora a escrita direta de arquivos normalmente dependa das bibliotecas internas do Dart.
