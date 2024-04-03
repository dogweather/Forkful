---
date: 2024-01-26 04:19:48.386676-07:00
description: "TOML (Tom's Obvious, Minimal Language) on datan serialisointiformaatti,\
  \ joka on helppo lukea sen selke\xE4n semantiikan ansiosta. Ohjelmoijat k\xE4ytt\xE4\
  v\xE4t\u2026"
lastmod: '2024-03-13T22:44:56.888967-06:00'
model: gpt-4-0125-preview
summary: "TOML (Tom's Obvious, Minimal Language) on datan serialisointiformaatti,\
  \ joka on helppo lukea sen selke\xE4n semantiikan ansiosta."
title: "Ty\xF6skentely TOML:n kanssa"
weight: 39
---

## Kuinka:
Työskennellessäsi TOMLin kanssa C++:ssa, tarvitset kirjaston kuten `toml++`. Tässä nopea aloitus:

```C++
#include <toml++/toml.h>
#include <iostream>
#include <fstream>

int main() {
    // Jäsentää TOMLin tiedostosta
    std::ifstream ifs("config.toml");
    auto config = toml::parse(ifs);

    // Arvon käyttäminen
    std::string title = config["title"].value_or("Nimeämätön");
    std::cout << "Otsikko: " << title << '\n';

    // Muokkaa ja tallenna TOML
    config["title"] = "Uusi Otsikko";
    std::ofstream ofs("config.toml");
    ofs << config;
}
```

Esimerkki `config.toml`:
```toml
title = "Esimerkki"
```

Esimerkkituloste:
```plaintext
Otsikko: Esimerkki
```

## Syväsukellus
TOMLin loi Tom Preston-Werner vuonna 2013 vaihtoehtona YAMLille ja JSONille. Se on suunniteltu yksinkertaiseksi ja eksplisiittiseksi, pääasiassa konfiguraatiotiedostoja varten. Toisin kuin JSON, TOML keskittyy olemaan epäselvyydetön, mikä tarkoittaa, että asiakirjan jäsentäminen on determinististä.

Vaihtoehtoja TOMLille ovat YAML, joka on sallivampi siinä, mitä se sallii, joskus kuitenkin ennustettavuuden kustannuksella. Toinen vaihtoehto, JSON, on rakenteeltaan melko tiukka, mutta ei yhtä ihmisystävällinen konfiguraatioissa kommenttien puutteen ja aaltosulkujen intensiivisen syntaksin vuoksi.

Toteutuksessa `toml++` on header-only C++17 kirjasto, joka noudattaa uusinta TOML-spesifikaatiota. Se tarjoaa DOM-tyyppisen käyttöliittymän TOML-datan navigointiin ja manipulointiin, mikä tekee siitä suoraviivaista integroida projekteihin. Kirjasto huolehtii jäsentämisestä, validoinnista ja tulostuksen generoinnista, mahdollistaen sinun hakea ja asettaa TOML-dataa käyttäen C++ tyyppejä.

## Katso Myös
- TOML GitHub varasto: https://github.com/toml-lang/toml
- `toml++`, C++ kirjasto TOMLille: https://github.com/marzer/tomlplusplus
- Virallinen TOML dokumentaatio, jossa yksityiskohtaiset selitykset formaatista: https://toml.io/en/
