---
aliases:
- /sv/rust/working-with-yaml/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:26:41.207630-07:00
description: "I Rust-programmering inneb\xE4r arbete med YAML (YAML Ain't Markup Language)\
  \ att tolka och generera data i YAML-format, en m\xE4nniskov\xE4nlig standard f\xF6\
  r data-\u2026"
lastmod: 2024-02-18 23:08:51.603604
model: gpt-4-0125-preview
summary: "I Rust-programmering inneb\xE4r arbete med YAML (YAML Ain't Markup Language)\
  \ att tolka och generera data i YAML-format, en m\xE4nniskov\xE4nlig standard f\xF6\
  r data-\u2026"
title: Att Arbeta med YAML
---

{{< edit_this_page >}}

## Vad & Varför?

I Rust-programmering innebär arbete med YAML (YAML Ain't Markup Language) att tolka och generera data i YAML-format, en människovänlig standard för data-serialisering. Programmerare integrerar YAML-hantering i Rust för att konfigurera applikationer, hantera inställningar eller bearbeta komplexa datastrukturer i ett klart och läsbart format, och utnyttjar dess enkelhet över JSON eller XML för konfigurationsfiler och datautbyte.

## Hur man gör:

Rust stöder inte YAML i sitt standardbibliotek, så vi använder vanligtvis tredjeparts lådor som `serde` (för serialisering och deserialisering av data) i kombination med `serde_yaml`.

Lägg först till beroenden i din `Cargo.toml`:

```toml
[dependencies]
serde = { version = "1.0", features = ["derive"] }
serde_yaml = "0.8"
```

Låt oss nu se hur man deserialiserar en YAML-sträng till en Rust-struktur och serialiserar en Rust-struktur tillbaka till en YAML-sträng.

### Deserialisera YAML till Rust-strukturer

Definiera en Rust-struktur som speglar de data du förväntar dig i YAML. Använd Serde-attribut för anpassning om det behövs.

```rust
use serde::{Deserialize, Serialize};
use serde_yaml;

#[derive(Debug, PartialEq, Serialize, Deserialize)]
struct Config {
    name: String,
    durability: i32,
    owner: Owner,
}

#[derive(Debug, PartialEq, Serialize, Deserialize)]
struct Owner {
    name: String,
    age: i32,
}

fn main() {
    let yaml_data = "
name: Shield
durability: 300
owner:
  name: Steve
  age: 25
";

    let deserialized_config: Config = serde_yaml::from_str(yaml_data).unwrap();
    println!("{:?}", deserialized_config);
}
```

Exempelutdata när du kör ovanstående Rust-kod blir:

```plaintext
Config { name: "Shield", durability: 300, owner: Owner { name: "Steve", age: 25 } }
```

### Serialisera Rust-strukturer till YAML

Detta exempel tar `Config`-strukturen från föregående avsnitt och serialiserar den tillbaka till YAML-format.

```rust
fn main() {
    let config = Config {
        name: String::from("Axe"),
        durability: 120,
        owner: Owner {
            name: String::from("Alex"),
            age: 30,
        },
    };

    let serialized_yaml = serde_yaml::to_string(&config).unwrap();
    println!("{}", serialized_yaml);
}
```

Förväntad utdata blir en YAML-formaterad sträng:

```yaml
---
name: Axe
durability: 120
owner:
  name: Alex
  age: 30
```

Dessa kodsnuttar demonstrerar hur du effektivt integrerar YAML-tolkning och generering i dina Rust-applikationer, med hjälp av de populära lådorna `serde` och `serde_yaml`, för att rymma komplexa datastrukturer och erbjuda enkla, människoläsbara konfigurationer.
