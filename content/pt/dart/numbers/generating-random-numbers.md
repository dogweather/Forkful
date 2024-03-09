---
title:                "Gerando números aleatórios"
date:                  2024-03-08T21:54:35.006129-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## O Que & Por Que?
Gerar números aleatórios em Dart envolve a criação de valores numéricos que são imprevisíveis e diferem a cada execução. Os programadores aproveitam essa funcionalidade por uma variedade de razões, desde simular cenários do mundo real em ambientes de teste até habilitar mecânicas de jogos e garantir segurança através da aleatoriedade em operações criptográficas.

## Como fazer:

A biblioteca principal do Dart inclui suporte para a geração de números aleatórios com a classe `Random` encontrada em `dart:math`. Aqui está um exemplo básico:

```dart
import 'dart:math';

void main() {
  var rand = Random();
  int randomNumber = rand.nextInt(100); // Gera um inteiro aleatório entre 0 e 99
  double randomDouble = rand.nextDouble(); // Gera um double aleatório entre 0.0 e 1.0
  print(randomNumber);
  print(randomDouble);
}
```

*Saída de exemplo: (Isso variará cada vez que for executado)*

```
23
0.6722390975465775
```

Para casos de uso que requerem aleatoriedade criptográfica, Dart oferece o construtor `Random.secure`:

```dart
import 'dart:math';

void main() {
  var secureRand = Random.secure();
  int secureRandomNumber = secureRand.nextInt(100);
  print(secureRandomNumber);
}
```

*Saída de exemplo: (Isso variará cada vez que for executado)*

```
45
```

Se você está trabalhando em projetos Flutter ou precisa de mais complexidade na aleatoriedade, você pode achar útil o pacote `faker` para gerar uma ampla gama de dados aleatórios, como nomes, endereços e datas.

Para usar o `faker`, primeiro, adicione-o ao seu arquivo `pubspec.yaml`:

```yaml
dependencies:
  faker: ^2.0.0
```

Em seguida, importe e use conforme mostrado:

```dart
import 'package:faker/faker.dart';

void main() {
  final faker = Faker();
  print(faker.person.name()); // Gera um nome aleatório
  print(faker.address.city()); // Gera um nome de cidade aleatório
}
```

*Saída de exemplo:*

```
Josie Runolfsdottir
East Lysanne
```
