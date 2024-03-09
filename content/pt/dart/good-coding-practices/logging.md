---
title:                "Registro"
date:                  2024-03-08T21:55:03.817842-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## O Que & Por Quê?

Registrar (logging) em Dart refere-se ao processo de gravação de vários níveis de informações durante a execução de um programa. Programadores fazem isso para monitorar o comportamento do software, depurar problemas e analisar o desempenho, facilitando a manutenção e a melhoria do aplicativo ao longo do tempo.

## Como fazer:

Dart inclui um mecanismo de registro simples através da biblioteca `dart:developer`. Para necessidades de registro mais sofisticadas, programadores costumam recorrer a bibliotecas de terceiros como `logger` e `log4dart`.

### Usando `dart:developer`
Isso é adequado para registro básico, especialmente durante o desenvolvimento:

```dart
import 'dart:developer';

void main() {
  log('Esta é uma mensagem de log de depuração.');
}
```

Saída:
```
Esta é uma mensagem de log de depuração.
```

### Usando o pacote `logger`
Para uma solução mais abrangente, o pacote `logger` oferece vários níveis de registro (por exemplo, info, warning, error) e pode ser formatado de maneira mais legível.

Primeiro, adicione a dependência `logger` no seu arquivo `pubspec.yaml`:

```yaml
dependencies:
  logger: ^1.0.0
```

Então, use-o da seguinte forma:

```dart
import 'package:logger/logger.dart';

var logger = Logger();

void main() {
  logger.d("Esta é uma mensagem de depuração");
  logger.w("Esta é uma mensagem de aviso");
  logger.e("Esta é uma mensagem de erro");
}
```

Uma amostra de saída pode parecer assim, com cada tipo de mensagem sendo formatado de forma diferente para fácil identificação:

```
💬 Esta é uma mensagem de depuração
⚠️ Esta é uma mensagem de aviso
❗️ Esta é uma mensagem de erro
```

### Usando o pacote `log4dart`
Para aplicações que requerem registro baseado em configuração (semelhante ao Log4j), `log4dart` oferece uma abordagem familiar. Isso é especialmente útil para aplicações em larga escala.

Certifique-se de incluir `log4dart` no seu `pubspec.yaml`:

```yaml
dependencies:
  log4dart: ^2.0.0
```

Um exemplo simples de uso:

```dart
import 'package:log4dart/log4dart.dart';

void main() {
  final logger = LoggerFactory.getLogger("MyApp");
  logger.debug("Depurando MyApp");
  logger.info("Mensagem informativa");
}
```

Saída:

```
DEBUG: Depurando MyApp
INFO: Mensagem informativa
```

Cada um desses métodos fornece um diferente nível de flexibilidade e complexidade, desde mensagens simples de depuração até registro abrangente e configurável adequado às necessidades de aplicações complexas.
