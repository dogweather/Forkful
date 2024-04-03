---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 23:56:14.820135-07:00
description: "\u0421\u0440\u0430\u0432\u043D\u0435\u043D\u0438\u0435 \u0434\u0432\u0443\
  \u0445 \u0434\u0430\u0442 \u043E\u0437\u043D\u0430\u0447\u0430\u0435\u0442 \u043F\
  \u0440\u043E\u0432\u0435\u0440\u043A\u0443 \u0438\u0445 \u0432\u0437\u0430\u0438\
  \u043C\u043E\u043E\u0442\u043D\u043E\u0448\u0435\u043D\u0438\u044F \u2014 \u043E\
  \u0434\u043D\u0430 \u0434\u0430\u0442\u0430 \u0440\u0430\u043D\u044C\u0448\u0435\
  , \u043F\u043E\u0437\u0436\u0435 \u0438\u043B\u0438 \u0442\u043E\u0447\u043D\u043E\
  \ \u0432 \u0442\u043E \u0436\u0435 \u0441\u0430\u043C\u043E\u0435 \u0432\u0440\u0435\
  \u043C\u044F, \u0447\u0442\u043E \u0438 \u0434\u0440\u0443\u0433\u0430\u044F. \u041F\
  \u0440\u043E\u0433\u0440\u0430\u043C\u043C\u0438\u0441\u0442\u044B \u0434\u0435\u043B\
  \u0430\u044E\u0442 \u044D\u0442\u043E \u0434\u043B\u044F\u2026"
lastmod: '2024-03-13T22:44:45.079296-06:00'
model: gpt-4-0125-preview
summary: "\u0421\u0440\u0430\u0432\u043D\u0435\u043D\u0438\u0435 \u0434\u0432\u0443\
  \u0445 \u0434\u0430\u0442 \u043E\u0437\u043D\u0430\u0447\u0430\u0435\u0442 \u043F\
  \u0440\u043E\u0432\u0435\u0440\u043A\u0443 \u0438\u0445 \u0432\u0437\u0430\u0438\
  \u043C\u043E\u043E\u0442\u043D\u043E\u0448\u0435\u043D\u0438\u044F \u2014 \u043E\
  \u0434\u043D\u0430 \u0434\u0430\u0442\u0430 \u0440\u0430\u043D\u044C\u0448\u0435\
  , \u043F\u043E\u0437\u0436\u0435 \u0438\u043B\u0438 \u0442\u043E\u0447\u043D\u043E\
  \ \u0432 \u0442\u043E \u0436\u0435 \u0441\u0430\u043C\u043E\u0435 \u0432\u0440\u0435\
  \u043C\u044F, \u0447\u0442\u043E \u0438 \u0434\u0440\u0443\u0433\u0430\u044F."
title: "\u0421\u0440\u0430\u0432\u043D\u0435\u043D\u0438\u0435 \u0434\u0432\u0443\u0445\
  \ \u0434\u0430\u0442"
weight: 27
---

## Как:
Давайте погрузимся в C# для сравнения дат. Предположим, у нас есть два объекта `DateTime`, `date1` и `date2`. Мы сравниваем их с помощью `DateTime.Compare(date1, date2)`, `date1.CompareTo(date2)` или напрямую сравнивая свойства:

```C#
DateTime date1 = new DateTime(2023, 3, 25);
DateTime date2 = new DateTime(2023, 3, 30);

// Использование статического метода DateTime.Compare
int result = DateTime.Compare(date1, date2);

if(result < 0)
    Console.WriteLine("date1 раньше, чем date2.");
else if(result == 0)
    Console.WriteLine("date1 тот же момент, что и date2.");
else
    Console.WriteLine("date1 позже, чем date2.");

// Использование метода экземпляра CompareTo
result = date1.CompareTo(date2);

if(result < 0)
    Console.WriteLine("date1 снова раньше.");
else if(result == 0)
    Console.WriteLine("Всё ещё тот же момент?");
else
    Console.WriteLine("date1 на этот раз позже?");

// Непосредственное сравнение
if(date1 < date2)
    Console.WriteLine("Ага, date1 раньше, это видно непосредственно.");
else if(date1 == date2)
    Console.WriteLine("Равны, просто и понятно.");
else
    Console.WriteLine("Или date1 позже? Нет, на этот раз нет.");
```

Вывод покажет, что `date1` раньше `date2` во всех сравнениях — вы говорите очевидное, но для этого и существуют логи.

## Глубокое Погружение
Сравнения DateTime являются частью C# с момента его создания, что критически важно для работы с вечно актуальным понятием времени. Внутренне значения `DateTime` представляют тики с полуночи, 1 января 0001 года, в среде Common Language Runtime.

Хотите альтернативы? Вы могли бы использовать `TimeSpan` для различий, или поднять ставки с NodaTime, библиотекой от Джона Скита для более сложной работы с датами и временем.

Вот технический забавный факт: типы `DateTime` в .NET могут быть `Unspecified`, `Utc` или `Local`. Сравниваете время UTC с местным? Это проблема. Всегда убедитесь, что типы совпадают, чтобы избежать искаженной логики!

## Смотрите Также
Погрузитесь глубже или проясните вопросы с помощью этих ресурсов:

- Документация по DateTime от Microsoft: https://docs.microsoft.com/en-us/dotnet/api/system.datetime
- Больше о DateTime.Kind: https://docs.microsoft.com/en-us/dotnet/api/system.datetime.kind
- NodaTime, для любопытных наблюдателей за часами: https://nodatime.org/
- TimeSpan для различий во времени: https://docs.microsoft.com/en-us/dotnet/api/system.timespan
