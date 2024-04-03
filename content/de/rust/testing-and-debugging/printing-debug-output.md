---
date: 2024-01-20 17:53:09.841237-07:00
description: "Debug-Ausgabe zu drucken bedeutet, Zwischenergebnisse und Variablenwerte\
  \ w\xE4hrend der Laufzeit in die Konsole zu schreiben. Programmierer nutzen das,\
  \ um\u2026"
lastmod: '2024-03-13T22:44:53.675363-06:00'
model: gpt-4-1106-preview
summary: "Debug-Ausgabe zu drucken bedeutet, Zwischenergebnisse und Variablenwerte\
  \ w\xE4hrend der Laufzeit in die Konsole zu schreiben."
title: Debug-Ausgaben drucken
weight: 33
---

## So geht’s:
```Rust
fn main() {
    let lebenswichtige_variable = 42;
    println!("Die Antwort ist: {}", lebenswichtige_variable);
    dbg!(&lebenswichtige_variable);
}
```
Ausgabe:
```
Die Antwort ist: 42
[src/main.rs:4] lebenswichtige_variable = 42
```
`println!` zeigt einfache Nachrichten. `dbg!` gibt den Wert, den Dateinamen und die Zeilennummer aus.

## Vertiefung:
Debugging-Ausdrucke gibt es, seit Programmierer Bugs jagen. `println!` ist einfach, aber roh. `dbg!` kam in Rust 1.32.0 und ist handlicher: Automatisches Spacing, Datei und Zeilenangaben. Weitere Tools für komplexere Fälle sind `log` und `env_logger`.

## Siehe auch:
- Rust by Example über `println!`: https://doc.rust-lang.org/rust-by-example/hello/print.html
- Rust Docs zu `dbg!`: https://doc.rust-lang.org/std/macro.dbg.html
- Für umfangreicheres Logging: https://crates.io/crates/env_logger
