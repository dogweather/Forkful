---
title:                "Enviando uma solicitação HTTP com autenticação básica"
date:                  2024-03-08T21:56:29.972768-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## O Que & Por Quê?

Enviar uma requisição HTTP com autenticação básica envolve anexar um nome de usuário e senha a uma requisição para verificar a identidade do usuário. Programadores usam isso para acessar recursos que requerem autenticação, garantindo comunicação segura entre o cliente e o servidor.

## Como fazer:

No Dart, você pode usar o pacote `http` para enviar requisições HTTP com autenticação básica. Primeiro, adicione o pacote `http` ao seu arquivo `pubspec.yaml`:

```yaml
dependencies:
  http: ^0.13.4
```

Depois, importe o pacote no seu arquivo Dart:

```dart
import 'package:http/http.dart' as http;
import 'dart:convert';
```

Para enviar uma requisição GET com autenticação básica, você pode usar o seguinte código:

```dart
Future<void> buscarDadosDoUsuario() async {
  final username = 'seuNomeDeUsuario';
  final password = 'suaSenha';
  final credenciais = base64Encode(utf8.encode('$username:$password'));
  final resposta = await http.get(
    Uri.parse('https://seuapi.com/dadosdousuario'),
    headers: {
      'Authorization': 'Basic $credenciais',
    },
  );

  if (resposta.statusCode == 200) {
    print('Dados do usuário buscados com sucesso!');
    print('Corpo da resposta: ${resposta.body}');
  } else {
    print('Falha ao buscar dados do usuário com o código de status: ${resposta.statusCode}');
  }
}
```

Este código envia uma requisição GET para 'https://seuapi.com/dadosdousuario' com um cabeçalho de autenticação básica. O nome de usuário e a senha são codificados em base64 e passados no cabeçalho 'Authorization' conforme os padrões de autenticação de acesso básico.

**Exemplo de saída:**

Após uma requisição bem-sucedida e se o servidor retornar um código de status 200, você pode ver:

```plaintext
Dados do usuário buscados com sucesso!
Corpo da resposta: {"id":1, "nome":"John Doe", "email":"john@example.com"}
```

Se a autenticação falhar ou houver qualquer outro erro, o código de status da resposta ajudará a identificar o problema.
