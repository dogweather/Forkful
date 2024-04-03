---
date: 2024-01-26 01:11:40.110029-07:00
description: "Organizar el c\xF3digo en funciones consiste en descomponer tu programa\
  \ en bloques reutilizables y modulares identificados por un nombre. Hacemos esto\
  \ para\u2026"
lastmod: '2024-03-13T22:44:58.852092-06:00'
model: gpt-4-1106-preview
summary: "Organizar el c\xF3digo en funciones consiste en descomponer tu programa\
  \ en bloques reutilizables y modulares identificados por un nombre."
title: "Organizando c\xF3digo en funciones"
weight: 18
---

## Cómo hacerlo:
Digamos que tienes un código que calcula el área de un círculo varias veces. En lugar de repetir la fórmula, la encapsulas en una función.

```Rust
fn calcular_area_circulo(radio: f64) -> f64 {
    std::f64::consts::PI * radio.powi(2)
}

fn main() {
    let radio = 5.0;
    let area = calcular_area_circulo(radio);
    println!("El área del círculo es: {}", area);
}
```

Salida:

```
El área del círculo es: 78.53981633974483
```

## Inmersión Profunda
Históricamente, las funciones provienen de la matemática, donde mapean entradas a salidas. En la programación, han existido desde los días del lenguaje ensamblador, aunque las llamábamos 'subrutinas'. Las funciones de Rust pueden devolver valores e incluso otras funciones gracias a las funciones de primera clase y las clausuras.

¿Alternativas? Código en línea o macros, pero son un lío para lógica compleja. Los objetos con métodos son otra forma de organizar la funcionalidad, un sabor diferente al de las funciones independientes.

La implementación en Rust es bastante sencilla. Las funciones declaran los tipos de sus parámetros y el tipo de retorno. Por convención, se nombran usando 'snake case'. Tienes tus funciones públicas (`pub fn`) para uso fuera del módulo y las privadas para uso interno. Y Rust tiene esta característica interesante donde no necesitas una palabra clave `return` para la última expresión en una función.

## Vea También
Consulta estos enlaces para más información:
- El Libro de Programación en Rust: [Funciones](https://doc.rust-lang.org/book/ch03-03-how-functions-work.html)
- Rust por Ejemplo sobre [Funciones](https://doc.rust-lang.org/rust-by-example/fn.html)
