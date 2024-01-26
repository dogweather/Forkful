---
title:                "Створення текстового файлу"
html_title:           "Arduino: Створення текстового файлу"
simple_title:         "Створення текстового файлу"
programming_language: "PHP"
category:             "PHP"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/php/writing-a-text-file.md"
---

{{< edit_this_page >}}

## Що це таке та навіщо?
Запис текстового файлу — це процес збереження даних у файл на диску. Програмісти роблять це, щоб зберегти результати, налаштування, або інші дані для майбутнього використання.

## Як робити:
```PHP
<?php
$file = 'example.txt';
$content = "Привіт! Це тестовий текст.\n";

// Відкрити файл для запису, створити якщо не існує
$fp = fopen($file, 'w');

// Перевірити відкриття файлу на помилки
if ($fp === false) {
    die('Не вдалось відкрити файл для запису');
}

// Записати контент у файл
fwrite($fp, $content);

// Закрити файл
fclose($fp);
?>
```
Sample output у файлі `example.txt`: Привіт! Це тестовий текст.

## Поглиблений Розгляд:
Запис файлів у PHP була з моменту її створення. Програмісти часто використовують `fopen()`, `fwrite()`, та `fclose()` для управління файлами, але є альтернативи: `file_put_contents()` для більш простого запису цілком. Докладніше, забезпечення безпеки під час запису важливе: слід перевіряти права доступу та уникати запису чутливих даних без шифрування.

## Дивіться Також:
- Офіційну документацію PHP про роботу з файлами: https://www.php.net/manual/en/book.filesystem.php
- Безпечний запис у файл: https://www.php.net/manual/en/function.fwrite.php#refsect1-function.fwrite-notes
- Про шифрування даних у PHP: https://www.php.net/manual/en/book.openssl.php
