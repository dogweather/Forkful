---
title:                "Обчислення дати в майбутньому або минулому"
html_title:           "Rust: Обчислення дати в майбутньому або минулому"
simple_title:         "Обчислення дати в майбутньому або минулому"
programming_language: "Rust"
category:             "Rust"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/uk/rust/calculating-a-date-in-the-future-or-past.md"
---

{{< edit_this_page >}}

## Що та навіщо?

Обчислення дати в майбутньому або минулому - це складання або віднімання днів, тижнів, місяців або років від заданої дати. Програмісти роблять це для опрацювання різних бізнес-сценаріїв, аналізу даних і оптимізації робочих процесів. 

## Як це робити:

Rust дозволяє використовувати бібліотеку Chrono для роботи з датами та часом. Спершу вам потрібно додати zпакет Chrono в ваш проект.

```Rust
[dependencies]
chrono = "0.4"
```

Разом з Chrono, ви можете обчислити дату в майбутньому або минулому:

```Rust
use chrono::{DateTime, Duration, Utc};

fn main() {
    let now: DateTime<Utc> = Utc::now();
    let in_three_days = now + Duration::days(3);
    let three_days_ago = now - Duration::days(3);
    
    println!("{}", in_three_days);
    println!("{}", three_days_ago);
}
```

Код виведе дату та час через три дні від поточного моменту і три дні назад.

## Поглиблений аналіз:

Історичний контекст: Від початку комп'ютерної ери, програмісти намагалися працювати з датами та часом. Проте, управління часом - не просте завдання через різницю в часових поясах, високосні роки та інші фактори.

Альтернативи: Rust також дозволяє використовувати інші пакети для роботи з датами та часом, такі як time або date-time.

Реалізаційні деталі: Rust використовує систему типів для забезпечення безпеки роботи з датами та часом. Наприклад, Chrono використовує типи DateTime, Date та Time для представлення різних аспектів дати та часу і забезпечує строгий контроль за введенням та обробкою даних.

## Також дивіться:

- [Chrono Documentation](https://docs.rs/chrono/0.4.11/chrono/) 
- [Rust Date and Time Manipulation with Chrono](https://www.joshmcguigan.com/blog/date-and-time-rust-chrono/)
- [Rust Programming By Example: Date and Time](https://learning.oreilly.com/library/view/rust-programming-by/9781788390637/3b3dff6d-7204-4dbd-baab-d7758391f48b.xhtml)