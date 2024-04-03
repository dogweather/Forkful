---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:26:38.369523-07:00
description: "En la programaci\xF3n con Rust, trabajar con YAML (YAML Ain't Markup\
  \ Language) consiste en analizar y generar datos en formato YAML, un est\xE1ndar\
  \ de\u2026"
lastmod: '2024-03-13T22:44:58.867071-06:00'
model: gpt-4-0125-preview
summary: "En la programaci\xF3n con Rust, trabajar con YAML (YAML Ain't Markup Language)\
  \ consiste en analizar y generar datos en formato YAML, un est\xE1ndar de serializaci\xF3\
  n de datos amigable para el ser humano."
title: Trabajando con YAML
weight: 41
---

## Cómo hacerlo:
Rust no soporta YAML en su biblioteca estándar, por lo que comúnmente utilizamos crates de terceros como `serde` (para serializar y deserializar datos) en combinación con `serde_yaml`.

Primero, añade las dependencias a tu `Cargo.toml`:

```toml
[dependencies]
serde = { version = "1.0", features = ["derive"] }
serde_yaml = "0.8"
```

Ahora, veamos cómo deserializar una cadena YAML en una estructura Rust y serializar una estructura Rust de vuelta en una cadena YAML.

### Deserializando YAML en estructuras de Rust
Define una estructura Rust que refleje los datos que esperas en YAML. Usa atributos de Serde para la personalización si es necesario.

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

La salida de muestra al ejecutar el código Rust anterior sería:

```plaintext
Config { name: "Shield", durability: 300, owner: Owner { name: "Steve", age: 25 } }
```

### Serializando estructuras de Rust en YAML
Este ejemplo toma la estructura `Config` de la sección anterior y la serializa de nuevo en formato YAML.

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

La salida esperada será una cadena en formato YAML:

```yaml
---
name: Axe
durability: 120
owner:
  name: Alex
  age: 30
```

Estos fragmentos demuestran cómo integrar eficientemente el análisis y la generación de YAML en tus aplicaciones Rust, utilizando los populares crates `serde` y `serde_yaml`, adaptándose a estructuras de datos complejas y proporcionando configuraciones simples y legibles para el ser humano.
