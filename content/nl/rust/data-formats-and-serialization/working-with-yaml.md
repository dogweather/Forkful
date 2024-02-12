---
title:                "Werken met YAML"
date:                  2024-01-28T22:12:27.393493-07:00
model:                 gpt-4-0125-preview
simple_title:         "Werken met YAML"

tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/nl/rust/working-with-yaml.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?

Werken met YAML betekent omgaan met gegevens in het "YAML Ain't Markup Language" formaat - een mensvriendelijke standaard voor gegevensserialisatie. Programmeurs gebruiken het voor configuratiebestanden, gegevensopslag of overal waar ze gemakkelijk leesbare en schrijfbare gestructureerde gegevens nodig hebben.

## Hoe te:

Om YAML in Rust te parsen en te genereren, gebruiken we de `serde_yaml` crate, die leunt op `serde` voor serialisatie/deserialisatie.

Voeg eerst afhankelijkheden toe aan je `Cargo.toml`:

```toml
[dependencies]
serde = { version = "1.0", features = ["derive"] }
serde_yaml = "0.8"
```

Laten we nu een Rust struct naar YAML serialiseren:

```rust
use serde::{Serialize, Deserialize};
use serde_yaml;

#[derive(Debug, Serialize, Deserialize)]
struct Config {
    debug: bool,
    environment: String,
    port: u16,
}

fn main() -> serde_yaml::Result<()> {
    let config = Config {
        debug: true,
        environment: "development".to_string(),
        port: 8080,
    };

    // Serialiseren naar YAML
    let yaml_string = serde_yaml::to_string(&config)?;
    println!("{}", yaml_string);
    // Uitvoer:
    // ---
    // debug: true
    // environment: "development"
    // port: 8080

    Ok(())
}
```

Om YAML te deserialiseren naar een Rust struct:

```rust
fn main() -> serde_yaml::Result<()> {
    let yaml_string = r#"
    debug: true
    environment: "development"
    port: 8080
    "#;

    let config: Config = serde_yaml::from_str(&yaml_string)?;
    println!("{:?}", config);
    // Uitvoer:
    // Config { debug: true, environment: "development", port: 8080 }

    Ok(())
}
```

## Diepere Duik

YAML is in 2001 gestart als een gebruiksvriendelijk alternatief voor XML. In tegenstelling tot JSON ondersteunt YAML commentaren en is het minder lawaaierig, waardoor het een favoriet is voor configuratiebestanden. Rust's `serde_yaml` benut `serde` voor gegevensconversie, waardoor hoge compatibiliteit en flexibiliteit worden gewaarborgd. Hoewel `serde_json` vaker wordt gebruikt vanwege de alomtegenwoordigheid van JSON in API's, blinkt `serde_yaml` uit voor lokale configuratie- en gegevensbestanden. Het is het vermelden waard dat overmatig complexe YAML-functies zelden worden gebruikt en soms ontmoedigd vanwege potentiële parseerproblemen.

## Zie Ook

Voor verdere lezing en meer complexe gebruiksscenario's:

- Serde's officiële documentatie: https://serde.rs/
- Serde YAML crate documentatie: https://docs.rs/serde_yaml/latest/serde_yaml/
- YAML officiële specificatie: https://yaml.org/spec/1.2/spec.html
- Het boek "The Rust Programming Language": https://doc.rust-lang.org/book/
