---
title:                "Створення тимчасового файлу"
html_title:           "C: Створення тимчасового файлу"
simple_title:         "Створення тимчасового файлу"
programming_language: "Gleam"
category:             "Gleam"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/gleam/creating-a-temporary-file.md"
---

{{< edit_this_page >}}

## Що і чому?

Створення тимчасового файлу - це процес, коли програма створює файл з унікальним ім'ям, який існує лише до закінчення її роботи. Програмісти роблять це для зберігання проміжних даних, що міняються під час виконання програми.

## Як це зробити:

```Gleam
import gleam/stdlib.{Process, File}

fn main() {
  let temp_file = File.new_temp()
  File.write(temp_file, "Деякі тимчасові дані")
  Process.sleep(5000)
  File.delete(temp_file)
}
```
У вищенаведеному коді ми створюємо новий тимчасовий файл, записуємо в нього деякі дані, робимо паузу у 5 секунд, а потім видаляємо файл.

## Поглиблений розділ

Створення тимчасових файлів було необхідним з самого початку епохи комп'ютерів, коли обсяг пам'яті був дуже обмеженим. Воно допомагає зберігати проміжні дані без потреби тримати їх у пам'яті.

Альтернативою може бути використання бази даних для зберігання проміжних результатів, але це часто overkill для більшості випадків.

Особливості реалізації цього у Gleam включають використання 'File.new_temp()' для створення нового тимчасового файлу з унікальним ім'ям.

## Дивіться також

- Gleam stdlib File documentation: [https://hexdocs.pm/gleam_stdlib/gleam/file/](https://hexdocs.pm/gleam_stdlib/gleam/file/)
- Process sleeping in Gleam: [https://hexdocs.pm/gleam_stdlib/gleam/process/](https://hexdocs.pm/gleam_stdlib/gleam/process/)