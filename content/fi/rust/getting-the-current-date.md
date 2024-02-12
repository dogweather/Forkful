---
title:                "Nykyisen päivämäärän hankkiminen"
aliases:
- fi/rust/getting-the-current-date.md
date:                  2024-02-03T19:10:50.456938-07:00
model:                 gpt-4-0125-preview
simple_title:         "Nykyisen päivämäärän hankkiminen"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/rust/getting-the-current-date.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Mikä & Miksi?

Nykyisen päivämäärän hakeminen Rustissa on yleinen tehtävä lokitusta, aikaan perustuvia operaatioita tai yksinkertaisesti päivämäärän näyttämistä varten. Toisin kuin jotkut kielet, jotka sisältävät päivämäärän ja ajan toiminnallisuuden standardikirjastossaan, Rust kannustaa käyttämään vankkaa kolmannen osapuolen kirjastoa, chrono, perusteelliseen päivämäärän ja ajan käsittelyyn sen paremman toiminnallisuuden ja käyttöhelppouden vuoksi.

## Kuinka:

### Käyttäen Rustin standardikirjastoa
Rustin standardikirjasto tarjoaa rajoitetun, mutta nopean tavan saada nykyinen aika, vaikkakaan ei suoraan nykyistä päivämäärää kalenterimuodossa. Näin teet sen:

```rust
use std::time::{SystemTime, UNIX_EPOCH};

fn main() {
    match SystemTime::now().duration_since(UNIX_EPOCH) {
        Ok(n) => println!("Nykyinen aika: {} sekuntia Unix Epochista.", n.as_secs()),
        Err(_) => panic!("SystemTime ennen Unix Epochia!"),
    }
}
```

Tuloste:
```
Nykyinen aika: 1615390665 sekuntia Unix Epochista.
```

### Käyttäen Chrono-kirjastoa
Lisää kattavaa päivämäärän ja ajan toiminnallisuutta, mukaan lukien nykyisen päivämäärän saamisen, varten sinun tulisi käyttää `chrono`-kirjastoa. Lisää ensin `chrono` `Cargo.toml`-tiedostoosi:

```toml
[dependencies]
chrono = "0.4"
```

Sitten voit käyttää `chrono`-kirjastoa saadaksesi nykyisen päivämäärän:

```rust
extern crate chrono;
use chrono::{Local, Datelike};

fn main() {
    let now = Local::now();
    println!("Nykyinen päivämäärä: {}-{}-{}", now.year(), now.month(), now.day());
}
```

Tuloste:
```
Nykyinen päivämäärä: 2023-4-20
```

`Chrono`-kirjasto tekee päivämäärien ja aikojen käsittelystä yksinkertaista, tarjoten laajan valikoiman toiminnallisuuksia nykyisen päivämäärän hakemisen lisäksi, mukaan lukien päivämäärien ja aikojen jäsentämisen, muotoilun ja aritmeettiset operaatiot.
