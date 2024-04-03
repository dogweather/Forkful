---
changelog:
- 2024-01-29, gpt-4-0125-preview, translated from English
date: 2024-01-29 00:05:40.029337-07:00
description: "\u0421\u043E\u0437\u0434\u0430\u043D\u0438\u0435 \u0442\u0435\u043A\u0441\
  \u0442\u043E\u0432\u043E\u0433\u043E \u0444\u0430\u0439\u043B\u0430 \u043E\u0437\
  \u043D\u0430\u0447\u0430\u0435\u0442 \u0441\u043E\u0445\u0440\u0430\u043D\u0435\u043D\
  \u0438\u0435 \u0434\u0430\u043D\u043D\u044B\u0445, \u043D\u0430\u043F\u0440\u0438\
  \u043C\u0435\u0440 \u0441\u0442\u0440\u043E\u043A, \u0432 \u0444\u0430\u0439\u043B\
  \ \u043D\u0430 \u0432\u0430\u0448\u0435\u043C \u0434\u0438\u0441\u043A\u0435. \u041F\
  \u0440\u043E\u0433\u0440\u0430\u043C\u043C\u0438\u0441\u0442\u044B \u0434\u0435\u043B\
  \u0430\u044E\u0442 \u044D\u0442\u043E \u0434\u043B\u044F \u0432\u0435\u0434\u0435\
  \u043D\u0438\u044F \u0436\u0443\u0440\u043D\u0430\u043B\u043E\u0432, \u0441\u043E\
  \u0445\u0440\u0430\u043D\u0435\u043D\u0438\u044F\u2026"
lastmod: '2024-03-13T22:44:45.090193-06:00'
model: gpt-4-0125-preview
summary: "\u0421\u043E\u0437\u0434\u0430\u043D\u0438\u0435 \u0442\u0435\u043A\u0441\
  \u0442\u043E\u0432\u043E\u0433\u043E \u0444\u0430\u0439\u043B\u0430 \u043E\u0437\
  \u043D\u0430\u0447\u0430\u0435\u0442 \u0441\u043E\u0445\u0440\u0430\u043D\u0435\u043D\
  \u0438\u0435 \u0434\u0430\u043D\u043D\u044B\u0445, \u043D\u0430\u043F\u0440\u0438\
  \u043C\u0435\u0440 \u0441\u0442\u0440\u043E\u043A, \u0432 \u0444\u0430\u0439\u043B\
  \ \u043D\u0430 \u0432\u0430\u0448\u0435\u043C \u0434\u0438\u0441\u043A\u0435."
title: "\u0421\u043E\u0437\u0434\u0430\u043D\u0438\u0435 \u0442\u0435\u043A\u0441\u0442\
  \u043E\u0432\u043E\u0433\u043E \u0444\u0430\u0439\u043B\u0430"
weight: 24
---

## Как это сделать:
Вы можете создать текстовый файл в C# с помощью `File.WriteAllText`, `File.AppendAllText` или `StreamWriter`.

```C#
using System;
using System.IO;

class Program
{
    static void Main()
    {
        // Записать текст в новый файл
        File.WriteAllText("log.txt", "Привет, файл!");

        // Добавить текст в существующий файл
        File.AppendAllText("log.txt", "\nДавайте добавим ещё одну строку.");

        // Использовать StreamWriter для записи в файл
        using (StreamWriter writer = new StreamWriter("log.txt", true))
        {
            writer.WriteLine("Ещё одна строка с помощью StreamWriter.");
        }
    }
}
```

Пример вывода в `log.txt`:
```
Привет, файл!
Давайте добавим ещё одну строку.
Ещё одна строка с помощью StreamWriter.
```

## Погружение в тему
Исторически операции ввода-вывода файлов в C# эволюционировали от основных операций `FileStream` к абстракциям вроде `StreamWriter`. К альтернативам относят использование `System.IO.FileStream` для более тщательного контроля или асинхронных методов вроде `WriteAllTextAsync` для повышения эффективности. Под капотом `StreamWriter` использует буфер для оптимизации операций записи.

## Смотрите также
Для дополнительного чтения и подробных учебных пособий:
- [Документация MSDN по файловому вводу-выводу](https://docs.microsoft.com/en-us/dotnet/standard/io/)
- [Класс MSDN StreamWriter](https://docs.microsoft.com/en-us/dotnet/api/system.io.streamwriter)
- [Учебник по асинхронному файловому вводу-выводу в C#](https://docs.microsoft.com/en-us/dotnet/standard/io/asynchronous-file-i-o)
