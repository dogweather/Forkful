---
title:                "Controleren of een directory bestaat"
aliases:
- nl/rust/checking-if-a-directory-exists.md
date:                  2024-01-28T21:56:01.751410-07:00
model:                 gpt-4-0125-preview
simple_title:         "Controleren of een directory bestaat"

tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/nl/rust/checking-if-a-directory-exists.md"
changelog:
  - 2024-01-28, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Wat & Waarom?

Controleren of een map bestaat in Rust is het verifiëren of een map aanwezig is op het bestandssysteem. Programmeurs doen dit om fouten te voorkomen bij het openen of wijzigen van bestanden, wat zorgt voor soepelere bestandsbewerkingen.

## Hoe:

De standaardbibliotheek van Rust maakt deze taak eenvoudig met `std::path::Path` en `std::fs`:

```rust
use std::path::Path;

fn main() {
    let path = Path::new("/some/directory");

    if path.exists() && path.is_dir() {
        println!("Map bestaat!");
    } else {
        println!("Map bestaat niet.");
    }
}
```

Voorbeelduitvoer, als de map bestaat:
```
Map bestaat!
```

Voorbeelduitvoer, als de map niet bestaat:
```
Map bestaat niet.
```

## Diepgaand:

Historisch gezien hadden bestandsbewerkingen meer uitgebreide foutafhandeling nodig, wat de code log maakte. Rust vereenvoudigt dit met beknopte methoden die "gewoon werken". Alternatieven, zoals shell-commando's of andere bibliotheken gebruiken, bestaan maar zijn niet zo gestroomlijnd. De `exists()` methode controleert alleen op het bestaan, niet of het een map of een bestand is; combineer het met `is_dir()` voor mappen. Deze methoden gebruiken intern de systeemaanroepen van het OS om efficiënt de status van het bestandssysteem op te vragen.

## Zie Ook:

- Documentatie van Rust's Path: https://doc.rust-lang.org/std/path/struct.Path.html
- Documentatie van Rust's fs module: https://doc.rust-lang.org/std/fs/
- Foutafhandeling in Rust: https://doc.rust-lang.org/book/ch09-00-error-handling.html
