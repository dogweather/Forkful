---
title:                "Jobbe med TOML"
date:                  2024-01-26T04:26:13.785024-07:00
model:                 gpt-4-0125-preview
simple_title:         "Jobbe med TOML"

tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/no/rust/working-with-toml.md"
---

{{< edit_this_page >}}

## Hva & Hvorfor?
TOML er et menneskelesbart data serialiseringsspråk, ofte brukt for konfigurasjoner. Programmerere bruker TOML på grunn av dets enkelhet og klarhet, som enkelt oversettes til en hash map i Rust.

## Hvordan:
```Rust
// 1. Inkluder 'toml'-pakken i din Cargo.toml
// [dependencies]
// toml = "0.5"

// 2. Deserialiser TOML til en struct i Rust
use toml::Value;

fn main() {
    let toml_content = r#"
        [server]
        host = "localhost"
        port = 8080
    "#;

    let value = toml_content.parse::<Value>().unwrap();
    let host = value.get("server").unwrap().get("host").unwrap();
    let port = value.get("server").unwrap().get("port").unwrap();
    
    println!("Serveren kjører på {}:{}", host, port);
    // Utdata: Serveren kjører på "localhost":8080
}
```

## Dybde Dykking
TOML, som står for Toms Opplysende, Minimalistiske Språk, ble skapt av Tom Preston-Werner i 2013. Det tar sikte på å være mer leselig enn JSON eller YAML for konfigurasjonsfiler. TOMLs design fokuserer på utvetydig syntaks, minimalisme, og enkel kartlegging til datatyper.

Alternativer til TOML inkluderer JSON, YAML, og XML, men TOML vinner i scenarioer der menneskelig lesbarhet og filredigering av ikke-programmerere er avgjørende. Når man jobber med TOML i Rust, gir serde et sterkt grunnlag for serialisering og deserialisering, ved å bruke trekk for å kartlegge TOML på Rusts strukturer uten anstrengelse.

En utfordring ved å jobbe med TOML er dens strenghet på typer og struktur. Programmereren må definere et godt strukturert Rust typsystem som reflekterer schemaet til TOML dataen for å effektivt utnytte TOML i Rust.

## Se Også
- [TOML Dokumentasjon](https://toml.io/en/)
- [serde_toml Pakke](https://docs.rs/serde_toml/)
- [Rust Programmeringsspråk Bok](https://doc.rust-lang.org/stable/book/)
- [TOML GitHub Repo](https://github.com/toml-lang/toml)
