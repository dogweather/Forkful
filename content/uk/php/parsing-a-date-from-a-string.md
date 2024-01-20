---
title:                "Аналіз дати з рядка"
html_title:           "C++: Аналіз дати з рядка"
simple_title:         "Аналіз дати з рядка"
programming_language: "PHP"
category:             "PHP"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/php/parsing-a-date-from-a-string.md"
---

{{< edit_this_page >}}

## Що і чому?

Розбір дати з рядка - це процес інтерпретації рядка з символами дати у формат, який розуміє програма. Програмісти роблять це для зручного маніпулювання даними дати і часу.

## Як це робиться:

Застосуємо стандартну функцію `strtotime()` і клас DateTime, щоб проілюструвати, як можна розібрати дату з рядка:

```PHP
<?php
// Використання strtotime():
$date = "2022-03-25";
$timestamp = strtotime($date);
echo date("d-m-Y", $timestamp);
// Виведе: 25-03-2022
```
```PHP
<?php
// Використання класу DateTime:
$date = "2022-03-25";
$datetime = new DateTime($date);
echo $datetime->format("d-m-Y");
// Виведе: 25-03-2022
```

## Детальний огляд

`strtotime()` є частиною PHP вже від версії PHP 4. Ця функція може перетворити дату, записану в текстовому форматі, у мітку часу Unix. Крім того, `strtotime()` унікальна тим, що може розпізнавати більшість форматів дати в англійській мові.

Альтернативою є клас DateTime, який був доданий у PHP 5.2.0. Він надає більше можливостей, ніж `strtotime()`, наприклад обробку виключень та більше методів маніпуляції з датами.

## Дивіться також

Для отримання детальної інформації та більшіх прикладів, перегляньте офіційну документацію PHP: 

- Manual PHP за посиланням [strtotime()](https://www.php.net/manual/uk/function.strtotime.php)
- Manual PHP за посиланням [DateTime](https://www.php.net/manual/uk/class.datetime.php)