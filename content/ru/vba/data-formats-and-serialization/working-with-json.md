---
aliases:
- /ru/vba/working-with-json/
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 22:06:15.272818-07:00
description: "JSON (JavaScript Object Notation) \u2014 \u044D\u0442\u043E \u043B\u0435\
  \u0433\u043A\u043E\u0432\u0435\u0441\u043D\u044B\u0439 \u0444\u043E\u0440\u043C\u0430\
  \u0442 \u043E\u0431\u043C\u0435\u043D\u0430 \u0434\u0430\u043D\u043D\u044B\u043C\
  \u0438, \u043A\u043E\u0442\u043E\u0440\u044B\u0439 \u043B\u0435\u0433\u043A\u043E\
  \ \u0447\u0438\u0442\u0430\u0435\u0442\u0441\u044F \u0438 \u043F\u0438\u0448\u0435\
  \u0442\u0441\u044F \u043B\u044E\u0434\u044C\u043C\u0438, \u0430 \u0442\u0430\u043A\
  \u0436\u0435 \u043B\u0435\u0433\u043A\u043E \u0430\u043D\u0430\u043B\u0438\u0437\
  \u0438\u0440\u0443\u0435\u0442\u0441\u044F \u0438\u2026"
lastmod: 2024-02-18 23:08:56.813087
model: gpt-4-0125-preview
summary: "JSON (JavaScript Object Notation) \u2014 \u044D\u0442\u043E \u043B\u0435\
  \u0433\u043A\u043E\u0432\u0435\u0441\u043D\u044B\u0439 \u0444\u043E\u0440\u043C\u0430\
  \u0442 \u043E\u0431\u043C\u0435\u043D\u0430 \u0434\u0430\u043D\u043D\u044B\u043C\
  \u0438, \u043A\u043E\u0442\u043E\u0440\u044B\u0439 \u043B\u0435\u0433\u043A\u043E\
  \ \u0447\u0438\u0442\u0430\u0435\u0442\u0441\u044F \u0438 \u043F\u0438\u0448\u0435\
  \u0442\u0441\u044F \u043B\u044E\u0434\u044C\u043C\u0438, \u0430 \u0442\u0430\u043A\
  \u0436\u0435 \u043B\u0435\u0433\u043A\u043E \u0430\u043D\u0430\u043B\u0438\u0437\
  \u0438\u0440\u0443\u0435\u0442\u0441\u044F \u0438\u2026"
title: "\u0420\u0430\u0431\u043E\u0442\u0430 \u0441 JSON"
---

{{< edit_this_page >}}

## Что и Почему?

JSON (JavaScript Object Notation) — это легковесный формат обмена данными, который легко читается и пишется людьми, а также легко анализируется и генерируется машинами. Программисты используют JSON для передачи данных между сервером и веб-приложением или для хранения информации в структурированном, доступном виде в различных программных средах, включая Visual Basic для приложений (VBA).

## Как:

VBA изначально не поддерживает разбор или генерацию JSON, поэтому мы будем использовать скриптовый язык, такой как JScript (через объект ScriptControl) для разбора строк JSON и создания объектов JSON. Вот как вы можете разобрать строку JSON в VBA:

```basic
Function ParseJSON(ByVal jsonString As String) As Object
    Dim scriptControl As Object
    Set scriptControl = CreateObject("MSScriptControl.ScriptControl")
    scriptControl.Language = "JScript"
    
    scriptControl.Eval "var obj = (" & jsonString & ")"
    Set ParseJSON = scriptControl.CodeObject.obj
End Function

Sub DemoParseJSON()
    Dim jsonString As String
    jsonString = "{""name"":""Джон"", ""age"":30, ""city"":""Нью-Йорк""}"
    
    Dim parsed As Object
    Set parsed = ParseJSON(jsonString)
    
    MsgBox "Имя: " & parsed.name & ", Возраст: " & parsed.age & ", Город: " & parsed.city
End Sub
```

Для генерации JSON вы можете использовать подобный подход, строя строку JSON через конкатенацию:

```basic
Function GenerateJSON(name As String, age As Integer, city As String) As String
    GenerateJSON = "{""name"":""" & name & """, ""age"":" & age & ", ""city"":""" & city & """}"
End Function

Sub DemoGenerateJSON()
    Dim jsonString As String
    jsonString = GenerateJSON("Джейн", 28, "Лос-Анджелес")
    
    MsgBox jsonString
End Sub
```

## Глубокое погружение

Показанные методы используют ScriptControl для работы с JSON, по сути передавая работу движку JavaScript. Это творческий обходной путь, но не обязательно самый эффективный или современный способ работы с JSON в контексте VBA. В более сложных приложениях этот метод может стать громоздким и ввести проблемы с производительностью или безопасностью, поскольку ScriptControl выполняется в среде, имеющей полный доступ к хост-компьютеру.

Другие программные среды, такие как Python или JavaScript, предлагают встроенную поддержку для JSON, что делает их более подходящими для приложений, требующих обширной манипуляции с JSON. Эти языки предоставляют комплексные библиотеки, которые облегчают не только разбор и генерацию, но и запросы и форматирование данных JSON.

Несмотря на эти ограничения в VBA, понимание того, как работать с JSON, жизненно важно в мире, где обмен данными через веб и файлы конфигурации преимущественно оформлены в формате JSON. Для программистов VBA освоение этих техник открывает возможности для интеграции с веб-API, интерпретации файлов конфигурации или даже создания простых веб-приложений. Однако, когда проекты растут в сложности или требуют высокой производительности, разработчики могут рассмотреть использование более дружелюбных к JSON программных сред.
