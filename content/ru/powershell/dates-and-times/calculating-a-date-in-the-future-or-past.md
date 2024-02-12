---
title:                "Расчет даты в будущем или прошлом"
aliases:
- /ru/powershell/calculating-a-date-in-the-future-or-past/
date:                  2024-01-28T23:55:47.895640-07:00
model:                 gpt-4-0125-preview
simple_title:         "Расчет даты в будущем или прошлом"

tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ru/powershell/calculating-a-date-in-the-future-or-past.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Что и Почему?
Вычисление даты в будущем или прошлом означает определение того, какая дата будет после или до определённого временного периода. Программисты делают это для автоматизации напоминаний, планирования задач или управления сроками действия.

## Как это сделать:

### Добавить дни к текущей дате:
```PowerShell
# Добавить 10 дней к сегодняшней дате
$newDate = (Get-Date).AddDays(10)
Write-Output $newDate
```

Пример вывода:
```
Четверг, 13 апреля 2023 года
```

### Вычесть дни из текущей даты:
```PowerShell
# Вычесть 15 дней из сегодняшней даты
$pastDate = (Get-Date).AddDays(-15)
Write-Output $pastDate
```

Пример вывода:
```
Среда, 20 марта 2023 года
```

### Рассчитать разницу между двумя датами:
```PowerShell
# Разница между двумя датами
$date1 = Get-Date '2023-04-01'
$date2 = Get-Date '2023-04-15'
$diff = $date2 - $date1
Write-Output $diff.Days
```

Пример вывода:
```
14
```

## Подробнее
Когда-то программистам приходилось вручную вычислять даты, используя сложные алгоритмы. Теперь языки программирования, такие как PowerShell, предоставляют встроенные функции, такие как `AddDays`, `AddMonths`, что делает этот процесс почти тривиальным.

### Альтернативы:
Хотя `AddDays` удобен, существуют также функции, такие как `AddHours`, `AddMinutes` и т. д., для более детального контроля. Кроме того, вы можете использовать `[datetime]::Today.AddDays(10)`, если предпочитаете статический подход.

### Детали реализации:
Объект `DateTime` в PowerShell имеет эти методы встроенные, так что вам не приходится изобретать велосипед. Под капотом он обрабатывает все виды сложностей, такие как високосные годы и корректировки перехода на летнее/зимнее время за вас.

## Смотрите также
- Официальная документация PowerShell по методам `DateTime`: [Microsoft Docs - Методы DateTime](https://docs.microsoft.com/en-us/dotnet/api/system.datetime?view=net-6.0)
- Больше о арифметике дат в PowerShell: [Арифметика дат в PowerShell](https://ss64.com/ps/syntax-dateformats.html)
- Для погружения в историю и тонкости систем календарей, актуальных для вычислений дат: [ЧаВо о календарях](http://www.tondering.dk/claus/cal/calendar29.html)
