---
title:                "Аналіз дати з рядка"
html_title:           "C++: Аналіз дати з рядка"
simple_title:         "Аналіз дати з рядка"
programming_language: "Gleam"
category:             "Gleam"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/gleam/parsing-a-date-from-a-string.md"
---

{{< edit_this_page >}}

## Що та чому?
Парсинг дати з рядка - це процес читання даних у вигляді тексту і перетворення їх на дату відповідного формату. Програмісти роблять це, щоб зручно та ефективно обробляти та маніпулювати датами в межах коду.

## Як це робити:
У Gleam це можна зробити за допомогою бібліотеки `date_time`. Спочатку вам потрібно її імпортувати.

```Gleam
import gleam/date_time.{StringParseError, convert_iso8601_date}
```

Тепер ви можете перетворювати стрічки у дати таким чином:

```Gleam
let date_result = convert_iso8601_date("2020-01-01")
case date_result {
  Error(e: StringParseError) -> io.println(e)
  Ok(date) -> io.println(date)
}
```

Якщо ви запустите цей код, та стрічка "2020-01-01" буде перетворена в дату.

## Поглиблений огляд
Парсинг дати з рядку став поширеним з виникненням потреби обробляти та представляти дати в коді. Існують альтернативні методи роботи з датами, такі як работа з датами як з числами. Однак, парсинг дати з рядка широко використовується через його зручність та гнучкість. Використання методу `convert_iso8601_date` в Gleam використовує стандарт формату дати ISO 8601. Помилки в обробці рядків перехоплюються та повертаються як тип `StringParseError`.

## Додатково
1. Документація по бібліотеці Gleam `date_time`: [link](https://hexdocs.pm/gleam_stdlib/gleam/date_time.html)
2. Подробиці формату дати ISO 8601: [link](https://uk.wikipedia.org/wiki/ISO_8601)