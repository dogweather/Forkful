---
title:                "Створення тимчасового файлу"
html_title:           "C: Створення тимчасового файлу"
simple_title:         "Створення тимчасового файлу"
programming_language: "Ruby"
category:             "Ruby"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/ruby/creating-a-temporary-file.md"
---

{{< edit_this_page >}}

## Що і чому?

Створення тимчасових файлів - це процес записування тимчасових даних на ваш хард-драйв. Програмісти роблять це для збереження проміжних даних або працюють з великими файлами, які не можуть бути збереженні в пам'яті.

## Як це зробити: 

Ось приклад коду в Ruby що створює тимчасовий файл:

```Ruby
require 'tempfile'

temp_file = Tempfile.new('test')
puts temp_file.path   # Виведе шлях файла
temp_file.write('Доброго дня, Україно!') # Запишемо деякі дані
temp_file.rewind   # Повернемо курсор до початку файла
puts temp_file.read   # Прочитає та виведе 'Доброго дня, Україно!'

temp_file.close
temp_file.unlink   # Видалить тимчасовий файл
```
## Поглиблення

**Історичний контекст:** 
Методи роботи з тимчасовими файлами у Ruby були впроваджені в стандартну бібліотеку рубіну з першої версії мови.

**Альтернативи:** 
У оперативній системі Linux можна використовувати `/dev/shm`, для тимчасового зберігання даних в RAM, що є швидше, ніж зберігання на диску.

**Деталі виконання:** 
Ruby створює тимчасовий файл в директорії, що визначена ваших системних налаштувань. Якщо ця директорія не визначена, Ruby вибирає системну тимчасову папку.

## Дивитися також:

* [Документація Ruby про клас Tempfile](https://ruby-doc.org/stdlib-2.5.1/libdoc/tempfile/rdoc/Tempfile.html)
* [Ruby API документація про IO і дискові операції](https://ruby-doc.org/core-3.2.0/IO.html)
* [Уроки по Ruby від Codecademy](https://www.codecademy.com/learn/learn-ruby)