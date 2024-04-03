---
date: 2024-01-20 17:37:37.522960-07:00
description: "Att konvertera ett datum till en str\xE4ng inneb\xE4r att omvandla datumdata\
  \ till en textrepresentation. Programmerare g\xF6r detta f\xF6r att underl\xE4tta\
  \ visning och\u2026"
lastmod: '2024-03-13T22:44:37.710509-06:00'
model: gpt-4-1106-preview
summary: "Att konvertera ett datum till en str\xE4ng inneb\xE4r att omvandla datumdata\
  \ till en textrepresentation."
title: "Omvandla ett datum till en str\xE4ng"
weight: 28
---

## Så här gör du:
```rust
use chrono::{DateTime, Utc, TimeZone};

fn main() {
    let now: DateTime<Utc> = Utc::now(); // Nuvarande datum och tid i UTC
    println!("{}", now.to_string()); // Standardkonvertering till sträng
    
    // Anpassad format
    println!("{}", now.format("%Y-%m-%d %H:%M:%S").to_string());
}

// Exempel på utskrift:
// 2023-04-05T14:30:12Z
// 2023-04-05 14:30:12
```

## Djupdykning
Historiskt har datumhantering i de flesta programmeringsspråk utvecklats från enkla tidsstämplar till rika bibliotek som hanterar tidzoner och kalenderfunktioner. Rust använder ofta `chrono`-krate för datum och tid, som erbjuder funktioner för att konvertera och formatera datum. Alternativ är Rusts standardbibliotekets `time` modul, men den är mindre kraftfull.

Vid implementering måste man hantera tidzoner, lokalisering och olika datumformat. `format`-metoden i `chrono` låter oss definiera exakt hur datumet ska se ut som en sträng genom att använda formatkoder, som `%Y-%m-%d %H:%M:%S` för det vanliga åååå-mm-dd hh:mm:ss formatet.

## Se Mer
- `chrono` krate på crates.io: https://crates.io/crates/chrono
- Rust-dokumentation för tidsformatering: https://doc.rust-lang.org/std/time/index.html
- strftime formatteringskoder: https://docs.rs/chrono/0.4.19/chrono/format/strftime/index.html
