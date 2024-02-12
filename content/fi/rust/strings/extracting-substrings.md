---
title:                "Merkkijonojen osien poimiminen"
aliases:
- /fi/rust/extracting-substrings/
date:                  2024-01-20T17:46:31.935215-07:00
model:                 gpt-4-1106-preview
simple_title:         "Merkkijonojen osien poimiminen"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/rust/extracting-substrings.md"
---

{{< edit_this_page >}}

## What & Why? 
Mikä ja miksi? Substringien eli alimerkkijonojen poimiminen on prosessi, jossa otetaan osia kiinteistä merkkijonoista. Ohjelmoijat tekevät tätä tietojen eristämiseen, tietojen muotoiluun tai tekstin pohjalta tehtävään päätöksentekoon.

## How to: 
Kuinka tehdään:

```Rust
fn main() {
    let text = "Moi, Rust-ohjelmoija!";
    let start = 5;
    let end = 9;
    
    // Käytä indeksejä substringin saamiseksi
    let substring = &text[start..end];
    
    println!("Substring on: '{}'", substring); // "Substring on: 'Rust'"
    
    // Toisenlainen tapa käyttämällä `.get(..)` - metodia
    match text.get(start..end) {
        Some(sub) => println!("Toinen tapa: '{}'", sub), // "Toinen tapa: 'Rust'"
        None => println!("Virheelliset indeksit"),
    }
}
```

## Deep Dive 
Syväsukellus: Rust ei oikeastaan puhu "substringeista" vaan viipaleista, "slices". Historiallisesti viipaleet ovat Rustin yritys tarjota turvallista pääsyä merkkijonoihin paniikkien ja väärien muistiviitteiden välttämiseksi. Erona esim. Pythoniin, Rust vaatii, että viipaleet ovat voimassaolevia UTF-8 sekvenssejä, joten suora indeksointi ei aina ole mahdollista. Tämän takia `.get(..)` metodi on kätevä, sillä se palauttaa `Option`-tyypin, joka kertoo, onnistuiko leikkaus. `.chars().collect()` ja muut metodit auttavat iterointiin, jos tarvitaan enemmän kontrollia Unicode-merkkien yli.

## See Also 
Katso myös:

- Rust's official string slices documentation: [https://doc.rust-lang.org/std/primitive.str.html](https://doc.rust-lang.org/std/primitive.str.html)
- 'The Rust Programming Language' book substring section: [https://doc.rust-lang.org/book/ch04-03-slices.html#string-slices](https://doc.rust-lang.org/book/ch04-03-slices.html#string-slices)
- Rust by Example's take on strings: [https://doc.rust-lang.org/rust-by-example/std/str.html](https://doc.rust-lang.org/rust-by-example/std/str.html)
