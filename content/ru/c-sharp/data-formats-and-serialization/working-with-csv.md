---
aliases:
- /ru/c-sharp/working-with-csv/
changelog:
- 2024-01-29, gpt-4-0125-preview, translated from English
date: 2024-01-29 00:04:32.908190-07:00
description: "\u0420\u0430\u0431\u043E\u0442\u0430 \u0441 CSV (Comma-Separated Values,\
  \ \u0437\u043D\u0430\u0447\u0435\u043D\u0438\u044F, \u0440\u0430\u0437\u0434\u0435\
  \u043B\u0435\u043D\u043D\u044B\u0435 \u0437\u0430\u043F\u044F\u0442\u044B\u043C\u0438\
  ) \u043E\u0437\u043D\u0430\u0447\u0430\u0435\u0442 \u0447\u0442\u0435\u043D\u0438\
  \u0435 \u0438 \u0437\u0430\u043F\u0438\u0441\u044C \u0434\u0430\u043D\u043D\u044B\
  \u0445 \u0432 \u043F\u0440\u043E\u0441\u0442\u043E\u043C, \u043E\u0441\u043D\u043E\
  \u0432\u0430\u043D\u043D\u043E\u043C \u043D\u0430 \u0442\u0435\u043A\u0441\u0442\
  \u0435 \u0444\u043E\u0440\u043C\u0430\u0442\u0435 \u2014 \u0442\u0430\u043A\u043E\
  \u043C,\u2026"
lastmod: 2024-02-18 23:08:57.023451
model: gpt-4-0125-preview
summary: "\u0420\u0430\u0431\u043E\u0442\u0430 \u0441 CSV (Comma-Separated Values,\
  \ \u0437\u043D\u0430\u0447\u0435\u043D\u0438\u044F, \u0440\u0430\u0437\u0434\u0435\
  \u043B\u0435\u043D\u043D\u044B\u0435 \u0437\u0430\u043F\u044F\u0442\u044B\u043C\u0438\
  ) \u043E\u0437\u043D\u0430\u0447\u0430\u0435\u0442 \u0447\u0442\u0435\u043D\u0438\
  \u0435 \u0438 \u0437\u0430\u043F\u0438\u0441\u044C \u0434\u0430\u043D\u043D\u044B\
  \u0445 \u0432 \u043F\u0440\u043E\u0441\u0442\u043E\u043C, \u043E\u0441\u043D\u043E\
  \u0432\u0430\u043D\u043D\u043E\u043C \u043D\u0430 \u0442\u0435\u043A\u0441\u0442\
  \u0435 \u0444\u043E\u0440\u043C\u0430\u0442\u0435 \u2014 \u0442\u0430\u043A\u043E\
  \u043C,\u2026"
title: "\u0420\u0430\u0431\u043E\u0442\u0430 \u0441 CSV"
---

{{< edit_this_page >}}

## Что и Почему?

Работа с CSV (Comma-Separated Values, значения, разделенные запятыми) означает чтение и запись данных в простом, основанном на тексте формате — таком, который универсален и удобен для таблиц. Программисты используют CSV за его простоту и взаимодействие при обмене табличными данными между системами.

## Как

### Чтение файлов CSV
```C#
using System;
using System.IO;

class ReadCSVExample
{
    static void Main()
    {
        string path = "data.csv";
        using (var reader = new StreamReader(path))
        {
            while (!reader.EndOfStream)
            {
                var line = reader.ReadLine();
                var values = line.Split(',');
                // Теперь сделайте что-то со значениями, например, напечатайте их
                Console.WriteLine(String.Join(" | ", values));
            }
        }
    }
}
```
**Пример вывода:**
```
John | Doe | johndoe@example.com
Jane | Smith | janesmith@example.com
```

### Запись файлов CSV
```C#
using System;
using System.IO;

class WriteCSVExample
{
    static void Main()
    {
        string path = "output.csv";
        var records = new[]
        {
            new[] {"Name", "Age", "Email"},
            new[] {"Alice", "23", "alice@example.com"},
            new[] {"Bob", "30", "bob@example.com"}
        };

        using (var writer = new StreamWriter(path))
        {
            foreach (var record in records)
            {
                var line = String.Join(",", record);
                writer.WriteLine(line);
            }
        }
        Console.WriteLine($"Данные записаны в {path}");
    }
}
```
**Пример вывода:**
```
Данные записаны в output.csv
```

## Углубление

CSV существует с начала времен вычислений, служа мостом между разными системами. Он не идеален — не имеет стандартной кодировки символов и плохо поддерживает многострочные поля без надежного парсера. Здесь на сцену выходят форматы вроде JSON и XML, предлагая больше сложности, но лучшую структуру для иерархических данных.

Под капотом вы обычно манипулируете строками, либо с использованием встроенных методов `string`, либо библиотеки вроде `CsvHelper` могут добавить дополнительную мощь вашей работе с CSV, предоставляя больше функций и изящно обрабатывая крайние случаи. Помните, в .NET нет встроенной обработки CSV, так что вы остаетесь наедине с манипуляциями со строками или можете выбрать стороннюю библиотеку.

## Смотрите также

Для более глубокого изучения манипуляции с CSV в C#:
- [Библиотека CsvHelper](https://joshclose.github.io/CsvHelper/)
- [Документация Microsoft по `StreamReader`](https://docs.microsoft.com/en-us/dotnet/api/system.io.streamreader)

Узнайте больше о альтернативах CSV:
- [Понимание JSON](https://www.json.org/json-en.html)
- [XML в двух словах](https://www.w3schools.com/xml/xml_whatis.asp)
