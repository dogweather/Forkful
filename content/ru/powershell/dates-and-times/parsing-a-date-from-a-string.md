---
title:                "Анализ даты из строки"
aliases:
- /ru/powershell/parsing-a-date-from-a-string/
date:                  2024-01-29T00:00:41.603277-07:00
model:                 gpt-4-0125-preview
simple_title:         "Анализ даты из строки"

tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ru/powershell/parsing-a-date-from-a-string.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Что и Почему?
Разбор даты из строки заключается в понимании информации о дате, содержащейся в тексте. Программисты делают это, чтобы иметь возможность выполнять вычисления, сравнения и сохранять даты в стандартизированном формате.

## Как это сделать:
PowerShell делает разбор дат довольно простым. Давайте посмотрим, как преобразовать строку в объект DateTime.

```PowerShell
# Базовый разбор с использованием ParseExact
$dateString = "March 31, 2023"
$format = "MMMM dd, yyyy"
$parsedDate = [datetime]::ParseExact($dateString, $format, $null)

# Вывод
$parsedDate
```

На выходе получаем:

```
Friday, March 31, 2023 12:00:00 AM
```

Иногда строки имеют разные форматы. Давайте решим эту задачу, используя стандартный `Parse`:

```PowerShell
# Разбор даты в различных форматах
$dateString = "2023-03-31T14:45:00"
$parsedDate = [datetime]::Parse($dateString)

# Вывод
$parsedDate
```

Здесь вывод:

```
Friday, March 31, 2023 2:45:00 PM
```

Имеете дело с форматами, специфичными для культуры? Используйте `ParseExact` с указанием конкретной культуры:

```PowerShell
# Разбор, специфичный для культуры
$dateString = "31/03/2023 16:45"
$format = "dd/MM/yyyy HH:mm"
$culture = [Globalization.CultureInfo]::GetCultureInfo("en-GB")
$parsedDate = [datetime]::ParseExact($dateString, $format, $culture)

# Вывод
$parsedDate
```

На выходе получаем:

```
Friday, March 31, 2023 4:45:00 PM
```

## Подробнее
Теперь о подробностях. Разбор даты всегда был капризным из-за разнообразия мировых форматов дат. В давние времена каждый язык программирования имел свой способ обработки дат, что часто приводило к несоответствиям. PowerShell, как более новый язык сценариев, воспользовался преимуществами класса DateTime из .NET, предоставляя мощные функции разбора.

В качестве альтернативы у нас есть `Get-Date`, который также может разобрать строку в объект DateTime. Рассмотрите использование `TryParseExact` и `TryParse`, если вы ожидаете неожиданное и хотите избежать исключений из-за неразбираемых строк.

Поговорим о реализации. Разбор даты чувствителен к культуре, что означает, что формат даты может варьироваться в зависимости от региона. Вот почему мы предоставляем информацию о культуре и формате, чтобы точно определить ожидаемую структуру строки с датой.

Иногда вы сталкиваетесь с очень необычными форматами — на помощь приходит метод `ParseExact`, ваш карманный нож для разбора дат. Он позволяет указать точный формат, который вы ожидаете. Здесь нет места догадкам.

## Смотрите также
Чтобы расширить свои знания, изучите эти ресурсы:

- [Официальная документация PowerShell по Get-Date](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/get-date?view=powershell-7.1)
- [.NET документация по DateTime.Parse](https://docs.microsoft.com/en-us/dotnet/api/system.datetime.parse?view=net-6.0)
- [Рассмотрения глобализации и локализации](https://docs.microsoft.com/en-us/dotnet/standard/globalization-localization/)

Помните, разбор даты — мощный инструмент, используйте его мудро!
