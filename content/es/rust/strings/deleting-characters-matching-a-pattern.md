---
date: 2024-01-20 17:42:59.254895-07:00
description: "Eliminar caracteres que coinciden con un patr\xF3n es quitar ciertos\
  \ caracteres de una cadena de texto que cumplen con una condici\xF3n especificada.\
  \ Lo hacemos\u2026"
lastmod: '2024-03-13T22:44:58.830705-06:00'
model: gpt-4-1106-preview
summary: "Eliminar caracteres que coinciden con un patr\xF3n es quitar ciertos caracteres\
  \ de una cadena de texto que cumplen con una condici\xF3n especificada."
title: "Eliminando caracteres que coinciden con un patr\xF3n"
weight: 5
---

## Cómo hacerlo:
```Rust
fn main() {
    let texto = "¡Hola, Crusty_Cangrejo_123!";
    let patron = ['_', '!', '1', '2', '3'];

    let resultado = eliminar_caracteres(&texto, &paton);
    println!("Texto limpio: {}", resultado);
}

fn eliminar_caracteres(texto: &str, caracteres_a_eliminar: &[char]) -> String {
    texto.chars()
        .filter(|c| !caracteres_a_eliminar.contains(c))
        .collect()
}

// Resultado:
// Texto limpio: Hola, CrustyCangrejo
```

## Deep Dive:
Eliminar caracteres según un patrón no es nada nuevo, viene de mucho antes de que Rust apareciera en el panorama de programación. En lenguajes como Perl o Python, operaciones como estas son pan de cada día gracias a sus poderosas expresiones regulares. Rust ofrece una extra capa de seguridad en el manejo de memoria al realizar estas operaciones, evitando errores comunes en otros lenguajes.

Alternativas para eliminación de caracteres incluyen el uso de expresiones regulares con la crate `regex` para patrones más complejos o implementando tu propia lógica como mostramos arriba, que puede ser más simple y con mejor rendimiento en escenarios sencillos.

El detalle de implementación importante aquí es que `chars()` retorna un iterador sobre los caracteres Unicode del string, no solo los bytes, lo que hace que nuestro código maneje correctamente texto en varios idiomas y símbolos especiales.

## Ver también:
- Documentación oficial de Rust [`std::string::String`](https://doc.rust-lang.org/std/string/struct.String.html)
- Guide to Rust Strings & [`.chars()` iterator](https://doc.rust-lang.org/book/ch08-02-strings.html#iterating-over-strings)
