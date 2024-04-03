---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:12:56.952104-07:00
description: "Att tolka HTML i Rust handlar om att extrahera data fr\xE5n HTML-dokument,\
  \ vilket \xE4r v\xE4sentligt f\xF6r webbskrapning, dataextraktion eller att bygga\
  \ webb-\u2026"
lastmod: '2024-03-13T22:44:37.696102-06:00'
model: gpt-4-0125-preview
summary: "Att tolka HTML i Rust handlar om att extrahera data fr\xE5n HTML-dokument,\
  \ vilket \xE4r v\xE4sentligt f\xF6r webbskrapning, dataextraktion eller att bygga\
  \ webb-crawlers."
title: Tolka HTML
weight: 43
---

## Hur gör man:
För att tolka HTML i Rust kommer du ofta att använda `scraper`-paketet, som erbjuder ett högnivågränssnitt för att traversera och manipulera HTML-dokument.

Först, lägg till `scraper` i din `Cargo.toml`:

```toml
[dependencies]
scraper = "0.12.0"
```

Nästa, här är ett enkelt exempel som extraherar alla länk-URL:er från en given HTML-sträng:

```rust
extern crate scraper;

use scraper::{Html, Selector};

fn main() {
    let html = r#"
    <html>
    <body>
        <a href="http://example.com/1">Länk 1</a>
        <a href="http://example.com/2">Länk 2</a>
    </body>
    </html>
    "#;

    let dokument = Html::parse_document(html);
    let selector = Selector::parse("a").unwrap();

    for element i dokument.select(&selector) {
        let länk = element.value().attr("href").unwrap();
        println!("Hittade länk: {}", länk);
    }
}
```

Utskrift:

```
Hittade länk: http://example.com/1
Hittade länk: http://example.com/2
```

I detta exempel tolkar vi ett enkelt HTML-dokument för att hitta alla `<a>`-element och extrahera deras `href`-attribut, vilket effektivt skriver ut URL:erna för alla länkarna i dokumentet. `scraper`-biblioteket förenklar HTML-tolkning och val av specifika element med hjälp av CSS-selektorer, vilket gör det till ett givet val för uppgifter inom webbskrapning i Rust.
