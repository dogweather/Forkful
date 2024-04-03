---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:19:35.409307-07:00
description: "\u0420\u043E\u0431\u043E\u0442\u0430 \u0437 CSV (Comma Separated Values,\
  \ \u0437\u043D\u0430\u0447\u0435\u043D\u043D\u044F, \u0440\u043E\u0437\u0434\u0456\
  \u043B\u0435\u043D\u0456 \u043A\u043E\u043C\u0430\u043C\u0438) \u043F\u0435\u0440\
  \u0435\u0434\u0431\u0430\u0447\u0430\u0454 \u0430\u043D\u0430\u043B\u0456\u0437\
  \ \u0442\u0430 \u0433\u0435\u043D\u0435\u0440\u0443\u0432\u0430\u043D\u043D\u044F\
  \ \u0444\u0430\u0439\u043B\u0456\u0432, \u0449\u043E \u0437\u0431\u0435\u0440\u0456\
  \u0433\u0430\u044E\u0442\u044C \u0442\u0430\u0431\u043B\u0438\u0447\u043D\u0456\
  \ \u0434\u0430\u043D\u0456 \u0443 \u043F\u0440\u043E\u0441\u0442\u043E\u043C\u0443\
  \u2026"
lastmod: '2024-03-13T22:44:49.186832-06:00'
model: gpt-4-0125-preview
summary: "\u0420\u043E\u0431\u043E\u0442\u0430 \u0437 CSV (Comma Separated Values,\
  \ \u0437\u043D\u0430\u0447\u0435\u043D\u043D\u044F, \u0440\u043E\u0437\u0434\u0456\
  \u043B\u0435\u043D\u0456 \u043A\u043E\u043C\u0430\u043C\u0438) \u043F\u0435\u0440\
  \u0435\u0434\u0431\u0430\u0447\u0430\u0454 \u0430\u043D\u0430\u043B\u0456\u0437\
  \ \u0442\u0430 \u0433\u0435\u043D\u0435\u0440\u0443\u0432\u0430\u043D\u043D\u044F\
  \ \u0444\u0430\u0439\u043B\u0456\u0432, \u0449\u043E \u0437\u0431\u0435\u0440\u0456\
  \u0433\u0430\u044E\u0442\u044C \u0442\u0430\u0431\u043B\u0438\u0447\u043D\u0456\
  \ \u0434\u0430\u043D\u0456 \u0443 \u043F\u0440\u043E\u0441\u0442\u043E\u043C\u0443\
  \ \u0442\u0435\u043A\u0441\u0442\u043E\u0432\u043E\u043C\u0443 \u0444\u043E\u0440\
  \u043C\u0430\u0442\u0456."
title: "\u0420\u043E\u0431\u043E\u0442\u0430 \u0437 CSV"
weight: 37
---

## Як це робити:
Elm не має вбудованої підтримки для аналізу або генерації CSV; натомість часто використовуються сторонні пакети, наприклад, `panosoft/elm-csv`. Нижче наведені приклади базового використання цієї бібліотеки для аналізу та генерації CSV.

### Аналіз CSV
Спочатку вам потрібно додати пакет CSV до вашого проекту Elm:

```bash
elm install panosoft/elm-csv
```

Потім ви можете аналізувати рядок CSV у список записів. Простий приклад:

```elm
import Csv

csvData : String
csvData =
   "name,age\nJohn Doe,30\nJane Smith,25"

parseResult : Result String (List (List String))
parseResult =
    Csv.parse csvData

-- Приклад виводу: Ok [["name","age"],["John Doe","30"],["Jane Smith","25"]]
```

### Генерація CSV
Для генерації рядка CSV з даних Elm використовуйте функцію `Csv.encode`:

```elm
import Csv

records : List (List String)
records =
    [ ["name", "age"]
    , ["John Doe", "30"]
    , ["Jane Smith", "25"]
    ]

csvOutput : String
csvOutput =
    Csv.encode records

-- Приклад виводу: "name,age\nJohn Doe,30\nJane Smith,25\n"
```

Цей спрощений підхід дозволяє інтегрувати функціональність CSV у ваші додатки Elm, використовуючи типізоване середовище для маніпуляції даними та обміну.
