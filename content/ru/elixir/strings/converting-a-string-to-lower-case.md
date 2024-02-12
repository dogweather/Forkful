---
title:                "Преобразование строки в нижний регистр"
aliases:
- /ru/elixir/converting-a-string-to-lower-case/
date:                  2024-01-28T23:56:55.352806-07:00
model:                 gpt-4-0125-preview
simple_title:         "Преобразование строки в нижний регистр"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/ru/elixir/converting-a-string-to-lower-case.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Что и Зачем?

Преобразование строки в нижний регистр заключается в изменении всех букв в строке на их форму в нижнем регистре. Программисты делают это для обеспечения консистентности в хранении данных, сравнениях и поиске.

## Как это сделать:

В Elixir это делается легко. Используйте функцию `String.downcase/1`:

```elixir
original = "LoReM IPSUM"
lowercased = String.downcase(original)

IO.puts original
IO.puts lowercased
```

Вывод:

```
LoReM IPSUM
lorem ipsum
```

## Подробнее

Обработка строк в Elixir учитывает Unicode, что очень важно для правильного преобразования в нижний регистр в разных алфавитах и письменностях. Исторически обработка строк в языках программирования не всегда учитывала эту сложность.

До современного подхода Elixir некоторые старые языки предлагали упрощенные методы, которые могли работать нормально для английского, но сталкивались с проблемами с такими языками, как турецкий, где, например, прописная 'i' не становится 'I', а становится 'İ'.

Внутренне Elixir использует маппинг регистров Unicode, чтобы справиться с этим правильно. И есть альтернативы; например, `String.downcase/2` позволяет вам указать локаль, что пригодится для учета специфики языка.

```elixir
turkish = "GÖLCÜK"
String.downcase(turkish, :tr)
```

Вывод:

```
gölcük
```

В приведённом выше примере обратите внимание на то, как символ 'I' сохраняется соответственно правилам регистра турецкого языка.

## Смотрите также

- Официальная документация модуля `String` Elixir: https://hexdocs.pm/elixir/String.html
- Маппинг регистров Unicode: https://www.unicode.org/reports/tr21/tr21-5.html
- Краткое руководство по Unicode в Elixir: https://elixir-lang.org/blog/2017/01/05/elixir-and-unicode-part-1/
