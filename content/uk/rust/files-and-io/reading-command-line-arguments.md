---
date: 2024-01-20 17:57:08.640435-07:00
description: "\u0427\u0438\u0442\u0430\u043D\u043D\u044F \u0430\u0440\u0433\u0443\u043C\
  \u0435\u043D\u0442\u0456\u0432 \u043A\u043E\u043C\u0430\u043D\u0434\u043D\u043E\u0433\
  \u043E \u0440\u044F\u0434\u043A\u0430 \u2013 \u0446\u0435 \u043F\u0440\u043E\u0446\
  \u0435\u0441 \u043E\u0442\u0440\u0438\u043C\u0430\u043D\u043D\u044F \u0434\u0430\
  \u043D\u0438\u0445, \u044F\u043A\u0456 \u043A\u043E\u0440\u0438\u0441\u0442\u0443\
  \u0432\u0430\u0447 \u043F\u0435\u0440\u0435\u0434\u0430\u0454 \u0432\u0430\u0448\
  \u0456\u0439 \u043F\u0440\u043E\u0433\u0440\u0430\u043C\u0456 \u043F\u0440\u0438\
  \ \u0457\u0457 \u0437\u0430\u043F\u0443\u0441\u043A\u0443. \u041F\u0440\u043E\u0433\
  \u0440\u0430\u043C\u0456\u0441\u0442\u0438 \u0432\u0438\u043A\u043E\u0440\u0438\u0441\
  \u0442\u043E\u0432\u0443\u044E\u0442\u044C \u0446\u0435 \u0434\u043B\u044F\u2026"
lastmod: '2024-03-13T22:44:48.963431-06:00'
model: gpt-4-1106-preview
summary: "\u0427\u0438\u0442\u0430\u043D\u043D\u044F \u0430\u0440\u0433\u0443\u043C\
  \u0435\u043D\u0442\u0456\u0432 \u043A\u043E\u043C\u0430\u043D\u0434\u043D\u043E\u0433\
  \u043E \u0440\u044F\u0434\u043A\u0430 \u2013 \u0446\u0435 \u043F\u0440\u043E\u0446\
  \u0435\u0441 \u043E\u0442\u0440\u0438\u043C\u0430\u043D\u043D\u044F \u0434\u0430\
  \u043D\u0438\u0445, \u044F\u043A\u0456 \u043A\u043E\u0440\u0438\u0441\u0442\u0443\
  \u0432\u0430\u0447 \u043F\u0435\u0440\u0435\u0434\u0430\u0454 \u0432\u0430\u0448\
  \u0456\u0439 \u043F\u0440\u043E\u0433\u0440\u0430\u043C\u0456 \u043F\u0440\u0438\
  \ \u0457\u0457 \u0437\u0430\u043F\u0443\u0441\u043A\u0443."
title: "\u0427\u0438\u0442\u0430\u043D\u043D\u044F \u0430\u0440\u0433\u0443\u043C\u0435\
  \u043D\u0442\u0456\u0432 \u043A\u043E\u043C\u0430\u043D\u0434\u043D\u043E\u0433\u043E\
  \ \u0440\u044F\u0434\u043A\u0430"
weight: 23
---

## Як це робити:
```Rust
use std::env;

fn main() {
    let args: Vec<String> = env::args().collect();
    
    if args.len() > 1 {
        println!("Your first argument is: {}", args[1]);
    } else {
        println!("No arguments provided!");
    }
}
```
Якщо запустити `program "Hello, world!"`, результат буде:
```
Your first argument is: Hello, world!
```
Якщо запустити просто `program`, результат буде:
```
No arguments provided!
```

## Поглиблений аналіз
Розуміння аргументів командного рядка йшло ще з часів UNIX. В Rust, метод `std::env::args` повертає ітератор аргументів. Існують альтернативи стандартній бібліотеці, наприклад, `clap` і `structopt`, що надають більше можливостей для аналізу аргументів і налаштування параметрів командного рядка. Система типів Rust і патерн `match` можуть бути використані для більш безпечної обробки аргументів.

## Див. також:
- The Rust Programming Language Book, Command Line Arguments: https://doc.rust-lang.org/book/ch12-01-accepting-command-line-arguments.html
- Crates `clap` for argument parsing: https://crates.io/crates/clap
- Crates `structopt` for defining options with structs: https://crates.io/crates/structopt
