---
title:                "Розрахунок дати в майбутньому або минулому"
html_title:           "Gleam: Розрахунок дати в майбутньому або минулому"
simple_title:         "Розрахунок дати в майбутньому або минулому"
programming_language: "Gleam"
category:             "Gleam"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/gleam/calculating-a-date-in-the-future-or-past.md"
---

{{< edit_this_page >}}

## Що і Навіщо?

Обчислення дати в майбутньому або минулому - це процес визначення точної дати, виходячи від конкретного періоду часу, доданого або віднятого від певної стартової дати. Програмісти роблять це для вирішення задач, пов'язаних з часом, таких як планування подій, обчислення термінів та відстеження часу.

## Як це робити:

```Gleam
import gleam/date.{iso_week_days, add, from_iso_date_string, new}

fn main() {
  let start_date = from_iso_date_string("2020-05-07")
    |> Result.unwrap(_, _)
  let new_date = start_date
    |> add(_, iso_week_days(3))
  }
  |> Ok(_)
  
  case new_date {
      Error(e) -> io.println("Error: " ++ e)
      Ok(date) -> io.println(from_iso_date_string(date))
  }
}
```

Виведення:
```Gleam
2020-05-10
```

## Глибше Занурення

1. **Історичний контекст**: Обчислення дат було основою для числення часу від давніх часів. Воно стало ще більш важливим з початком ери комп'ютерів, коли зробилось необхідним розрахувати дати автоматично для різних застосунків.

2. **Альтернативи**: Існують інші способи обчислення дати в майбутньому або минулому в Gleam, наприклад, використовуючи функції `datetime.add` або `datetime.subtract`. Вибір залежить від конкретного сценарію.

3. **Деталі реалізації**: в `gleam/date`, додавання днів до дати обчислюється шляхом конвертації дати в юліанську дату, додаванням потрібної кількости днів, а потім конвертацією назад в григоріанську дату.

## Дивіться також:

1. [Документація `gleam/date`](https://hexdocs.pm/gleam_stdlib/date.html)
2. [Gleam Cookbook: Working with Dates and Times](https://gleam.run/book/tour/dates-and-times.html)
3. [Gleam Forum: Date Calculations](https://gleam.run/forum/t/date-calculations/145)