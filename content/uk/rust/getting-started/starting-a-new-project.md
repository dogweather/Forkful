---
title:                "Починаємо новий проект"
aliases:
- /uk/rust/starting-a-new-project/
date:                  2024-01-20T18:04:27.644906-07:00
model:                 gpt-4-1106-preview
simple_title:         "Починаємо новий проект"

tag:                  "Getting Started"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/rust/starting-a-new-project.md"
---

{{< edit_this_page >}}

## What & Why? (Що та Навіщо?)
Створення нового проекту — це як відкриття чистої книги для ваших ідей. Програмісти починають нові проєкти, щоб реалізувати унікальні рішення чи випробувати нові технології.

## How to: (Як це зробити:)
```Rust
// Інсталюємо Rust і Cargo, якщо ще не:
// $ curl https://sh.rustup.rs -sSf | sh

// Створюємо новий проект за допомогою Cargo
// $ cargo new my_project
// $ cd my_project

// Ось як виглядає main.rs для стандартного "Hello, world!" проекту:
fn main() {
    println!("Привіт, світ!");
}

// Компілюємо і запускаємо проект:
// $ cargo run

// Вивід:
// Привіт, світ!
```

## Deep Dive (Поглиблений Розбір)
Створення проекту в Rust може здатися новачкам складним, але Cargo робить це легким. У 2015 році Cargo став офіційним інструментом для управління залежностями і збірки проектів Rust. Альтернативи Cargo існують, але є менш популярними. Наприклад, Makefiles чи bash скрипти, що все ще використовуються старшими проектами або тими, кому потрібен більший контроль.

Рішення скористатися Cargo для нового проекту означає не тільки створення структурованої системи файлів, але й налаштування файлу `Cargo.toml`, де вказуються метадата проекту та залежності. Cargo дозволяє з легкістю додавати бібліотеки, керувати версіями та створювати складні проекти з багатьма цілями (binaries) і залежностями.

## See Also (Дивись Також)
- Документація Cargo [Cargo Book](https://doc.rust-lang.org/cargo/)
- Навчання Rust з нуля [Rustlings](https://github.com/rust-lang/rustlings)
- Rust by Example, практичне навчання на прикладах [Rust by Example](https://doc.rust-lang.org/stable/rust-by-example/)
