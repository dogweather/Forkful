---
title:                "Запис в стандартний потік помилок"
date:                  2024-01-19
html_title:           "Arduino: Запис в стандартний потік помилок"
simple_title:         "Запис в стандартний потік помилок"
programming_language: "PHP"
category:             "PHP"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/php/writing-to-standard-error.md"
---

{{< edit_this_page >}}

## Що це та навіщо?
Стандартний потік помилок (stderr) – це канал для виведення повідомлень про помилки та діагностику. Програмісти використовують stderr, щоб розділити основний вивід даних від повідомлень про помилки, що полегшує обробку та аналіз проблем.

## Як це зробити:
```PHP
<?php
// Просте виведення в stderr.
file_put_contents('php://stderr', "Це повідомлення помилки.\n");

// Використання fprintf для виведення в stderr.
$err_msg = "Помилка! Неправильне введення даних.\n";
fprintf(STDERR, $err_msg);
?>
```
Вивід в консолі (stderr):
```
Це повідомлення помилки.
Помилка! Неправильне введення даних.
```

## Поглиблений огляд:
До введення stderr у Unix-системах усі повідомлення йшли в стандартний потік виводу (stdout), що ускладнювало одночасний перегляд результатів програми та помилок. В PHP, `php://stderr` – це спеціальний потік, що дозволяє виводити дані прямо в stderr. Альтернативно, можна використовувати константу `STDERR` за допомогою `fwrite` або `fprintf`. Потік stderr відкритий за замовчуванням та доступний у будь-який час під час виконання сценарію.

## Дивіться також:
1. Офіційна документація PHP про роботу з потоками: https://www.php.net/manual/uk/wrappers.php.php
2. Більше інформації про stdio в Unix: https://en.wikipedia.org/wiki/Standard_streams
3. Рекомендації по виведенню помилок за допомогою `trigger_error()` в PHP: https://www.php.net/manual/uk/function.trigger-error.php
