---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 23:58:50.619375-07:00
description: "\u041E\u0431\u0440\u0430\u0431\u043E\u0442\u043A\u0430 \u043E\u0448\u0438\
  \u0431\u043E\u043A \u0432 Swift \u043E\u0437\u043D\u0430\u0447\u0430\u0435\u0442\
  \ \u043F\u0440\u0435\u0434\u0432\u0438\u0434\u0435\u043D\u0438\u0435 \u0438 \u0440\
  \u0435\u0430\u0433\u0438\u0440\u043E\u0432\u0430\u043D\u0438\u0435 \u043D\u0430\
  \ \u043F\u0440\u043E\u0431\u043B\u0435\u043C\u044B, \u0432\u043E\u0437\u043D\u0438\
  \u043A\u0430\u044E\u0449\u0438\u0435 \u043F\u0440\u0438 \u0432\u044B\u043F\u043E\
  \u043B\u043D\u0435\u043D\u0438\u0438 \u0432\u0430\u0448\u0435\u0433\u043E \u043A\
  \u043E\u0434\u0430. \u041C\u044B \u0434\u0435\u043B\u0430\u0435\u043C \u044D\u0442\
  \u043E \u0434\u043B\u044F \u0442\u043E\u0433\u043E, \u0447\u0442\u043E\u0431\u044B\
  \u2026"
lastmod: '2024-03-13T22:44:45.697197-06:00'
model: gpt-4-0125-preview
summary: "\u041E\u0431\u0440\u0430\u0431\u043E\u0442\u043A\u0430 \u043E\u0448\u0438\
  \u0431\u043E\u043A \u0432 Swift \u043E\u0437\u043D\u0430\u0447\u0430\u0435\u0442\
  \ \u043F\u0440\u0435\u0434\u0432\u0438\u0434\u0435\u043D\u0438\u0435 \u0438 \u0440\
  \u0435\u0430\u0433\u0438\u0440\u043E\u0432\u0430\u043D\u0438\u0435 \u043D\u0430\
  \ \u043F\u0440\u043E\u0431\u043B\u0435\u043C\u044B, \u0432\u043E\u0437\u043D\u0438\
  \u043A\u0430\u044E\u0449\u0438\u0435 \u043F\u0440\u0438 \u0432\u044B\u043F\u043E\
  \u043B\u043D\u0435\u043D\u0438\u0438 \u0432\u0430\u0448\u0435\u0433\u043E \u043A\
  \u043E\u0434\u0430."
title: "\u041E\u0431\u0440\u0430\u0431\u043E\u0442\u043A\u0430 \u043E\u0448\u0438\u0431\
  \u043E\u043A"
weight: 16
---

## Как:
Swift использует обработку ошибок с помощью блоков `do`, `try` и `catch`. Давайте посмотрим:

```Swift
enum FileError: Error {
    case fileDoesNotExist
    case noPermission
}

func readFile(atPath path: String) throws -> String {
    // Представим, что у нас есть некоторая логика здесь, чтобы проверить, существует ли файл и имеем ли мы разрешение на его чтение
    let fileExists = false
    let havePermission = true

    if !fileExists {
        throw FileError.fileDoesNotExist
    }

    if !havePermission {
        throw FileError.noPermission
    }

    return "Содержимое файла идет здесь"
}

do {
    let fileContent = try readFile(atPath: "/path/to/file")
    print(fileContent)
} catch FileError.fileDoesNotExist {
    print("Ой! Файл не найден.")
} catch FileError.noPermission {
    print("Ах! Нет разрешения на чтение файла.")
} catch {
    print("Произошла неизвестная ошибка.")
}

```

Пример вывода:

```
Ой! Файл не найден.
```

## Глубокое Погружение
Обработка ошибок не всегда была такой изящной, как сейчас. В Objective-C вы имели дело с указателями на объекты NSError, что казалось громоздким. Теперь у нас есть более элегантная система с перечислениями Swift и протоколом `Error`.

`throw` в Swift позволяет нам сигнализировать о том, что что-то пошло не так. Блоки `do` действуют как области, осведомленные об ошибках, префикс `try` вызывает рискованные операции, а `catch` обрабатывает ситуации, если что-то идет не так.

Опционалы являются альтернативой для ситуаций, которые не совсем "статус ошибки", но все же могут иметь "нет результата". Они немного похожи на переменные Шрёдингера — у них есть значение или его нет.

Для действительного погружения рекомендуется ознакомиться с типами `Result`, которые являются стильными гибридами между обычными возвращаемыми значениями и шаблонами ошибок.

## Смотрите также
- Официальное руководство по обработке ошибок Swift: [Apple Docs](https://docs.swift.org/swift-book/LanguageGuide/ErrorHandling.html)
- Лучшие практики обработки ошибок в Swift: [RayWenderlich.com](https://www.raywenderlich.com/1851-beginning-swift-error-handling)
- Продвинутая обработка ошибок в Swift: [Статья на Medium](https://medium.com/better-programming/advanced-error-handling-in-swift-4f6bdf6b01d8)
