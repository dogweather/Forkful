---
date: 2024-01-20 17:58:50.479445-07:00
description: "Suchen und Ersetzen von Text erm\xF6glicht es, spezifische Zeichenkombinationen\
  \ in einem Datenstrom zu finden und durch neue Inhalte zu ersetzen. Es ist ein\u2026"
lastmod: '2024-03-13T22:44:53.657926-06:00'
model: gpt-4-1106-preview
summary: "Suchen und Ersetzen von Text erm\xF6glicht es, spezifische Zeichenkombinationen\
  \ in einem Datenstrom zu finden und durch neue Inhalte zu ersetzen."
title: Suchen und Ersetzen von Text
weight: 10
---

## How to:
Die Standardbibliothek von Rust bietet mächtige Methoden zum Textersatz. Hier ein einfaches Beispiel:

```Rust
fn main() {
    let text = "Frohe Weihnachten!";
    let updated_text = text.replace("Weihnachten", "Ostern");
    println!("{}", updated_text);
}
```

Ausgabe:

```
Frohe Ostern!
```

Für reguläre Ausdrücke benutzt man das `regex` Crates:

```Rust
use regex::Regex;

fn main() {
    let regel = Regex::new(r"Weihnachten").unwrap();
    let text = "Frohe Weihnachten!";
    let nachher = regel.replace_all(text, "Ostern");
    println!("{}", nachher);
}

```

Ausgabe:

```
Frohe Ostern!
```

## Deep Dive
Textsuche und -ersatz gibt's schon ewig. Sed, ein Stream-Editor für Unix-Systeme, nutzt seit den 1970ern reguläre Ausdrücke für solche Operationen. In Rust haben wir ähnliche Funktionen direkt in der Standardbibliothek oder durch Crates wie `regex` für komplexere Suchmuster.

Man unterscheidet zwischen simplen Textersetzungsmethoden wie `replace()` und "Regular Expressions" (Regex), die flexible Suchmuster erkennen. Regex ist mächtig, aber langsamer und schwieriger zu lesen.

Beim Arbeiten mit Strings in Rust muss man auch die Zeichenkodierung beachten. Rust verwendet UTF-8, was Internationale Texte einfach macht, aber beim Ersetzen muss man darauf aufpassen, keine ungültigen Zeichenketten zu erzeugen.

## See Also
- Rust Buch - Strings: https://doc.rust-lang.org/book/ch08-02-strings.html
- `regex` Crate Dokumentation: https://docs.rs/regex/
- Online Regex Tester: https://regexr.com/
