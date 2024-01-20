---
title:                "Перевірка наявності директорії"
html_title:           "Gleam: Перевірка наявності директорії"
simple_title:         "Перевірка наявності директорії"
programming_language: "Gleam"
category:             "Gleam"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/gleam/checking-if-a-directory-exists.md"
---

{{< edit_this_page >}}

## Що та навіщо?
Перевірка наявності директорії — це процес виявлення, чи існує директорія на вашому комп'ютері. Програмісти це роблять, щоб полегшити обробку помилок і забезпечити безперебійну роботу програми.

## Як це робити:
Використовуйте функцію `file_exists` з модуля `gleam/filesystem` таким чином:

```gleam
import gleam/filesystem.{file_exists}

fn main() {
  let status = file_exists("/тут/ваш/шлях")
  case status {
    Ok(True) -> 
      io.println("Директорія існує")
    _ -> 
      io.println("Директорія не існує")
  }
}
```

Якщо вказана директорія існує, виведе "Директорія існує", інакше - "Директорія не існує".

## Трохи більше інформації:
Метод перевірки наявності директорії на стеку збереження спостерігався майже з самого початку створення операційних систем. Варіативність способів та підходів до цієї проблеми залежить від мови програмування. Застосовуємо в Gleam, імперативний стиль дозволяє детективному коду працювати більш ефективно та достовірно. Тим не менше, багато мов, зокрема Хаскель або Ерланг, пропонують більш функціональний підхід, завдяки чому код стає чистішим та однозначнішим.

## Дивитись також:
Посилання на інші ресурси:

1. Документація Gleam по модулю `filesystem`: [gleam/filesystem](https://hexdocs.pm/gleam_stdlib/gleam/filesystem#file_exists)

2. SO відомий в кіл приклад перевірки наявності директорії в Python: [Stackoverflow Python Example](https://stackoverflow.com/questions/893323/how-to-find-if-directory-exists-in-python)

3. Порівняння методів перевірки існування директорії в різних мовах програмування: [Comparison of Directory Existence Checking](https://www.geekhideout.com/dir_exists.shtml).