---
title:                "Визначення довжини рядка"
date:                  2024-01-20T17:48:05.998240-07:00
model:                 gpt-4-1106-preview
simple_title:         "Визначення довжини рядка"
programming_language: "PHP"
category:             "PHP"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/php/finding-the-length-of-a-string.md"
---

{{< edit_this_page >}}

## What & Why?
Що таке довжина рядка та чому ми це вимірюємо? У PHP, як і в багатьох мовах програмування, довжина рядка – це кількість символів у ньому. Це важливо для валідації введених даних, обробки тексту та збереження пам’яті.

## How to:
Знайдемо довжину рядка за допомогою функції `strlen`.
```PHP
<?php
$text = "Привіт, світ!";
echo strlen($text); // Покаже: 21
?>
```
Зверніть увагу, що в UTF-8 кожен український символ може використовувати більше одного байта.

## Deep Dive:
У минулому, до UTF-8, ми просто рахували байти. Тепер, з різноманітністю символів та ємністю, `strlen` не завжди надійна для багатобайтових кодувань. Використовуйте `mb_strlen` для точного підрахунку в UTF-8.

```PHP
<?php
echo mb_strlen($text, "UTF-8"); // Правильно покаже: 12
?>
```

Альтернативи `strlen` інколи потрібні, наприклад `substr_count` для підрахунку певних символів. На рівні реалізації, PHP оперує складніше, оскільки обробляє різні кодування та розміри символів.

## See Also:
* Документація PHP про `strlen`: https://www.php.net/manual/uk/function.strlen.php
* Документація PHP про `mb_strlen`: https://www.php.net/manual/uk/function.mb-strlen.php
* Про кодування UTF-8: https://uk.wikipedia.org/wiki/UTF-8
