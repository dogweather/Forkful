---
date: 2024-01-20 17:37:30.711334-07:00
description: "Converter uma data em uma string em Rust \xE9 transformar um valor de\
  \ data/hora em um formato de texto leg\xEDvel. Fazemos isso principalmente para\
  \ mostrar\u2026"
lastmod: '2024-03-13T22:44:46.379248-06:00'
model: gpt-4-1106-preview
summary: "Converter uma data em uma string em Rust \xE9 transformar um valor de data/hora\
  \ em um formato de texto leg\xEDvel."
title: Convertendo uma data em uma string
weight: 28
---

## How to:
Vamos usar a biblioteca `chrono` porque a Rust Standard Library não trata diretamente de conversão de datas.

Adicione no seu `Cargo.toml`:

```toml
[dependencies]
chrono = "0.4"
```

A seguir, um exemplo de código:

```rust
extern crate chrono;
use chrono::{DateTime, Utc, Local};

fn main() {
    let agora_utc: DateTime<Utc> = Utc::now();
    println!("Data e hora em UTC: {}", agora_utc.format("%Y-%m-%d %H:%M:%S"));

    let agora_local: DateTime<Local> = Local::now();
    println!("Data e hora local: {}", agora_local.format("%Y-%m-%d %H:%M:%S"));
}
```

Saída de exemplo:

```
Data e hora em UTC: 2023-04-10 10:30:45
Data e hora local: 2023-04-10 13:30:45
```

## Deep Dive
Antes do `chrono`, tivemos que confiar em bibliotecas de C ou soluções menos convencionais. A biblioteca `time` também é uma alternativa, mas `chrono` é mais popular na comunidade Rust por sua riqueza de recursos e facilidade de uso.

Quando formatamos uma data, usamos especificadores de formato (linha `%Y-%m-%d %H:%M:%S`) para definir como a data será exibida. Outras linguagens de programação têm abordagens semelhantes.

Internamente, `chrono` lida com datas como timestamps (o número de segundos desde uma data específica: 1º de janeiro de 1970), o que facilita operações como comparação e aritmética de datas.

## See Also
- Chrono Documentation: https://docs.rs/chrono/0.4.19/chrono/
- Rust Date and Time Formatting: https://docs.rs/chrono/0.4.19/chrono/format/strftime/index.html
- Time Crate: https://docs.rs/time/0.3.2/time/
