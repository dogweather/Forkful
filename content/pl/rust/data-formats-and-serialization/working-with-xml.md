---
aliases:
- /pl/rust/working-with-xml/
date: 2024-01-26 04:35:52.849089-07:00
description: "XML, czyli eXtensible Markup Language, to jakby rozwlek\u0142y kuzyn\
  \ JSON-a. Z XML-em b\u0119dziesz si\u0119 zmaga\u0107, maj\u0105c do czynienia ze\
  \ starszymi systemami,\u2026"
lastmod: 2024-02-18 23:08:49.414083
model: gpt-4-0125-preview
summary: "XML, czyli eXtensible Markup Language, to jakby rozwlek\u0142y kuzyn JSON-a.\
  \ Z XML-em b\u0119dziesz si\u0119 zmaga\u0107, maj\u0105c do czynienia ze starszymi\
  \ systemami,\u2026"
title: Praca z XML
---

{{< edit_this_page >}}

## Co i dlaczego?
XML, czyli eXtensible Markup Language, to jakby rozwlekły kuzyn JSON-a. Z XML-em będziesz się zmagać, mając do czynienia ze starszymi systemami, oprogramowaniem dla przedsiębiorstw, lub API, które opuściły wagon JSON-a. Jest niezbędny do wymiany danych, gdzie XML utrzymuje swoją pozycję.

## Jak to zrobić:
W Rust, można obsłużyć XML za pomocą crate'ów takich jak `xml-rs`. Zainstaluj, dodając `xml-rs = "0.8"` do twojego `Cargo.toml`. Oto jak przeanalizować prosty XML:

```rust
extern crate xml;

use xml::reader::{EventReader, XmlEvent};

fn main() {
    let xml_data = r#"<book category="fiction">
    <title>Rust in Action</title>
    <author>Tim McNamara</author>
    <year>2021</year>
</book>"#;

    let parser = EventReader::from_str(xml_data);
    for e in parser {
        match e {
            Ok(XmlEvent::StartElement { name, .. }) => {
                println!("Początek: {}", name);
            }
            Ok(XmlEvent::Characters(data)) => {
                println!("Tekst: {}", data);
            }
            Ok(XmlEvent::EndElement { name }) => {
                println!("Koniec: {}", name);
            }
            Err(e) => {
                println!("Błąd: {}", e);
            }
            _ => {}
        }
    }
}
```

Wyjście:
```
Początek: book
Początek: title
Tekst: Rust in Action
Koniec: title
Początek: author
Tekst: Tim McNamara
Koniec: author
Początek: year
Tekst: 2021
Koniec: year
Koniec: book
```
Ten kod odczytuje strumień XML, obsługując elementy początkowe i końcowe oraz dane tekstowe, rejestrując każdy krok.

## Szczegółowa analiza:
XML to senior w świecie technologii, stworzony dla sieci pod koniec lat 90. Jego design promuje czytelność (zarówno dla maszyn, jak i ludzi) i obszerne dane samoopisujące.

Alternatywy? Jasne, JSON jest współczesnym wyborem dla API sieciowych, lżejszym i mniej hałaśliwym. Tymczasem YAML zdobył fanów dla konfiguracji, dzięki swojemu czystemu układowi. Ale XML nie zniknie tak szybko – ogromne infrastruktury są zbudowane na jego podstawie.

Pod kapotą, parsowanie XML w Rust opiera się na wzorcach iteratorów, utrzymując niskie zużycie pamięci i wysoką wydajność. Znajdziesz crate'y takie jak `serde-xml-rs` dla bardziej serde-podobnego doświadczenia – bonus dla tych, którzy są przyzwyczajeni do obsługi JSON-a.

## Zobacz także:
Więcej na temat Rust i XML: 
- `serde-xml-rs` dla kompatybilności Rust z serde: [https://github.com/RReverser/serde-xml-rs](https://github.com/RReverser/serde-xml-rs)
- Oficjalna dokumentacja Rust (bo nigdy nie zaszkodzi się podszkolić): [https://doc.rust-lang.org/stable/book/](https://doc.rust-lang.org/stable/book/)
