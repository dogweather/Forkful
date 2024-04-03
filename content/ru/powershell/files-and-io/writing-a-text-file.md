---
changelog:
- 2024-01-29, gpt-4-0125-preview, translated from English
date: 2024-01-29 00:05:34.515110-07:00
description: "\u0421\u043E\u0437\u0434\u0430\u043D\u0438\u0435 \u0442\u0435\u043A\u0441\
  \u0442\u043E\u0432\u043E\u0433\u043E \u0444\u0430\u0439\u043B\u0430 \u2014 \u044D\
  \u0442\u043E \u0441\u043E\u0445\u0440\u0430\u043D\u0435\u043D\u0438\u0435 \u0434\
  \u0430\u043D\u043D\u044B\u0445 \u0432 \u0432\u0438\u0434\u0435 \u043F\u0440\u043E\
  \u0441\u0442\u043E\u0433\u043E \u0442\u0435\u043A\u0441\u0442\u0430 \u043D\u0430\
  \ \u0434\u0438\u0441\u043A\u0435. \u041F\u0440\u043E\u0433\u0440\u0430\u043C\u043C\
  \u0438\u0441\u0442\u044B \u0434\u0435\u043B\u0430\u044E\u0442 \u044D\u0442\u043E\
  \ \u0434\u043B\u044F \u0432\u0435\u0434\u0435\u043D\u0438\u044F \u0436\u0443\u0440\
  \u043D\u0430\u043B\u043E\u0432, \u043A\u043E\u043D\u0444\u0438\u0433\u0443\u0440\
  \u0430\u0446\u0438\u0438 \u0438\u043B\u0438 \u0445\u0440\u0430\u043D\u0435\u043D\
  \u0438\u044F\u2026"
lastmod: '2024-03-13T22:44:45.486063-06:00'
model: gpt-4-0125-preview
summary: "\u0421\u043E\u0437\u0434\u0430\u043D\u0438\u0435 \u0442\u0435\u043A\u0441\
  \u0442\u043E\u0432\u043E\u0433\u043E \u0444\u0430\u0439\u043B\u0430 \u2014 \u044D\
  \u0442\u043E \u0441\u043E\u0445\u0440\u0430\u043D\u0435\u043D\u0438\u0435 \u0434\
  \u0430\u043D\u043D\u044B\u0445 \u0432 \u0432\u0438\u0434\u0435 \u043F\u0440\u043E\
  \u0441\u0442\u043E\u0433\u043E \u0442\u0435\u043A\u0441\u0442\u0430 \u043D\u0430\
  \ \u0434\u0438\u0441\u043A\u0435."
title: "\u0421\u043E\u0437\u0434\u0430\u043D\u0438\u0435 \u0442\u0435\u043A\u0441\u0442\
  \u043E\u0432\u043E\u0433\u043E \u0444\u0430\u0439\u043B\u0430"
weight: 24
---

## Как это сделать:
Вот как записывать в текстовый файл в PowerShell; это очень просто!

Создать и записать текст в новый файл:
```PowerShell
"Hello, world!" | Out-File -FilePath .\hello.txt
```

Добавить текст в существующий файл:
```PowerShell
"Welcome to PowerShell scripting!" | Add-Content -Path .\hello.txt
```

Проверить содержимое файла:
```PowerShell
Get-Content .\hello.txt
```

Пример вывода:
```
Hello, world!
Welcome to PowerShell scripting!
```

## Глубокое погружение
Файлы PowerShell по умолчанию используют кодировку UTF-16. Раньше текстовые файлы были проще — только ASCII. Теперь `Out-File` и `Add-Content` позволяют выбрать кодировку. Если вы приверженец старой школы, существует `Set-Content`, но у него есть ограничения. Для больших файлов рассмотрите использование `[System.IO.StreamWriter]` для повышения эффективности.

## Смотрите также
Для получения дополнительных навыков работы с файлами в PowerShell посетите:
- Документацию Microsoft по [Out-File](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/out-file)
- Документацию Microsoft по [Add-Content](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.management/add-content)

Помните, практика делает идеальным. Так что приступайте к написанию скриптов!
