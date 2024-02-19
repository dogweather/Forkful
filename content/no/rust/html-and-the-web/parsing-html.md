---
aliases:
- /no/rust/parsing-html/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:12:57.416671-07:00
description: "\xC5 parse HTML i Rust handler om \xE5 trekke ut data fra HTML-dokumenter,\
  \ som er essensielt for web scraping, datautvinning eller bygging av nett-crawlere.\u2026"
lastmod: 2024-02-18 23:08:53.682775
model: gpt-4-0125-preview
summary: "\xC5 parse HTML i Rust handler om \xE5 trekke ut data fra HTML-dokumenter,\
  \ som er essensielt for web scraping, datautvinning eller bygging av nett-crawlere.\u2026"
title: Analysering av HTML
---

{{< edit_this_page >}}

## Hva & Hvorfor?

Å parse HTML i Rust handler om å trekke ut data fra HTML-dokumenter, som er essensielt for web scraping, datautvinning eller bygging av nett-crawlere. Programmerere gjør dette for å automatisere innsamlingen av informasjon fra nettet, analysere webinnhold eller migrere innhold fra en plattform til en annen.

## Hvordan:

For å parse HTML i Rust, vil du ofte bruke `scraper` crate, som gir et høynivå grensesnitt for å traversere og manipulere HTML-dokumenter.

Først, legg til `scraper` i din `Cargo.toml`:

```toml
[dependencies]
scraper = "0.12.0"
```

Deretter, her er et enkelt eksempel som trekker ut alle lenke-URL-er fra en gitt HTML-streng:

```rust
extern crate scraper;

use scraper::{Html, Selector};

fn main() {
    let html = r#"
    <html>
    <body>
        <a href="http://example.com/1">Lenke 1</a>
        <a href="http://example.com/2">Lenke 2</a>
    </body>
    </html>
    "#;

    let document = Html::parse_document(html);
    let selector = Selector::parse("a").unwrap();

    for element in document.select(&selector) {
        let link = element.value().attr("href").unwrap();
        println!("Fant lenke: {}", link);
    }
}
```

Utdata:

```
Fant lenke: http://example.com/1
Fant lenke: http://example.com/2
```

I dette eksemplet parser vi et enkelt HTML-dokument for å finne alle `<a>`-elementene og trekke ut deres `href`-attributter, som effektivt skriver ut URL-ene til alle lenkene i dokumentet. `Scraper`-biblioteket forenkler HTML-parsing og valg av spesifikke elementer ved bruk av CSS-selektorer, noe som gjør det til et foretrukket valg for web scraping-oppgaver i Rust.
