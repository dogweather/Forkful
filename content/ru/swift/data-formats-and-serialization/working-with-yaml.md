---
aliases:
- /ru/swift/working-with-yaml/
changelog:
- 2024-01-29, gpt-4-0125-preview, translated from English
date: 2024-01-29 00:05:22.565176-07:00
description: "YAML, \u0447\u0442\u043E \u0440\u0430\u0441\u0448\u0438\u0444\u0440\u043E\
  \u0432\u044B\u0432\u0430\u0435\u0442\u0441\u044F \u043A\u0430\u043A \"YAML Ain't\
  \ Markup Language\" (YAML - \u044D\u0442\u043E \u043D\u0435 \u044F\u0437\u044B\u043A\
  \ \u0440\u0430\u0437\u043C\u0435\u0442\u043A\u0438), \u043F\u0440\u0435\u0434\u0441\
  \u0442\u0430\u0432\u043B\u044F\u0435\u0442 \u0441\u043E\u0431\u043E\u0439 \u0441\
  \u0442\u0430\u043D\u0434\u0430\u0440\u0442 \u0441\u0435\u0440\u0438\u0430\u043B\u0438\
  \u0437\u0430\u0446\u0438\u0438 \u0434\u0430\u043D\u043D\u044B\u0445, \u043F\u043E\
  \u043D\u044F\u0442\u043D\u044B\u0439\u2026"
lastmod: 2024-02-18 23:08:57.433577
model: gpt-4-0125-preview
summary: "YAML, \u0447\u0442\u043E \u0440\u0430\u0441\u0448\u0438\u0444\u0440\u043E\
  \u0432\u044B\u0432\u0430\u0435\u0442\u0441\u044F \u043A\u0430\u043A \"YAML Ain't\
  \ Markup Language\" (YAML - \u044D\u0442\u043E \u043D\u0435 \u044F\u0437\u044B\u043A\
  \ \u0440\u0430\u0437\u043C\u0435\u0442\u043A\u0438), \u043F\u0440\u0435\u0434\u0441\
  \u0442\u0430\u0432\u043B\u044F\u0435\u0442 \u0441\u043E\u0431\u043E\u0439 \u0441\
  \u0442\u0430\u043D\u0434\u0430\u0440\u0442 \u0441\u0435\u0440\u0438\u0430\u043B\u0438\
  \u0437\u0430\u0446\u0438\u0438 \u0434\u0430\u043D\u043D\u044B\u0445, \u043F\u043E\
  \u043D\u044F\u0442\u043D\u044B\u0439\u2026"
title: "\u0420\u0430\u0431\u043E\u0442\u0430 \u0441 YAML"
---

{{< edit_this_page >}}

## Что и Почему?
YAML, что расшифровывается как "YAML Ain't Markup Language" (YAML - это не язык разметки), представляет собой стандарт сериализации данных, понятный человеку, который мы можем использовать для конфигурирования файлов или обмена данными. Программисты любят YAML за его простоту и читаемость, особенно в настройках конфигурации, сценариях CI/CD и системах оркестровки контейнеров.

## Как использовать:
Swift изначально не обрабатывает YAML, поэтому нам нужно использовать стороннюю библиотеку, такую как Yams. Сначала добавьте Yams в ваш `Package.swift`:

```swift
dependencies: [
    .package(url: "https://github.com/jpsim/Yams.git", from: "4.0.0")
]
```

Затем, импортируйте Yams и используйте его для парсинга YAML в словарь Swift:

```swift
import Yams

let yamlString = """
name: John Doe
age: 34
languages:
  - Swift
  - Python
"""

do {
    if let data = try Yams.load(yaml: yamlString) as? [String: Any] {
        print(data)
    }
} catch {
    print("Не удалось разобрать строку YAML.")
}

// Вывод:
// ["name": "John Doe", "age": 34, "languages": ["Swift", "Python"]]
```

Если вы хотите генерировать YAML из объектов Swift:

```swift
import Yams

let dictionary: [String: Any] = [
    "name": "Jane Smith",
    "age": 28,
    "languages": ["Java", "Kotlin"]
]

do {
    let yaml = try Yams.dump(object: dictionary)
    print(yaml)
} catch {
    print("Не удалось преобразовать словарь в YAML.")
}

// Вывод:
// age: 28
// languages:
//   - Java
//   - Kotlin
// name: Jane Smith
```

## Глубже
YAML появился в 2001 году как альтернатива XML, удобная для человека. Он напоминает JSON с меньшим использованием скобок и лучшей читаемостью для человека. В то время как для веб-API обычно выбирают JSON, YAML предпочитают для файлов конфигурации. Альтернативами являются TOML и JSON5, но использование пробельных символов в YAML и возможность комментирования строк делают его желательным. С Yams, Swift подходит к обработке YAML с классовым маппингом, предлагая баланс между простотой сценариев и типовой безопасностью.

## Смотрите также
- Официальный сайт YAML для деталей спецификации: [https://yaml.org](https://yaml.org)
- Репозиторий Yams на GitHub: [https://github.com/jpsim/Yams](https://github.com/jpsim/Yams)
- Документация Менеджера Пакетов Swift: [https://swift.org/package-manager/](https://swift.org/package-manager/)
