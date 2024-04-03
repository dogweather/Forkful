---
changelog:
- 2024-01-29, gpt-4-0125-preview, translated from English
date: 2024-01-29 00:04:31.358186-07:00
description: "\u0420\u0430\u0431\u043E\u0442\u0430 \u0441 JSON \u0432 Swift \u0441\
  \u0432\u044F\u0437\u0430\u043D\u0430 \u0441 \u0438\u0441\u043F\u043E\u043B\u044C\
  \u0437\u043E\u0432\u0430\u043D\u0438\u0435\u043C \u043B\u0435\u0433\u043A\u043E\u0432\
  \u0435\u0441\u043D\u043E\u0433\u043E \u0444\u043E\u0440\u043C\u0430\u0442\u0430\
  \ \u0434\u0430\u043D\u043D\u044B\u0445 \u0434\u043B\u044F \u043E\u0431\u043C\u0435\
  \u043D\u0430 \u0434\u0430\u043D\u043D\u044B\u043C\u0438. \u041F\u0440\u043E\u0433\
  \u0440\u0430\u043C\u043C\u0438\u0441\u0442\u044B \u0438\u0441\u043F\u043E\u043B\u044C\
  \u0437\u0443\u044E\u0442 JSON \u0434\u043B\u044F \u043F\u0435\u0440\u0435\u0434\u0430\
  \u0447\u0438 \u0434\u0430\u043D\u043D\u044B\u0445 \u043C\u0435\u0436\u0434\u0443\
  \u2026"
lastmod: '2024-03-13T22:44:45.721667-06:00'
model: gpt-4-0125-preview
summary: "\u0420\u0430\u0431\u043E\u0442\u0430 \u0441 JSON \u0432 Swift \u0441\u0432\
  \u044F\u0437\u0430\u043D\u0430 \u0441 \u0438\u0441\u043F\u043E\u043B\u044C\u0437\
  \u043E\u0432\u0430\u043D\u0438\u0435\u043C \u043B\u0435\u0433\u043A\u043E\u0432\u0435\
  \u0441\u043D\u043E\u0433\u043E \u0444\u043E\u0440\u043C\u0430\u0442\u0430 \u0434\
  \u0430\u043D\u043D\u044B\u0445 \u0434\u043B\u044F \u043E\u0431\u043C\u0435\u043D\
  \u0430 \u0434\u0430\u043D\u043D\u044B\u043C\u0438."
title: "\u0420\u0430\u0431\u043E\u0442\u0430 \u0441 JSON"
weight: 38
---

## Как:
Swift упрощает разбор JSON с помощью протокола `Codable`. Вот как вы можете декодировать JSON в объект Swift:

```Swift
import Foundation

// Определение модели, соответствующей Codable
struct User: Codable {
    var name: String
    var age: Int
}

// Строка JSON
let jsonString = """
{
    "name": "John Doe",
    "age": 30
}
"""

// Преобразование строки JSON в Data
if let jsonData = jsonString.data(using: .utf8) {
    // Декодирование данных JSON в объект User
    do {
        let user = try JSONDecoder().decode(User.self, from: jsonData)
        print("Имя: \(user.name), Возраст: \(user.age)")
    } catch {
        print("Ошибка декодирования JSON: \(error)")
    }
}
```

Пример вывода:
```
Имя: John Doe, Возраст: 30
```

## Подробный разбор
JSON (JavaScript Object Notation) широко используется с начала 2000-х годов после того, как Дуглас Крокфорд его описал. Он заменил XML во многих случаях благодаря своему более простому синтаксису и лучшей производительности. Хотя `Codable` в Swift является предпочтительным способом работы с JSON, существуют альтернативы, такие как `JSONSerialization`, для случаев, когда типы не соответствуют требованиям `Codable`. В фоновом режиме `Codable` абстрагирует низкоуровневый разбор и делает сериализацию/десериализацию бесшовной.

## Смотрите также
- Узнайте больше о JSON и Swift в официальном блоге Swift: [Swift.org](https://swift.org/blog/)
- Ознакомьтесь с документацией `Codable`: [Swift Codable](https://developer.apple.com/documentation/swift/codable)
- Для работы со сложными структурами JSON рассмотрите сторонние библиотеки, такие как SwiftyJSON, доступные на [GitHub](https://github.com/SwiftyJSON/SwiftyJSON).
