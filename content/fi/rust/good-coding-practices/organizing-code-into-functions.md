---
date: 2024-01-26 01:16:17.280527-07:00
description: "Koodin j\xE4rjest\xE4minen funktioihin tarkoittaa ohjelmasi jakamista\
  \ uudelleenk\xE4ytett\xE4viin, modulaarisiin palasiin, joita kutsutaan nimell\xE4\
  . Teemme sen\u2026"
lastmod: '2024-03-13T22:44:56.362164-06:00'
model: gpt-4-0125-preview
summary: "Koodin j\xE4rjest\xE4minen funktioihin tarkoittaa ohjelmasi jakamista uudelleenk\xE4\
  ytett\xE4viin, modulaarisiin palasiin, joita kutsutaan nimell\xE4."
title: "Koodin j\xE4rjest\xE4minen funktioihin"
weight: 18
---

## Kuinka:
Kuvittele, että sinulla on koodia, joka laskee ympyrän alan useita kertoja. Sen sijaan, että toistaisit kaavan, kääriydyt sen funktioon.

```Rust
fn laske_ympyran_ala(sade: f64) -> f64 {
    std::f64::consts::PI * sade.powi(2)
}

fn main() {
    let sade = 5.0;
    let ala = laske_ympyran_ala(sade);
    println!("Ympyrän ala on: {}", ala);
}
```

Tuloste:

```
Ympyrän ala on: 78.53981633974483
```

## Syväsukellus
Historiallisesti funktiot ovat matematiikasta, missä ne kuvaavat syötteitä tuloksiin. Ohjelmoinnissa ne ovat olleet olemassa jo assembly-päivistä lähtien, vaikkakin kutsuimme niitä 'aliohjelmiksi'. Rust-funktiot voivat palauttaa arvoja ja jopa muita funktioita ansiostaan ensiluokkaisille funktioille ja sulkemisille.

Vaihtoehtoja? Sisäänkirjoitettu koodi tai makrot, mutta ne ovat sotkuisia monimutkaiselle logiikalle. Oliot metodeineen ovat toinen tapa järjestää toiminnallisuutta, toisenlainen maku kuin itsenäiset funktiot.

Toteutus Rustissa on melko suoraviivaista. Funktiot ilmoittavat parametriensa tyypit ja paluutyypin. Nimeämiskonventio on 'käärmekeissi'. Sinulla on julkiset funktiot (`pub fn`) käytettäväksi moduulin ulkopuolella ja yksityiset sisäiseen käyttöön. Ja Rustissa on tämä siisti ominaisuus, ettei `return`-avainsanaa tarvita funktion viimeisen lausekkeen kohdalla.

## Katso myös
Tutustu näihin saadaksesi lisätietoja:
- The Rust Programming Language Book: [Funktiot](https://doc.rust-lang.org/book/ch03-03-how-functions-work.html)
- Rust by Example [Funktioista](https://doc.rust-lang.org/rust-by-example/fn.html)
