---
title:                "Analisando HTML"
date:                  2024-03-08T21:55:53.200638-07:00
model:                 gpt-4-0125-preview
changelog:
  - 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
---

{{< edit_this_page >}}

## O Que & Por Quê?
Analisar (ou "parsear") HTML na programação envolve extrair dados de documentos HTML. Os programadores fazem isso para interagir com ou raspar conteúdo da web para extração de informações, testes ou propósitos de automação, mesmo quando APIs oficiais não estão disponíveis.

## Como fazer:
Dart não oferece suporte integrado para análise de HTML em suas bibliotecas principais. No entanto, você pode usar um pacote de terceiros como `html` para analisar e manipular documentos HTML.

Primeiro, adicione o pacote `html` ao seu arquivo `pubspec.yaml`:

```yaml
dependencies:
  html: ^0.15.0
```

Em seguida, importe o pacote para o seu arquivo Dart:

```dart
import 'package:html/parser.dart' show parse;
import 'package:html/dom.dart';
```

Aqui está um exemplo básico de análise de uma string contendo HTML e extração de dados:

```dart
void main() {
  var htmlDocument = """
  <html>
    <body>
      <h1>Olá, Dart!</h1>
      <p>Este é um parágrafo em um HTML de exemplo</p>
    </body>
  </html>
  """;

  // Analisar a string HTML
  Document document = parse(htmlDocument);

  // Extraindo dados
  String titulo = document.querySelector('h1')?.text ?? "Nenhum título encontrado";
  String paragrafo = document.querySelector('p')?.text ?? "Nenhum parágrafo encontrado";

  print('Título: $titulo');
  print('Parágrafo: $paragrafo');
}
```

Saída:

```
Título: Olá, Dart!
Parágrafo: Este é um parágrafo em um HTML de exemplo
```

Para interagir com páginas web reais, você pode combinar a análise de `html` com solicitações HTTP (usando o pacote `http` para buscar conteúdo web). Aqui está um exemplo rápido:

Primeiro, adicione o pacote `http` junto com `html`:

```yaml
dependencies:
  html: ^0.15.0
  http: ^0.13.3
```

Em seguida, busque e analise uma página HTML da web:

```dart
import 'package:http/http.dart' as http;
import 'package:html/parser.dart' show parse;

void main() async {
  var url = 'https://example.com';
  
  // Buscar a página web
  var response = await http.get(Uri.parse(url));
  
  if (response.statusCode == 200) {
    var document = parse(response.body);

    // Suponha que a página tenha tags <h1> de seu interesse
    var manchetes = document.querySelectorAll('h1').map((e) => e.text).toList();
    
    print('Manchetes: $manchetes');
  } else {
    print('A solicitação falhou com o status: ${response.statusCode}.');
  }
}
```

Nota: A técnica de raspagem da web mostrada acima deve ser usada de maneira responsável e em conformidade com os termos de serviço do website.
