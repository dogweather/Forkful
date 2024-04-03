---
date: 2024-01-20 17:51:31.230358-07:00
description: "Stringinterpolasjon lar oss flette inn verdier i en streng. Det gj\xF8\
  r koden mer lesbar og dynamisk, og sparer oss for maset med konstant plussing av\u2026"
lastmod: '2024-03-13T22:44:40.560060-06:00'
model: gpt-4-1106-preview
summary: Stringinterpolasjon lar oss flette inn verdier i en streng.
title: Interpolering av en streng
weight: 8
---

## How to: (Slik gjør du det:)
```Rust
fn main() {
    let name = "Verden";
    let greeting = format!("Hei, {}!", name);
    println!("{}", greeting);  // Skriver ut: Hei, Verden!
}
```

Enkel fletting med `format!` makroen.

```Rust
fn main() {
    let temp = 22.5;
    println!("Temperaturen er {} grader Celsius.", temp); // Temperaturen er 22.5 grader Celsius.
}
```

Direkte bruk av `println!` makroen for interpolasjon.

## Deep Dive (Dypdykk)
Historisk sett kom stringinterpolasjon fra tidlige programmeringsspråk som Perl eller Ruby. I Rust er det litt annerledes fordi Rust fokuserer på sikkerhet og ytelse. Rust bruker makroer som `format!`, `print!`, og `println!` for å utføre interpolasjon under kjøring. Alternativer til Rusts makroer inkluderer direkte strengmanipulasjon eller tredjepartsbiblioteker, men de er ikke like sikre eller effektive. Implementasjonsdetaljer inkluderer sjekking under kompilering og hindring av minnelekkasjer, takket være eierskapssystemet.

## See Also (Se også)
- [Rust Programming Language Book on Macros](https://doc.rust-lang.org/book/ch19-06-macros.html)
- [Rust by Example on Formatted Print](https://doc.rust-lang.org/rust-by-example/hello/print.html)
- [Rust Documentation on `std::fmt`](https://doc.rust-lang.org/std/fmt/)
