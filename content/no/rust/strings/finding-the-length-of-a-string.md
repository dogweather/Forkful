---
aliases:
- /no/rust/finding-the-length-of-a-string/
date: 2024-01-20 17:48:09.542464-07:00
description: "\xC5 finne lengden p\xE5 en streng i Rust betyr \xE5 telle antall tegn\
  \ den inneholder. Programmerere trenger denne informasjonen for \xE5 validere inndata,\
  \ manipulere\u2026"
lastmod: 2024-02-18 23:08:53.676455
model: gpt-4-1106-preview
summary: "\xC5 finne lengden p\xE5 en streng i Rust betyr \xE5 telle antall tegn den\
  \ inneholder. Programmerere trenger denne informasjonen for \xE5 validere inndata,\
  \ manipulere\u2026"
title: "Finn lengden p\xE5 en streng"
---

{{< edit_this_page >}}

## Hva & Hvorfor?
Å finne lengden på en streng i Rust betyr å telle antall tegn den inneholder. Programmerere trenger denne informasjonen for å validere inndata, manipulere tekst, eller bare for å sjekke størrelsen på en streng.

## Hvordan gjøre det:
```rust
fn main() {
    let tekst = "Hei, Norge!";
    let lengde = tekst.chars().count();
    
    println!("Lengden av '{}' er {}", tekst, lengde);
}
```
Output:
```
Lengden av 'Hei, Norge!' er 11
```

## Dypdykk
Helt fra Rusts tidlige dager var det å finne lengden på en streng ikke alltid så rett fram. Rusts `String` type er kodet i UTF-8, noe som gjør `.len()` metoden mindre intuitiv; den returnerer antall bytes, ikke antall tegn. Derfor bruker vi `.chars().count()` for å få det faktiske antall tegn. Et alternativ er `.bytes().count()` om man heller vil ha antall bytes, eller `.graphemes(true).count()` (fra `unicode-segmentation` craten) for å få antall grafemer, som kan være nyttig ved mer kompleks tekstbehandling.

## Se også
- Rust dokumentasjonen for strenger: https://doc.rust-lang.org/std/string/
- `unicode-segmentation` crate for å håndtere grafemer: https://crates.io/crates/unicode-segmentation
