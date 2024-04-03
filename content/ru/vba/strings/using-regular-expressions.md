---
changelog:
- 2024-02-01, gpt-4-0125-preview, translated from English
date: 2024-02-01 22:05:31.151079-07:00
description: "\u0420\u0435\u0433\u0443\u043B\u044F\u0440\u043D\u044B\u0435 \u0432\u044B\
  \u0440\u0430\u0436\u0435\u043D\u0438\u044F (regex) \u0432 Visual Basic \u0434\u043B\
  \u044F \u043F\u0440\u0438\u043B\u043E\u0436\u0435\u043D\u0438\u0439 (VBA) \u043F\
  \u0440\u0435\u0434\u043E\u0441\u0442\u0430\u0432\u043B\u044F\u044E\u0442 \u043C\u043E\
  \u0449\u043D\u044B\u0439 \u0441\u043F\u043E\u0441\u043E\u0431 \u043F\u043E\u0438\
  \u0441\u043A\u0430, \u0441\u043E\u043F\u043E\u0441\u0442\u0430\u0432\u043B\u0435\
  \u043D\u0438\u044F \u0438 \u043C\u0430\u043D\u0438\u043F\u0443\u043B\u044F\u0446\
  \u0438\u0438 \u0441\u0442\u0440\u043E\u043A\u0430\u043C\u0438. \u041F\u0440\u043E\
  \u0433\u0440\u0430\u043C\u043C\u0438\u0441\u0442\u044B\u2026"
lastmod: '2024-03-13T22:44:44.723594-06:00'
model: gpt-4-0125-preview
summary: "\u0420\u0435\u0433\u0443\u043B\u044F\u0440\u043D\u044B\u0435 \u0432\u044B\
  \u0440\u0430\u0436\u0435\u043D\u0438\u044F (regex) \u0432 Visual Basic \u0434\u043B\
  \u044F \u043F\u0440\u0438\u043B\u043E\u0436\u0435\u043D\u0438\u0439 (VBA) \u043F\
  \u0440\u0435\u0434\u043E\u0441\u0442\u0430\u0432\u043B\u044F\u044E\u0442 \u043C\u043E\
  \u0449\u043D\u044B\u0439 \u0441\u043F\u043E\u0441\u043E\u0431 \u043F\u043E\u0438\
  \u0441\u043A\u0430, \u0441\u043E\u043F\u043E\u0441\u0442\u0430\u0432\u043B\u0435\
  \u043D\u0438\u044F \u0438 \u043C\u0430\u043D\u0438\u043F\u0443\u043B\u044F\u0446\
  \u0438\u0438 \u0441\u0442\u0440\u043E\u043A\u0430\u043C\u0438."
title: "\u0418\u0441\u043F\u043E\u043B\u044C\u0437\u043E\u0432\u0430\u043D\u0438\u0435\
  \ \u0440\u0435\u0433\u0443\u043B\u044F\u0440\u043D\u044B\u0445 \u0432\u044B\u0440\
  \u0430\u0436\u0435\u043D\u0438\u0439"
weight: 11
---

## Как использовать:
Чтобы использовать регулярные выражения в VBA, сначала нужно включить библиотеку Microsoft VBScript Regular Expressions. В редакторе VBA перейдите в `Инструменты` -> `Ссылки`, затем отметьте `Microsoft VBScript Regular Expressions 5.5`.

Вот простой пример для поиска существования шаблона в строке:

```vb
Sub FindPattern()
    Dim regex As Object
    Set regex = CreateObject("VBScript.RegExp")

    With regex
        .Global = True
        .IgnoreCase = True
        .Pattern = "\bis\b"  ' Ищет слово "is"
    End With
    
    Dim testString As String
    testString = "This is a test string."
    
    If regex.Test(testString) Then
        MsgBox "Шаблон найден."
    Else
        MsgBox "Шаблон не найден."
    End If
End Sub
```

Чтобы заменить шаблон в строке:

```vb
Sub ReplacePattern()
    Dim regex As Object, replacedString As String
    Set regex = CreateObject("VBScript.RegExp")
    
    With regex
        .Global = True
        .IgnoreCase = False
        .Pattern = "\s"  ' Соответствует любому пробельному символу
    End With
    
    replacedString = regex.Replace("This is a test string.", "_")
    MsgBox replacedString  ' Выводит: "This_is_a_test_string."
End Sub
```

## Погружение в детали
Включение регулярных выражений в языки программирования часто восходит к инструментам Unix 1970-х годов. VBA интегрировал regex через библиотеку VBScript Regular Expressions, подчеркивая его значимость в задачах обработки текста даже в приложениях, традиционно не ассоциируемых с интенсивной манипуляцией текстом, таких как Excel или Access.

Несмотря на их мощь, regex в VBA иногда может быть менее интуитивно понятным или производительным по сравнению с более современными реализациями в языках, таких как Python или JavaScript. Например, модуль `re` в Python предлагает обширную поддержку именованных групп и более сложных возможностей сопоставления с образцом, обеспечивая более чистый и потенциально более читаемый подход. Однако, работая в экосистеме VBA, регулярные выражения остаются бесценным инструментом для задач, требующих сопоставления шаблонов или манипуляции текстом. Потеря эффективности часто незначительна на фоне удобства и возможностей, которые regex предоставляет при работе со строками в офисных приложениях.
