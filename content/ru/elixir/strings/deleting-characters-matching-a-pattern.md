---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 23:56:53.487401-07:00
description: "\u0423\u0434\u0430\u043B\u0435\u043D\u0438\u0435 \u0441\u0438\u043C\u0432\
  \u043E\u043B\u043E\u0432, \u0441\u043E\u043E\u0442\u0432\u0435\u0442\u0441\u0442\
  \u0432\u0443\u044E\u0449\u0438\u0445 \u0448\u0430\u0431\u043B\u043E\u043D\u0443\
  , \u0437\u0430\u043A\u043B\u044E\u0447\u0430\u0435\u0442\u0441\u044F \u0432 \u043F\
  \u043E\u0438\u0441\u043A\u0435 \u043E\u043F\u0440\u0435\u0434\u0435\u043B\u0451\u043D\
  \u043D\u044B\u0445 \u043F\u043E\u0441\u043B\u0435\u0434\u043E\u0432\u0430\u0442\u0435\
  \u043B\u044C\u043D\u043E\u0441\u0442\u0435\u0439 \u0441\u0438\u043C\u0432\u043E\u043B\
  \u043E\u0432 \u0438 \u0438\u0445 \u0443\u0434\u0430\u043B\u0435\u043D\u0438\u0438\
  . \u041F\u0440\u043E\u0433\u0440\u0430\u043C\u043C\u0438\u0441\u0442\u044B \u0434\
  \u0435\u043B\u0430\u044E\u0442 \u044D\u0442\u043E \u0434\u043B\u044F\u2026"
lastmod: '2024-03-13T22:44:44.397670-06:00'
model: gpt-4-0125-preview
summary: "\u0423\u0434\u0430\u043B\u0435\u043D\u0438\u0435 \u0441\u0438\u043C\u0432\
  \u043E\u043B\u043E\u0432, \u0441\u043E\u043E\u0442\u0432\u0435\u0442\u0441\u0442\
  \u0432\u0443\u044E\u0449\u0438\u0445 \u0448\u0430\u0431\u043B\u043E\u043D\u0443\
  , \u0437\u0430\u043A\u043B\u044E\u0447\u0430\u0435\u0442\u0441\u044F \u0432 \u043F\
  \u043E\u0438\u0441\u043A\u0435 \u043E\u043F\u0440\u0435\u0434\u0435\u043B\u0451\u043D\
  \u043D\u044B\u0445 \u043F\u043E\u0441\u043B\u0435\u0434\u043E\u0432\u0430\u0442\u0435\
  \u043B\u044C\u043D\u043E\u0441\u0442\u0435\u0439 \u0441\u0438\u043C\u0432\u043E\u043B\
  \u043E\u0432 \u0438 \u0438\u0445 \u0443\u0434\u0430\u043B\u0435\u043D\u0438\u0438\
  ."
title: "\u0423\u0434\u0430\u043B\u0435\u043D\u0438\u0435 \u0441\u0438\u043C\u0432\u043E\
  \u043B\u043E\u0432, \u0441\u043E\u043E\u0442\u0432\u0435\u0442\u0441\u0442\u0432\
  \u0443\u044E\u0449\u0438\u0445 \u0448\u0430\u0431\u043B\u043E\u043D\u0443"
weight: 5
---

## Как:
В Elixir используйте функцию `String.replace/4` для удаления символов, соответствующих шаблону. Посмотрите эти примеры:

```elixir
# Удалить цифры из строки
original_string = "Elixir2023Rocks!"
clean_string = String.replace(original_string, ~r/\d/, "")
IO.puts(clean_string) # Вывод: "ElixirRocks!"

# Удалить пунктуацию
punctuationless_string = String.replace(original_string, ~r/[[:punct:]]/, "")
IO.puts(punctuationless_string) # Вывод: "Elixir2023Rocks"

# Устранить пробелы
no_whitespace_string = String.replace(original_string, ~r/\s/, "")
IO.puts(no_whitespace_string) # Вывод: "Elixir2023Rocks!"
```

## Глубже в тему
Использование сопоставления с описанием для удаления символов в строках не является уникальным для Elixir; это общая возможность почти во всех языках программирования, эволюционировавшая из способностей регулярных выражений (regex) в ранних инструментах Unix, таких как `sed` и `grep`. Альтернативами `String.replace/4` могут быть использование сопоставления с образцом и рекурсии для ручного обхода и изменения строки, но этот метод обычно более многословен и сложен, что делает встроенные функции regex предпочтительными. Под капотом `String.replace/4` использует наследие Elixir от Erlang, используя мощные возможности сопоставления с образцом и манипулирования строками виртуальной машины BEAM.

## Смотрите также:
- Документация модуля `String` в Elixir: [https://hexdocs.pm/elixir/String.html](https://hexdocs.pm/elixir/String.html)
- Regex в Elixir: [https://hexdocs.pm/elixir/Regex.html](https://hexdocs.pm/elixir/Regex.html)
- 'Изучите регулярные выражения': [https://www.regular-expressions.info/tutorial.html](https://www.regular-expressions.info/tutorial.html)
- Взгляд Elixir School на строки и сопоставление с образцом: [https://elixirschool.com/en/lessons/basics/strings/](https://elixirschool.com/en/lessons/basics/strings/)
