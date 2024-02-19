---
aliases:
- /ru/c-sharp/working-with-toml/
changelog:
- 2024-01-29, gpt-4-0125-preview, translated from English
date: 2024-01-29 00:05:10.773708-07:00
description: "TOML - \u044D\u0442\u043E \u0430\u0431\u0431\u0440\u0435\u0432\u0438\
  \u0430\u0442\u0443\u0440\u0430 \u0434\u043B\u044F Tom's Obvious, Minimal Language\
  \ (\u042F\u0432\u043D\u044B\u0439, \u041C\u0438\u043D\u0438\u043C\u0430\u043B\u0438\
  \u0441\u0442\u0438\u0447\u043D\u044B\u0439 \u042F\u0437\u044B\u043A \u0422\u043E\
  \u043C\u0430) - \u0444\u043E\u0440\u043C\u0430\u0442 \u0444\u0430\u0439\u043B\u0430\
  \ \u043A\u043E\u043D\u0444\u0438\u0433\u0443\u0440\u0430\u0446\u0438\u0438, \u043A\
  \u043E\u0442\u043E\u0440\u044B\u0439 \u043B\u0435\u0433\u043A\u043E \u0447\u0438\
  \u0442\u0430\u0435\u0442\u0441\u044F\u2026"
lastmod: 2024-02-18 23:08:57.024654
model: gpt-4-0125-preview
summary: "TOML - \u044D\u0442\u043E \u0430\u0431\u0431\u0440\u0435\u0432\u0438\u0430\
  \u0442\u0443\u0440\u0430 \u0434\u043B\u044F Tom's Obvious, Minimal Language (\u042F\
  \u0432\u043D\u044B\u0439, \u041C\u0438\u043D\u0438\u043C\u0430\u043B\u0438\u0441\
  \u0442\u0438\u0447\u043D\u044B\u0439 \u042F\u0437\u044B\u043A \u0422\u043E\u043C\
  \u0430) - \u0444\u043E\u0440\u043C\u0430\u0442 \u0444\u0430\u0439\u043B\u0430 \u043A\
  \u043E\u043D\u0444\u0438\u0433\u0443\u0440\u0430\u0446\u0438\u0438, \u043A\u043E\
  \u0442\u043E\u0440\u044B\u0439 \u043B\u0435\u0433\u043A\u043E \u0447\u0438\u0442\
  \u0430\u0435\u0442\u0441\u044F\u2026"
title: "\u0420\u0430\u0431\u043E\u0442\u0430 \u0441 TOML"
---

{{< edit_this_page >}}

## Что и Почему?
TOML - это аббревиатура для Tom's Obvious, Minimal Language (Явный, Минималистичный Язык Тома) - формат файла конфигурации, который легко читается благодаря своей ясной семантике. Программисты используют его для конфигурационных файлов, упрощают обмен данными между системами и потому что он находит баланс между читаемостью для человека и возможностью разбора для машины.

## Как сделать:
Сначала установите парсер TOML, например, `Tomlyn`. Используйте ваш менеджер пакетов:

```csharp
dotnet add package Tomlyn
```

Затем разберите TOML файл:

```csharp
using Tomlyn;
using Tomlyn.Model;
using System;

var tomlContent = @"
[owner]
name = 'Tom Preston-Werner'
dob = 1979-05-27T07:32:00Z";

var tomlTable = Toml.Parse(tomlContent).ToModel();

Console.WriteLine($"Владелец: {tomlTable["owner"]["name"]}");
// Вывод:
// Владелец: Tom Preston-Werner
```

Теперь создайте и запишите TOML:

```csharp
using Tomlyn;
using Tomlyn.Syntax;
using System;
using System.IO;

var doc = new DocumentSyntax
{
    Tables =
    {
        new TableSyntax("owner")
        {
            Items =
            {
                { "name", "Tom Preston-Werner" },
                { "dob", "1979-05-27T07:32:00Z" }
            }
        }
    }
};

var tomlString = doc.ToString();
File.WriteAllText("config.toml", tomlString);
Console.WriteLine("TOML записан в config.toml");
// Вывод:
// TOML записан в config.toml
```

## Погружение:
TOML был создан Томом Престон-Вернером, сооснователем GitHub, примерно в 2013 году в качестве реакции на ограничения существующих форматов, таких как YAML и JSON, в настройках конфигурации. Он специально разработан для конфигов с сильным акцентом на простоту и однозначность.

Альтернативные форматы конфигурации включают YAML, JSON и XML. Однако TOML выделяется тем, что он более дружелюбный к пользователю, особенно для файлов конфигурации, где ручное редактирование является обычным делом. JSON, хотя и повсеместно используем, менее читаем для сложных конфигов, а XML является многословным. YAML, хотя и схож по читаемости, может стать сложным при интенсивном использовании пробелов и имеет риски безопасности с определенным содержанием.

С точки зрения реализации, TOML фокусируется на четком отображении в хеш-таблицу, обеспечивая предсказуемость извлечения данных. С выпуском версии 1.0.0 TOML утвердил свои спецификации, улучшив стабильность и поддержку инструментария.

## Смотрите также:
- Официальный репозиторий и спецификация TOML на GitHub: [github.com/toml-lang/toml](https://github.com/toml-lang/toml)
- Tomlyn, библиотека для .NET: [github.com/xoofx/Tomlyn](https://github.com/xoofx/Tomlyn)
