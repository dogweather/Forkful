---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:18:09.031800-07:00
description: "Las expresiones regulares, o regex, permiten a los desarrolladores buscar,\
  \ coincidir y manipular cadenas con t\xE9cnicas avanzadas de coincidencia de\u2026"
lastmod: '2024-03-13T22:44:58.836597-06:00'
model: gpt-4-0125-preview
summary: "Las expresiones regulares, o regex, permiten a los desarrolladores buscar,\
  \ coincidir y manipular cadenas con t\xE9cnicas avanzadas de coincidencia de patrones."
title: Usando expresiones regulares
weight: 11
---

## Cómo hacerlo:
La biblioteca `regex` de Rust es la opción predilecta para trabajar con expresiones regulares. Para usarla, primero necesitarás añadirla a tu `Cargo.toml`:

```toml
[dependencies]
regex = "1"
```

Luego, puedes comenzar a implementar funcionalidades de regex en tu código Rust. Así es como se realizan algunas operaciones comunes:

### Coincidir un Patrón en una Cadena
```rust
use regex::Regex;

fn main() {
    let re = Regex::new(r"^\d{4}-\d{2}-\d{2}$").unwrap();
    let fecha = "2023-04-15";

    println!("¿El texto coincide con el patrón de fecha? {}", re.is_match(fecha));
    // Salida: ¿El texto coincide con el patrón de fecha? true
}
```

### Encontrar y Acceder a Coincidencias
```rust
use regex::Regex;

fn main() {
    let texto = "Rust 2023, C++ 2022, Python 2021";
    let re = Regex::new(r"\b(\w+)\s(\d{4})").unwrap();

    for cap in re.captures_iter(texto) {
        println!("Lenguaje: {}, Año: {}", &cap[1], &cap[2]);
    }
    // Salida:
    // Lenguaje: Rust, Año: 2023
    // Lenguaje: C++, Año: 2022
    // Lenguaje: Python, Año: 2021
}
```

### Reemplazar Texto
```rust
use regex::Regex;

fn main() {
    let re = Regex::new(r"\b(\w+)\s(\d{4})").unwrap();
    let texto = "Rust 2023, C++ 2022, Python 2021";
    let reemplazado = re.replace_all(texto, "$1 fue actualizado en $2");

    println!("Texto actualizado: {}", reemplazado);
    // Salida: Texto actualizado: Rust fue actualizado en 2023, C++ fue actualizado en 2022, Python fue actualizado en 2021
}
```

### Dividir Texto Usando un Regex
```rust
use regex::Regex;

fn main() {
    let re = Regex::new(r"\W+").unwrap(); // dividir en cualquier carácter que no sea de palabra
    let texto = "Rust-C++-Python-Go";

    let campos: Vec<&str> = re.split(texto).collect();

    for campo in campos {
        println!("Lenguaje: {}", campo);
    }
    // Salida:
    // Lenguaje: Rust
    // Lenguaje: C++
    // Lenguaje: Python
    // Lenguaje: Go
}
```

Estos ejemplos proporcionan una guía básica para comenzar con las expresiones regulares en Rust. A medida que tus necesidades se vuelvan más sofisticadas, el 'crate' `regex` ofrece una gran cantidad de funcionalidades para tareas complejas de coincidencia de patrones y manipulación de texto.
