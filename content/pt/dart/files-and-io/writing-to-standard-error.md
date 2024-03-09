---
title:                "Escrevendo para o erro padrão"
date:                  2024-03-08T21:57:59.178142-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## O Quê & Porquê?

Escrever para o erro padrão (stderr) em Dart consiste em enviar mensagens de erro e diagnósticos para um fluxo separado, distinto da saída padrão (stdout). Programadores fazem isso para diferenciar entre a saída normal do programa e os erros ou mensagens de aviso, permitindo um depuração e registro de logs mais fácil.

## Como Fazer:

Em Dart, escrever para o stderr é direto usando o objeto `stderr` disponível em `dart:io`. Aqui está um exemplo básico:

```dart
import 'dart:io';

void main() {
  stderr.writeln('Esta é uma mensagem de erro.');
}
```

Saída ao executar:
```
Esta é uma mensagem de erro.
```
Essa mensagem é enviada para o fluxo stderr, que é tipicamente exibido no console ou terminal.

Para demonstrar mais complexidade, como registrar uma exceção, o rico conjunto de funcionalidades do Dart permite um tratamento de erros conciso e eficaz:

```dart
import 'dart:io';

void riskyOperation() {
  try {
    // Simula uma operação que pode lançar uma exceção
    throw Exception('Algo deu errado!');
  } catch (e) {
    stderr.writeln('Erro: $e');
  }
}

void main() {
  riskyOperation();
}
```

Saída ao executar:
```
Erro: Exception: Algo deu errado!
```

Esse padrão é especialmente útil para aplicações que precisam separar logs normais de logs de erro, facilitando o monitoramento e a depuração de aplicações.

Embora a biblioteca padrão do Dart seja bastante abrangente, muitos programas não requerem bibliotecas de terceiros para escrever no stderr. No entanto, se sua aplicação precisa de capacidades de registro mais sofisticadas (por exemplo, para arquivos, pela rede, formatação), o pacote `logging` é uma escolha popular. Aqui está uma rápida olhada em como usar `logging` para erros:

```dart
import 'dart:io';
import 'package:logging/logging.dart';

final logger = Logger('MyAppLogger');

void setupLogging() {
  logger.onRecord.listen((record) {
    if (record.level >= Level.SEVERE) {
      stderr.writeln('${record.level.name}: ${record.time}: ${record.message}');
    }
  });
}

void main() {
  setupLogging();
  logger.severe('Erro Grave: Algo significativamente ruim aconteceu.');
}
```

Saída ao executar:
```
SEVERE: 2023-04-01 00:00:00.000: Erro Grave: Algo significativamente ruim aconteceu.
```

Este método oferece um grau maior de personalização e controle sobre o que é registrado como um erro e como é formatado, o que pode ser muito útil em aplicações maiores e mais complexas.
