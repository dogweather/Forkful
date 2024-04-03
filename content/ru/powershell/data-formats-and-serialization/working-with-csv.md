---
changelog:
- 2024-01-29, gpt-4-0125-preview, translated from English
date: 2024-01-29 00:03:55.896473-07:00
description: "\u0420\u0430\u0431\u043E\u0442\u0430 \u0441 CSV (\u0437\u043D\u0430\u0447\
  \u0435\u043D\u0438\u044F, \u0440\u0430\u0437\u0434\u0435\u043B\u0435\u043D\u043D\
  \u044B\u0435 \u0437\u0430\u043F\u044F\u0442\u044B\u043C\u0438) \u0432\u043A\u043B\
  \u044E\u0447\u0430\u0435\u0442 \u0432 \u0441\u0435\u0431\u044F \u043E\u0431\u0440\
  \u0430\u0431\u043E\u0442\u043A\u0443 \u0442\u0435\u043A\u0441\u0442\u043E\u0432\u044B\
  \u0445 \u0434\u0430\u043D\u043D\u044B\u0445, \u0440\u0430\u0437\u0434\u0435\u043B\
  \u0435\u043D\u043D\u044B\u0445 \u0437\u0430\u043F\u044F\u0442\u044B\u043C\u0438\
  , \u043D\u0430 \u0441\u0442\u0440\u043E\u043A\u0438 \u0438 \u0441\u0442\u043E\u043B\
  \u0431\u0446\u044B. \u041F\u0440\u043E\u0433\u0440\u0430\u043C\u043C\u0438\u0441\
  \u0442\u044B \u0440\u0430\u0431\u043E\u0442\u0430\u044E\u0442\u2026"
lastmod: '2024-03-13T22:44:45.493161-06:00'
model: gpt-4-0125-preview
summary: "\u0420\u0430\u0431\u043E\u0442\u0430 \u0441 CSV (\u0437\u043D\u0430\u0447\
  \u0435\u043D\u0438\u044F, \u0440\u0430\u0437\u0434\u0435\u043B\u0435\u043D\u043D\
  \u044B\u0435 \u0437\u0430\u043F\u044F\u0442\u044B\u043C\u0438) \u0432\u043A\u043B\
  \u044E\u0447\u0430\u0435\u0442 \u0432 \u0441\u0435\u0431\u044F \u043E\u0431\u0440\
  \u0430\u0431\u043E\u0442\u043A\u0443 \u0442\u0435\u043A\u0441\u0442\u043E\u0432\u044B\
  \u0445 \u0434\u0430\u043D\u043D\u044B\u0445, \u0440\u0430\u0437\u0434\u0435\u043B\
  \u0435\u043D\u043D\u044B\u0445 \u0437\u0430\u043F\u044F\u0442\u044B\u043C\u0438\
  , \u043D\u0430 \u0441\u0442\u0440\u043E\u043A\u0438 \u0438 \u0441\u0442\u043E\u043B\
  \u0431\u0446\u044B."
title: "\u0420\u0430\u0431\u043E\u0442\u0430 \u0441 CSV"
weight: 37
---

## Как:


### Импорт файла CSV
```PowerShell
$data = Import-Csv -Path "path\to\yourfile.csv"
$data
```
**Пример вывода:**
```
Name        Occupation    Location
----        ----------    --------
Джон Доу    Разработчик   Нью-Йорк
Джейн Смит  Аналитик      Сан-Франциско
```

### Экспорт в файл CSV
```PowerShell
$data | Export-Csv -Path "path\to\newfile.csv" -NoTypeInformation
```
**Создает "newfile.csv" с данными из `$data`.**

### Добавление строки в данные CSV
```PowerShell
$newRow = [PSCustomObject]@{
    Name       = 'Эмили Кларк'
    Occupation = 'Дизайнер'
    Location   = 'Остин'
}
$data += $newRow
$data | Export-Csv -Path "path\to\yourfile.csv" -NoTypeInformation
```

### Выбор определенных столбцов
```PowerShell
$data | Select-Object Name, Location
```
**Пример вывода:**
```
Name        Location
----        --------
Джон Доу    Нью-Йорк
Джейн Смит  Сан-Франциско
Эмили Кларк Остин
```

## Углубленно
Исторически файлы CSV имеют корни в раннем вычислительном процессе как простой способ организации табличных данных без необходимости в сложных форматах файлов. Альтернативы, такие как XML и JSON, предлагают более богатые структуры данных, но CSV выделяется для табличных данных из-за его читаемости, низкой нагрузки и простоты редактирования с помощью простых текстовых редакторов. В PowerShell, командлеты `Import-Csv` и `Export-Csv` инкапсулируют детали реализации, обрабатывая ввод-вывод файлов и конвертацию данных в .NET объекты и из них.

## См. также
- [Документация PowerShell по Import-Csv](https://docs.microsoft.com/ru-ru/powershell/module/microsoft.powershell.utility/import-csv)
- [Документация PowerShell по Export-Csv](https://docs.microsoft.com/ru-ru/powershell/module/microsoft.powershell.utility/export-csv)
