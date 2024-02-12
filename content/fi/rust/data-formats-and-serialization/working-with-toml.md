---
title:                "Työskentely TOML:n kanssa"
aliases:
- fi/rust/working-with-toml.md
date:                  2024-01-26T04:26:19.793875-07:00
model:                 gpt-4-0125-preview
simple_title:         "Työskentely TOML:n kanssa"

tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/rust/working-with-toml.md"
---

{{< edit_this_page >}}

## Mikä & Miksi?
TOML on ihmisen luettavissa oleva datan serialisointikieli, jota käytetään usein konfiguraatioissa. Ohjelmoijat käyttävät TOMLia sen yksinkertaisuuden ja selkeyden vuoksi, mikä kääntyy helposti hajautustauluksi Rustissa.

## Kuinka toimia:
```Rust
// 1. Sisällytä 'toml' laatikko Cargo.toml-tiedostoosi
// [riippuvuudet]
// toml = "0.5"

// 2. Deserialisoi TOML rakenneksi Rustissa
use toml::Value;

fn main() {
    let toml_sisalto = r#"
        [palvelin]
        isäntä = "localhost"
        portti = 8080
    "#;

    let arvo = toml_sisalto.parse::<Value>().unwrap();
    let isäntä = arvo.get("palvelin").unwrap().get("isäntä").unwrap();
    let portti = arvo.get("palvelin").unwrap().get("portti").unwrap();
    
    println!("Palvelin toimii osoitteessa {}:{}", isäntä, portti);
    // Tulostus: Palvelin toimii osoitteessa "localhost":8080
}
```

## Syväsukellus
TOML, joka tarkoittaa Tom's Obvious, Minimal Language, luotiin Tom Preston-Wernerin toimesta vuonna 2013. Sen tavoitteena on olla luettavampi kuin JSON tai YAML konfiguraatiotiedostoissa. TOMLin suunnittelussa keskitytään yksiselitteiseen syntaksiin, minimalismiin ja helppoon karttumiseen datatyyppeihin.

Vaihtoehtoja TOMLille ovat JSON, YAML ja XML, mutta TOML voittaa skenaarioissa, joissa ihmisen luettavuus ja tiedoston muokkaaminen ei-ohjelmoijien toimesta on kriittistä. Kun työskennellään TOMLin kanssa Rustissa, serde tarjoaa vankan perustan serialisointiin ja deserialisointiin, käyttäen piirteitä TOMLin karttamiseen vaivattomasti Rustin rakenteisiin.

Haasteena TOMLin kanssa työskennellessä on sen tiukkuus tyypeissä ja rakenteessa. Ohjelmoijan on määriteltävä hyvin rakennettu Rustin tyyppijärjestelmä, joka heijastaa TOML-datan skeemaa, jotta TOMLia voidaan tehokkaasti hyödyntää Rustissa.

## Katso Myös
- [TOML Dokumentaatio](https://toml.io/en/)
- [serde_toml Laatikko](https://docs.rs/serde_toml/)
- [Rust Ohjelmointikielen Kirja](https://doc.rust-lang.org/stable/book/)
- [TOML GitHub Repo](https://github.com/toml-lang/toml)
