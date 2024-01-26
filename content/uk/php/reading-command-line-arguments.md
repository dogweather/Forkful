---
title:                "Читання аргументів командного рядка"
date:                  2024-01-20T17:56:50.666949-07:00
model:                 gpt-4-1106-preview
simple_title:         "Читання аргументів командного рядка"
programming_language: "PHP"
category:             "PHP"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/php/reading-command-line-arguments.md"
---

{{< edit_this_page >}}

## What & Why? (Що і чому?)
Читання аргументів командного рядка – це процес отримання даних, переданих вашому PHP скрипту при виклику з консолі. Програмісти використовують це для створення гнучких скриптів, які можуть змінювати поведінку на основі параметрів, заданих користувачам.

## How to: (Як це зробити:)
```PHP
<?php
// Забрати аргументи, що були передані скрипту
$arguments = $argv;
unset($arguments[0]); // Перший аргумент завжди містить ім'я файлу скрипту

// Вивести аргументи
foreach ($arguments as $key => $value) {
    echo "Arg #{$key}: {$value}\n";
}

// Приклад виклику: php script.php аргумент1 аргумент2
?>
```
Приклад виводу:
```
Arg #1: аргумент1
Arg #2: аргумент2
```

## Deep Dive (Занурення у деталі):
Командний рядок існує давно, і майже всі мови програмування мають засоби для читання аргументів командного рядка. У PHP, `$argv` - це масив, який містить аргументи, а `$argc` - кількість цих аргументів. Звертайте увагу, що `$argv[0]` завжди ім'я скрипту, тому його часто ігнорують при читанні аргументів.

Альтернатива `$argv` - використання функції `getopt()`, яка пропонує більш продвинуте розпізнавання параметрів, включно з іменованими опціями та коротким форматом.

Деталі реалізації читання аргументів командного рядка в PHP досить прості, але у професійних додатках могут бути використані розгалужені бібліотеки для кращої обробки аргументів, такі як Symfony Console.

## See Also (Дивіться також):
- Офіційна документація PHP по роботі з аргументами командного рядка: [php.net/manual/en/reserved.variables.argv.php](https://www.php.net/manual/en/reserved.variables.argv.php)
- Документація функції `getopt()`: [php.net/manual/en/function.getopt.php](https://www.php.net/manual/en/function.getopt.php)
- Symfony Console компонент: [symfony.com/doc/current/components/console.html](https://symfony.com/doc/current/components/console.html)
