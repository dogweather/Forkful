---
date: 2024-01-20 17:55:20.384882-07:00
description: "\u0427\u0438\u0442\u0430\u043D\u043D\u044F \u0442\u0435\u043A\u0441\u0442\
  \u043E\u0432\u043E\u0433\u043E \u0444\u0430\u0439\u043B\u0443 \u2014 \u0446\u0435\
  \ \u043F\u0440\u043E\u0446\u0435\u0441 \u0437\u0430\u0432\u0430\u043D\u0442\u0430\
  \u0436\u0435\u043D\u043D\u044F \u0442\u0435\u043A\u0441\u0442\u0443 \u0437 \u0444\
  \u0430\u0439\u043B\u0443 \u0443 \u0432\u0430\u0448\u0443 \u043F\u0440\u043E\u0433\
  \u0440\u0430\u043C\u0443. \u041F\u0440\u043E\u0433\u0440\u0430\u043C\u0456\u0441\
  \u0442\u0438 \u0446\u0435 \u0440\u043E\u0431\u043B\u044F\u0442\u044C, \u0449\u043E\
  \u0431 \u043E\u0431\u0440\u043E\u0431\u0438\u0442\u0438 \u0434\u0430\u043D\u0456\
  \ \u0430\u0431\u043E \u0437\u0447\u0438\u0442\u0430\u0442\u0438 \u043A\u043E\u043D\
  \u0444\u0456\u0433\u0443\u0440\u0430\u0446\u0456\u0457."
lastmod: '2024-03-13T22:44:49.949548-06:00'
model: gpt-4-1106-preview
summary: "\u0427\u0438\u0442\u0430\u043D\u043D\u044F \u0442\u0435\u043A\u0441\u0442\
  \u043E\u0432\u043E\u0433\u043E \u0444\u0430\u0439\u043B\u0443 \u2014 \u0446\u0435\
  \ \u043F\u0440\u043E\u0446\u0435\u0441 \u0437\u0430\u0432\u0430\u043D\u0442\u0430\
  \u0436\u0435\u043D\u043D\u044F \u0442\u0435\u043A\u0441\u0442\u0443 \u0437 \u0444\
  \u0430\u0439\u043B\u0443 \u0443 \u0432\u0430\u0448\u0443 \u043F\u0440\u043E\u0433\
  \u0440\u0430\u043C\u0443."
title: "\u0427\u0438\u0442\u0430\u043D\u043D\u044F \u0442\u0435\u043A\u0441\u0442\u043E\
  \u0432\u043E\u0433\u043E \u0444\u0430\u0439\u043B\u0443"
weight: 22
---

## Як це зробити:
```Swift
import Foundation

// Путь до файлу
let path = "/path/to/your/file.txt"

// Читання вмісту з файла
if let content = try? String(contentsOfFile: path, encoding: .utf8) {
    print(content)
} else {
    print("Не можливо прочитати файл.")
}
```
Вихідні дані:
```
Привіт! Це текст з вашого файла.
```

## Поглиблено:
Читання файлів тексту в Swift не виникло з пустоти; цей процес сягає корінням в ранні дні програмування. Історично, читання даних було одним із перших завдань, які комп’ютери виконували. Ви могли б використовувати InputStream або FileManager для більш складного читання, а також налаштувати потоки для асинхронного читання. Важливо розуміти, як Swift управляє пам'яттю під час операцій з файлами, щоб не зіткнутися з витоками пам'яті або виключеннями під час роботи з великими файлами.

## Дивіться також:
- Apple Documentation for FileManager: [FileManager](https://developer.apple.com/documentation/foundation/filemanager)
- Apple Documentation for Streams: [Streams](https://developer.apple.com/documentation/foundation/stream)
- Swift String and Characters: [Strings and Characters](https://docs.swift.org/swift-book/LanguageGuide/StringsAndCharacters.html)
