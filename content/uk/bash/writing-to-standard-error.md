---
title:                "Запис в стандартний потік помилок"
date:                  2024-01-19
html_title:           "Arduino: Запис в стандартний потік помилок"
simple_title:         "Запис в стандартний потік помилок"
programming_language: "Bash"
category:             "Bash"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/bash/writing-to-standard-error.md"
---

{{< edit_this_page >}}

## Що це таке та Навіщо?
Письмо в стандартну помилку (stderr) дає змогу відділяти помилки та важливі повідомлення від основного виводу програми. Програмісти це роблять, щоб легше контролювати та обробляти виняткові умови.

## Як це робити:
```Bash
#!/bin/bash
echo "Це іде в стандартний вивід (stdout)"
echo "Це іде в стандартну помилку (stderr)" >&2
```
Вивід наказу:
```
Це іде в стандартний вивід (stdout)
Це іде в стандартну помилку (stderr)
```

## Поглиблений Огляд:
У UNIX-подібних системах stderr (дескриптор файлу 2) була визначена з самого початку як засіб ефективного логування помилок. Альтернативи, як `logger` в системах Linux, можуть відправляти помилки в системні журнали. Що стосується реалізації, записування в stderr не прив’язане до буферизації, тому повідомлення помилок виводяться негайно, що важливо для відлагодження.

## Читайте Також:
- GNU Bash документація: https://www.gnu.org/software/bash/manual/
- Розуміння потоків введення/виведення: https://tldp.org/LDP/abs/html/io-redirection.html
- Як перенаправити stderr у Bash: https://www.cyberciti.biz/faq/redirecting-stderr-to-stdout/
