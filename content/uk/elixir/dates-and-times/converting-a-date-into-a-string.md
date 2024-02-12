---
title:                "Перетворення дати в рядок"
aliases:
- /uk/elixir/converting-a-date-into-a-string/
date:                  2024-01-20T17:37:12.548367-07:00
model:                 gpt-4-1106-preview
simple_title:         "Перетворення дати в рядок"

tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/elixir/converting-a-date-into-a-string.md"
---

{{< edit_this_page >}}

## Що це таке та чому це важливо?
Перетворення дати у рядок дозволяє легше зберігати, виводити та обмінюватися датами. Програмісти роблять це, щоб працювати з датами як з текстом, що зручно для відображення користувачам або для форматування під час збереження в бази даних.

## Як це зробити:
```elixir
# Припустимо, у вас є дата у структурі Date
date = ~D[2023-04-15]

# Використання Date.to_string для перетворення на рядок
date_string = Date.to_string(date)
IO.puts(date_string)  # Виводить "2023-04-15"

# Для більш складного форматування можемо використати strftime з модуля "Timex" (бібліотека третьої сторони)
{:ok, timex} = Date.strptime("15-04-2023", "%d-%m-%Y")
formatted_string = Timex.format!(timex, "{WDshort}, {D} {Mshort} {YYYY}")
IO.puts(formatted_string)  # Виводить, наприклад, "Sat, 15 Apr 2023"
```

## Підводимо підсумки
Історично, форматування дат було завжди важливо для програмування, але стандарти змінювалися з часом. У Elixir, робота з датами ставала простішою завдяки модулю Date, що вийшов з версії 1.3. Використання стандартів ISO8601 є рекомендованим для обміну даними. Однак, коли потрібно локалізоване або унікальне форматування, бібліотека "Timex" часто є вибором номер один в Elixir спільноти завдяки своїй гнучкості та потужності.

## Додаткові ресурси:
- [Офіційна документація Elixir модуля Date](https://hexdocs.pm/elixir/Date.html)
- [GitHub сторінка бібліотеки Timex](https://github.com/bitwalker/timex)
- [Стандарт ISO8601](https://uk.wikipedia.org/wiki/ISO_8601)
