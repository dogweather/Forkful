---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:06:19.760423-07:00
description: "Capitalizar una cadena en Rust implica modificar la cadena para que\
  \ su primer car\xE1cter est\xE9 en may\xFAscula si es una letra, mientras que el\
  \ resto de la\u2026"
lastmod: '2024-03-13T22:44:58.829655-06:00'
model: gpt-4-0125-preview
summary: "Capitalizar una cadena en Rust implica modificar la cadena para que su primer\
  \ car\xE1cter est\xE9 en may\xFAscula si es una letra, mientras que el resto de\
  \ la cadena permanece sin cambios."
title: Capitalizando una cadena de texto
weight: 2
---

## Cómo hacerlo:
Para capitalizar una cadena en Rust, tienes dos rutas principales: usar las funcionalidades de la biblioteca estándar o emplear crates de terceros para necesidades más complejas o específicas. Aquí te mostramos cómo hacer ambas.

### Usando la Biblioteca Estándar de Rust
La biblioteca estándar de Rust no proporciona un método directo para capitalizar cadenas, pero puedes lograrlo manipulando los caracteres de la cadena.

```rust
fn capitalize_first(s: &str) -> String {
    let mut c = s.chars();
    match c.next() {
        None => String::new(),
        Some(f) => f.to_uppercase().collect::<String>() + c.as_str(),
    }
}

fn main() {
    let mi_cadena = "hola";
    println!("{}", capitalize_first(mi_cadena)); // Salida: Hola
}
```

### Usando el Crate `heck`
Para un enfoque más directo, especialmente cuando se trabaja dentro de un contexto de procesamiento de texto más amplio, podrías preferir usar bibliotecas de terceros como `heck`. El crate `heck` ofrece varias funcionalidades de conversión de casos, incluyendo una manera simple de capitalizar cadenas.

Primero, agrega `heck` a tu `Cargo.toml`:

```toml
[dependencies]
heck = "0.4.0"
```

Luego, úsalo para capitalizar tu cadena:

```rust
extern crate heck; // No es necesario en la edición de Rust 2018 o posterior
use heck::TitleCase;

fn main() {
    let mi_cadena = "hola mundo";
    let capitalizada = mi_cadena.to_title_case();
    println!("{}", capitalizada); // Salida: Hola Mundo
}
```

Nota: El método `to_title_case` proporcionado por `heck` capitaliza cada palabra en la cadena, lo que podría ser más de lo que estás buscando si solo quieres que el primer carácter de la cadena esté en mayúsculas. Ajusta tu uso según tus necesidades específicas.
