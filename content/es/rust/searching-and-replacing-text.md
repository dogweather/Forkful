---
title:                "Buscando y reemplazando texto"
date:                  2024-01-20T17:58:49.096126-07:00
model:                 gpt-4-1106-preview
simple_title:         "Buscando y reemplazando texto"
programming_language: "Rust"
category:             "Rust"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/es/rust/searching-and-replacing-text.md"
---

{{< edit_this_page >}}

## Qué y Por Qué?
Buscar y reemplazar texto permite modificar cadenas de caracteres fácilmente, una herramienta esencial para corregir errores, actualizar datos o cambiar código. Los programadores usan esta técnica para ahorrar tiempo y evitar alterar manualmente largos bloques de texto.

## Cómo Hacerlo:
Vamos a ver un ejemplo sencillo en Rust utilizando el método `replace` de las cadenas de texto:

```rust
fn main() {
    let texto = "Hola, mundo. Rust es genial.";
    let nuevo_texto = texto.replace("genial", "increíble");
    println!("{}", nuevo_texto);
}
```

Salida:
```
Hola, mundo. Rust es increíble.
```

Si quieres reemplazar todas las coincidencias que satisfacen un patrón, puedes usar expresiones regulares con la crate `regex`:

```rust
use regex::Regex;

fn main() {
    let texto = "El 2020 y el 2021 fueron años de aprendizaje.";
    let re = Regex::new(r"202[01]").unwrap();
    let nuevo_texto = re.replace_all(texto, "XXXX");
    println!("{}", nuevo_texto);
}

```

Salida:
```
El XXXX y el XXXX fueron años de aprendizaje.
```

Nota que para usar `regex`, debes incluir la crate en tu `Cargo.toml`.

## Análisis Profundo
Buscar y reemplazar texto es un concepto que se remonta a los primeros editores de texto. Rust está diseñado para la seguridad y la abstracción, por lo que el manejo de texto es más riguroso. `replace` y `replace_all` son métodos sencillos pero poderosos. `replace` cambia todas las ocurrencias de una subcadena, mientras que `replace_all` de `regex` permite reemplazos basados en patrones complejos. Aunque `regex` tiene un coste computacional mayor, es flexible y ampliamente utilizado para búsquedas más elaboradas.

## Ver También
- [Rust std::string::String](https://doc.rust-lang.org/std/string/struct.String.html)
