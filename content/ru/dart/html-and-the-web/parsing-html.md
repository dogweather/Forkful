---
changelog:
- 2024-03-08, OpenAIModel.GPT_4_TURBO, translated from English
date: 2024-03-08 21:55:58.081239-07:00
description: "\u041F\u0430\u0440\u0441\u0438\u043D\u0433 HTML \u0432 \u043F\u0440\u043E\
  \u0433\u0440\u0430\u043C\u043C\u0438\u0440\u043E\u0432\u0430\u043D\u0438\u0438 \u0432\
  \u043A\u043B\u044E\u0447\u0430\u0435\u0442 \u0438\u0437\u0432\u043B\u0435\u0447\u0435\
  \u043D\u0438\u0435 \u0434\u0430\u043D\u043D\u044B\u0445 \u0438\u0437 HTML-\u0434\
  \u043E\u043A\u0443\u043C\u0435\u043D\u0442\u043E\u0432. \u041F\u0440\u043E\u0433\
  \u0440\u0430\u043C\u043C\u0438\u0441\u0442\u044B \u0434\u0435\u043B\u0430\u044E\u0442\
  \ \u044D\u0442\u043E \u0434\u043B\u044F \u0432\u0437\u0430\u0438\u043C\u043E\u0434\
  \u0435\u0439\u0441\u0442\u0432\u0438\u044F \u0441 \u0432\u0435\u0431-\u043A\u043E\
  \u043D\u0442\u0435\u043D\u0442\u043E\u043C \u0438\u043B\u0438 \u0441\u0431\u043E\
  \u0440\u0430\u2026"
lastmod: '2024-03-13T22:44:44.507454-06:00'
model: gpt-4-0125-preview
summary: "\u041F\u0430\u0440\u0441\u0438\u043D\u0433 HTML \u0432 \u043F\u0440\u043E\
  \u0433\u0440\u0430\u043C\u043C\u0438\u0440\u043E\u0432\u0430\u043D\u0438\u0438 \u0432\
  \u043A\u043B\u044E\u0447\u0430\u0435\u0442 \u0438\u0437\u0432\u043B\u0435\u0447\u0435\
  \u043D\u0438\u0435 \u0434\u0430\u043D\u043D\u044B\u0445 \u0438\u0437 HTML-\u0434\
  \u043E\u043A\u0443\u043C\u0435\u043D\u0442\u043E\u0432."
title: "\u0420\u0430\u0437\u0431\u043E\u0440 HTML"
weight: 43
---

## Как это сделать:
Dart не предоставляет встроенную поддержку для парсинга HTML в своих основных библиотеках. Однако, вы можете использовать сторонний пакет, такой как `html`, для парсинга и манипуляции HTML-документами.

Сначала добавьте пакет `html` в файл `pubspec.yaml`:

```yaml
dependencies:
  html: ^0.15.0
```

Затем импортируйте пакет в ваш Dart файл:

```dart
import 'package:html/parser.dart' show parse;
import 'package:html/dom.dart';
```

Вот базовый пример парсинга строки, содержащей HTML, и извлечения данных:

```dart
void main() {
  var htmlDocument = """
  <html>
    <body>
      <h1>Привет, Dart!</h1>
      <p>Это параграф в примере HTML</p>
    </body>
  </html>
  """;

  // Парсинг HTML строки
  Document document = parse(htmlDocument);

  // Извлечение данных
  String title = document.querySelector('h1')?.text ?? "Заголовок не найден";
  String paragraph = document.querySelector('p')?.text ?? "Параграф не найден";

  print('Заголовок: $title');
  print('Параграф: $paragraph');
}
```

Вывод:

```
Заголовок: Привет, Dart!
Параграф: Это параграф в примере HTML
```

Чтобы взаимодействовать с реальными веб-страницами, вы можете комбинировать парсинг `html` с HTTP-запросами (используя пакет `http` для получения веб-контента). Вот быстрый пример:

Сначала добавьте пакет `http` вместе с `html`:

```yaml
dependencies:
  html: ^0.15.0
  http: ^0.13.3
```

Затем извлеките и проанализируйте HTML-страницу из сети:

```dart
import 'package:http/http.dart' as http;
import 'package:html/parser.dart' show parse;

void main() async {
  var url = 'https://example.com';
  
  // Получение веб-страницы
  var response = await http.get(Uri.parse(url));
  
  if (response.statusCode == 200) {
    var document = parse(response.body);

    // Предположим, что на странице есть интересующие вас теги <h1>
    var headlines = document.querySelectorAll('h1').map((e) => e.text).toList();
    
    print('Заголовки: $headlines');
  } else {
    print('Запрос не удался со статусом: ${response.statusCode}.');
  }
}
```

Примечание: Техника веб-скрапинга, показанная выше, должна использоваться ответственно и в соответствии с условиями использования веб-сайта.
