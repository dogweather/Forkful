---
title:                "Interpolazione di una stringa"
aliases:
- it/rust/interpolating-a-string.md
date:                  2024-01-20T17:51:37.875780-07:00
model:                 gpt-4-1106-preview
simple_title:         "Interpolazione di una stringa"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/it/rust/interpolating-a-string.md"
---

{{< edit_this_page >}}

## Cosa & Perché?
L'interpolazione di stringhe permette di iniettare dei valori direttamente all'interno di una stringa. I programmatori la usano per concatenare variabili, espressioni ed eseguire formattazioni in modo più leggibile e conciso.

## Come fare:
```Rust
fn main() {
    let animale = "gatto";
    let suono = "miao";
    // Interpolazione con la macro `format!`
    let frase = format!("Il {} fa '{}'", animale, suono);
    println!("{}", frase); // Stampare la frase interpolata
}

```
Output:
```
Il gatto fa 'miao'
```

## Approfondimento
L'interpolazione di stringhe non è presente in Rust come feature del linguaggio nativa, come in altri linguaggi (ad esempio, Python o Ruby). Si usa invece la macro `format!` o si stampa direttamente con `println!` o `write!`. Questa scelta mantiene la tipizzazione statica e la sicurezza nelle operazioni sulle stringhe. Se vieni da linguaggi con interpolazione nativa, potrebbe sembrarti più scomodo, ma questa è una decisione progettuale per prevenire errori a runtime.

Come alternativa alla `format!`, puoi anche concatenare usando `+` o `push_str()`, ma queste opzioni sono più verbosi e meno performanti quando si lavora con più valori.

## Vedi Anche
- Rust Book sulla formattazione e stampa di testo: [The Rust Programming Language - Formatted print](https://doc.rust-lang.org/stable/book/ch02-00-guessing-game-tutorial.html#storing-values-with-variables)
- Documentazione ufficiale della macro `format!`: [Rust std::fmt](https://doc.rust-lang.org/std/fmt/)
- Discussione sull'interpolazione di stringhe in Rust: [Rust Internals Forum](https://internals.rust-lang.org/)
