---
title:                "Видалення символів, що відповідають патерну"
html_title:           "C: Видалення символів, що відповідають патерну"
simple_title:         "Видалення символів, що відповідають патерну"
programming_language: "Gleam"
category:             "Gleam"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/gleam/deleting-characters-matching-a-pattern.md"
---

{{< edit_this_page >}}

## Що це і навіщо?

Видалення символів, що відповідають певному шаблону, - це метод очищення вхідних даних від непотрібного шуму. Програмісти використовують це для поліпшення якості даних і забезпечення коректної роботи програми.

## Як це зробити:

Наведемо приклади кодування та вихідних даних у блоках коду 'Gleam'.

```Gleam
import gleam/regex

fn delete_pattern(str: String, pattern: String) -> Result(String, regex.Error) {
    regex.replace(pattern, str, "", all)
}
```
Ви можете використовувати цю функцію, щоб видалити певний зразок. Наприклад,
```Gleam
let output = delete_pattern("Hello, World!", "[^A-Za-z ]") // "Hello World"
```
Цей приклад видаляє всі символи, які не є літерами англійського алфавіту чи пробілами.

## Поглиблений матеріал:

Обробка рядків має довгу історію в програмуванні, і видалення символів, що відповідають певному шаблону, є одним з ключових методів у цьому процесі. Існують альтернативи, такі як фільтрування символів або розбиття рядка за певним шаблоном, але вибір завжди залежить від специфічних вимог до вашої програми. 

У деталях, функція `delete_pattern`, яку ми написали, використовує регулярні вирази бібліотеки `gleam/regex` для знаходження та видалення зазначеного шаблону у рядку. `all` аргумент дозволяє замінити всі входження.

## Дивіться також:

Додаткова інформація про роботу з рядками та регулярними виразами у Gleam доступна в офіційній документації Gleam:

- Документація Gleam: [https://gleam.run/book/tour/regular-expressions.html](https://gleam.run/book/tour/regular-expressions.html)
- Github Gleam: [https://github.com/gleam-lang/gleam](https://github.com/gleam-lang/gleam)