---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 21:57:37.760875-07:00
description: "Een string omzetten naar kleine letters betekent elke letter in de string\
  \ veranderen in een kleine letter. Het is handig voor hoofdletterongevoelige\u2026"
lastmod: '2024-03-13T22:44:50.581078-06:00'
model: gpt-4-0125-preview
summary: Een string omzetten naar kleine letters betekent elke letter in de string
  veranderen in een kleine letter.
title: Een string omzetten naar kleine letters
weight: 4
---

## Hoe te:
```Rust
fn main() {
    let begroeting = "HeLLo, WoRlD!";
    let kleine_letters_begroeting = begroeting.to_lowercase();
    println!("{}", kleine_letters_begroeting); // "hello, world!"
}
```
Output:
```
hello, world!
```

## Diepgaande Duik
Voor de methode `.to_lowercase()`, zou je Rustaceans `.to_ascii_lowercase()` voor dezelfde taak hebben kunnen zien gebruiken, wat alleen ASCII-karakters beïnvloedde. De Rust standaardbibliotheek is geëvolueerd, en biedt `.to_lowercase()` aan voor volledige Unicode-ondersteuning—wat betekent dat het meer kan dan alleen Engels! Dit is erg belangrijk als je app de stap zet naar de bredere, meertalige wereld.

Wat zit er onder de kap? Nou, de `to_lowercase()` methode verandert niet gewoon 'A' in 'a'. Het is meer als een kleine taalkundige, kundig in de wegen van Unicode. Het volgt de Unicode-standaard om karakters correct naar kleine letters om te zetten met respect voor hun culturele nuances.

Natuurlijk, er zijn alternatieven. Je kunt een lus starten, elk karakter doorlopen, en het zelf omzetten. Maar waarom het wiel opnieuw uitvinden als de Rust standaardbibliotheek het werk al heeft gedaan?

## Zie Ook
- [Rust documentatie over `to_lowercase()`](https://doc.rust-lang.org/std/primitive.str.html#method.to_lowercase)
- [Rust String documentatie](https://doc.rust-lang.org/std/string/struct.String.html)
- [Unicode hoofdletter mapping](https://www.unicode.org/reports/tr21/tr21-5.html)
