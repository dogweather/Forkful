---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:21:01.453294-07:00
description: "\u0420\u043E\u0431\u043E\u0442\u0430 \u0437 CSV (\u0437\u043D\u0430\u0447\
  \u0435\u043D\u043D\u044F, \u0440\u043E\u0437\u0434\u0456\u043B\u0435\u043D\u0456\
  \ \u043A\u043E\u043C\u0430\u043C\u0438) \u043F\u0435\u0440\u0435\u0434\u0431\u0430\
  \u0447\u0430\u0454 \u0447\u0438\u0442\u0430\u043D\u043D\u044F \u0442\u0430 \u0437\
  \u0430\u043F\u0438\u0441 \u0434\u0430\u043D\u0438\u0445 \u0443 \u0444\u0430\u0439\
  \u043B\u0438 CSV, \u043F\u043E\u043F\u0443\u043B\u044F\u0440\u043D\u0438\u0439 \u0444\
  \u043E\u0440\u043C\u0430\u0442 \u0434\u043B\u044F \u043F\u0440\u0435\u0434\u0441\
  \u0442\u0430\u0432\u043B\u0435\u043D\u043D\u044F \u0442\u0430\u0431\u043B\u0438\u0447\
  \u043D\u0438\u0445 \u0434\u0430\u043D\u0438\u0445 \u0443 \u0432\u0438\u0433\u043B\
  \u044F\u0434\u0456\u2026"
lastmod: '2024-03-13T22:44:49.468928-06:00'
model: gpt-4-0125-preview
summary: "\u0420\u043E\u0431\u043E\u0442\u0430 \u0437 CSV (\u0437\u043D\u0430\u0447\
  \u0435\u043D\u043D\u044F, \u0440\u043E\u0437\u0434\u0456\u043B\u0435\u043D\u0456\
  \ \u043A\u043E\u043C\u0430\u043C\u0438) \u043F\u0435\u0440\u0435\u0434\u0431\u0430\
  \u0447\u0430\u0454 \u0447\u0438\u0442\u0430\u043D\u043D\u044F \u0442\u0430 \u0437\
  \u0430\u043F\u0438\u0441 \u0434\u0430\u043D\u0438\u0445 \u0443 \u0444\u0430\u0439\
  \u043B\u0438 CSV, \u043F\u043E\u043F\u0443\u043B\u044F\u0440\u043D\u0438\u0439 \u0444\
  \u043E\u0440\u043C\u0430\u0442 \u0434\u043B\u044F \u043F\u0440\u0435\u0434\u0441\
  \u0442\u0430\u0432\u043B\u0435\u043D\u043D\u044F \u0442\u0430\u0431\u043B\u0438\u0447\
  \u043D\u0438\u0445 \u0434\u0430\u043D\u0438\u0445 \u0443 \u0432\u0438\u0433\u043B\
  \u044F\u0434\u0456 \u043F\u0440\u043E\u0441\u0442\u043E\u0433\u043E \u0442\u0435\
  \u043A\u0441\u0442\u0443."
title: "\u0420\u043E\u0431\u043E\u0442\u0430 \u0437 CSV"
weight: 37
---

## Як це зробити:
PHP надає вбудовані функції для роботи з файлами CSV, що робить читання та запис у ці файли простим, без потреби в сторонніх бібліотеках. Ось приклади, які допоможуть вам розпочати:

### Читання файлу CSV
Ви можете відкрити файл CSV і прочитати його вміст за допомогою `fopen()` у поєднанні з `fgetcsv()`:

```php
<?php
$filename = 'data.csv';
$handle = fopen($filename, "r");
if ($handle !== FALSE) {
    while (($data = fgetcsv($handle, 1000, ",")) !== FALSE) {
        $num = count($data);
        echo "Кількість полів у рядку: $num\n";
        for ($c = 0; $c < $num; $c++) {
            echo $data[$c] . "\n";
        }
    }
    fclose($handle);
}
?>
```

Цей скрипт виводить кількість полів у кожному рядку, за якими слідують вміст кожного поля.

### Запис у файл CSV
Щоб записати в файл CSV, використовуйте `fopen()` в режимі запису (`w`) та `fputcsv()`:

```php
<?php
$list = [
    ['ID', 'Ім\'я', 'Електронна пошта'],
    [1, 'John Doe', 'john@example.com'],
    [2, 'Jane Doe', 'jane@example.com']
];

$handle = fopen('users.csv', 'w');

foreach ($list as $row) {
    fputcsv($handle, $row);
}

fclose($handle);
?>
```

Цей скрипт створює файл під назвою `users.csv` і записує заголовок та два рядки даних до нього.

### Використання бібліотеки: League\Csv
Для більш розширеної роботи з CSV, бібліотека `League\Csv` пропонує повний набір можливостей. Після її встановлення через Composer (`composer require league/csv`), ви можете використовувати її для більш гнучкого читання та запису даних CSV.

#### Читання за допомогою League\Csv
```php
<?php
require 'vendor/autoload.php';

use League\Csv\Reader;

$csv = Reader::createFromPath('data.csv', 'r');
$csv->setHeaderOffset(0); // Використовується, якщо ви хочете використати перший рядок як заголовок

$results = $csv->getRecords();
foreach ($results as $row) {
    print_r($row);
}
?>
```

Цей скрипт читає `data.csv`, вважаючи перший рядок за заголовки стовпців і виводить кожен рядок як асоційований масив.

#### Запис за допомогою League\Csv
```php
<?php
require 'vendor/autoload.php';

use League\Csv\Writer;

$csv = Writer::createFromPath('users_new.csv', 'w+');

$csv->insertOne(['ID', 'Ім\'я', 'Електронна пошта']);
$csv->insertAll([
    [3, 'Alex Doe', 'alex@example.com'],
    [4, 'Anna Smith', 'anna@example.com']
]);

echo "Успішно записано у файл users_new.csv.";
?>
```

Це створює `users_new.csv` і записує заголовочний рядок, за яким слідують два рядки даних.
