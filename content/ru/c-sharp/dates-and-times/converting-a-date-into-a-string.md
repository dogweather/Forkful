---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 23:56:53.841327-07:00
description: "\u041F\u0440\u0435\u043E\u0431\u0440\u0430\u0437\u043E\u0432\u0430\u043D\
  \u0438\u0435 \u0434\u0430\u0442\u044B \u0432 \u0441\u0442\u0440\u043E\u043A\u0443\
  \ \u0432 C# \u0437\u0430\u043A\u043B\u044E\u0447\u0430\u0435\u0442\u0441\u044F \u0432\
  \ \u0438\u0437\u043C\u0435\u043D\u0435\u043D\u0438\u0438 \u0444\u043E\u0440\u043C\
  \u0430\u0442\u0430 \u0438\u0437 \u043E\u0431\u044A\u0435\u043A\u0442\u0430 DateTime\
  \ \u0432 \u0442\u0435\u043A\u0441\u0442\u043E\u0432\u043E\u0435 \u043F\u0440\u0435\
  \u0434\u0441\u0442\u0430\u0432\u043B\u0435\u043D\u0438\u0435. \u041F\u0440\u043E\
  \u0433\u0440\u0430\u043C\u043C\u0438\u0441\u0442\u044B \u0434\u0435\u043B\u0430\u044E\
  \u0442 \u044D\u0442\u043E \u0434\u043B\u044F \u043E\u0442\u043E\u0431\u0440\u0430\
  \u0436\u0435\u043D\u0438\u044F\u2026"
lastmod: '2024-03-13T22:44:45.077322-06:00'
model: gpt-4-0125-preview
summary: "\u041F\u0440\u0435\u043E\u0431\u0440\u0430\u0437\u043E\u0432\u0430\u043D\
  \u0438\u0435 \u0434\u0430\u0442\u044B \u0432 \u0441\u0442\u0440\u043E\u043A\u0443\
  \ \u0432 C# \u0437\u0430\u043A\u043B\u044E\u0447\u0430\u0435\u0442\u0441\u044F \u0432\
  \ \u0438\u0437\u043C\u0435\u043D\u0435\u043D\u0438\u0438 \u0444\u043E\u0440\u043C\
  \u0430\u0442\u0430 \u0438\u0437 \u043E\u0431\u044A\u0435\u043A\u0442\u0430 DateTime\
  \ \u0432 \u0442\u0435\u043A\u0441\u0442\u043E\u0432\u043E\u0435 \u043F\u0440\u0435\
  \u0434\u0441\u0442\u0430\u0432\u043B\u0435\u043D\u0438\u0435."
title: "\u041F\u0440\u0435\u043E\u0431\u0440\u0430\u0437\u043E\u0432\u0430\u043D\u0438\
  \u0435 \u0434\u0430\u0442\u044B \u0432 \u0441\u0442\u0440\u043E\u043A\u0443"
weight: 28
---

## Как:
В C# у вас есть объект `DateTime` и множество способов превратить его в строку. Вот несколько из них:

```csharp
DateTime now = DateTime.Now;
string defaultString = now.ToString(); // Формат по умолчанию
string specificFormat = now.ToString("yyyy-MM-dd"); // Пользовательский формат, здесь ISO 8601
string withCulture = now.ToString("d", new CultureInfo("en-US")); // Короткая дата в американской культуре

Console.WriteLine(defaultString); // Вывод зависит от настроек культуры системы
Console.WriteLine(specificFormat); // Вывод: "2023-04-01"
Console.WriteLine(withCulture); // Вывод: "4/1/2023"
```

## Подробнее
Раньше манипуляции с датами и строками были сложнее. Сегодня `DateTime` в C# предлагает `.ToString()` с перегрузками для культуры и формата. Интерфейс `IFormatProvider`, например `CultureInfo`, контролирует форматирование, специфичное для культуры.

Альтернативы? Конечно! `String.Format` и интерполяция (`$"{now:yyyy-MM-dd}"`) являются вариантами для вставки дат в строки с контекстом. `DateTimeOffset` удобен для учета часовых поясов.

С точки зрения реализации, помните, что `DateTime` - это структура, а значит, тип значения. Преобразование его не изменяет оригинал: неизменяемость это плюс. Внимательно выбирайте формат строки, исходя из вашей аудитории (конечных пользователей) и системы, с которой вы взаимодействуете (базы данных, API).

## Смотрите также
- [Метод DateTime.ToString](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.tostring)
- [Пользовательские строки формата даты и времени](https://docs.microsoft.com/en-us/dotnet/standard/base-types/custom-date-and-time-format-strings)
- [Класс CultureInfo](https://docs.microsoft.com/en-us/dotnet/api/system.globalization.cultureinfo)
