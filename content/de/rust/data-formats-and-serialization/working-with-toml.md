---
date: 2024-01-26 04:26:00.823060-07:00
description: "TOML ist eine f\xFCr Menschen lesbare Datenserialisierungssprache, die\
  \ oft f\xFCr Konfigurationen verwendet wird. Programmierer nutzen TOML wegen seiner\u2026"
lastmod: '2024-03-13T22:44:53.696503-06:00'
model: gpt-4-0125-preview
summary: "TOML ist eine f\xFCr Menschen lesbare Datenserialisierungssprache, die oft\
  \ f\xFCr Konfigurationen verwendet wird."
title: Arbeiten mit TOML
weight: 39
---

## Wie man:
```Rust
// 1. Füge das 'toml'-Paket in deine Cargo.toml ein
// [Abhängigkeiten]
// toml = "0.5"

// 2. Deserialisiere TOML in eine Struktur in Rust
use toml::Value;

fn main() {
    let toml_inhalt = r#"
        [server]
        host = "localhost"
        port = 8080
    "#;

    let wert = toml_inhalt.parse::<Value>().unwrap();
    let host = wert.get("server").unwrap().get("host").unwrap();
    let port = wert.get("server").unwrap().get("port").unwrap();
    
    println!("Der Server läuft auf {}:{}", host, port);
    // Ausgabe: Der Server läuft auf "localhost":8080
}
```

## Tiefere Einblicke
TOML, das für Toms Offensichtliche, Minimale Sprache steht, wurde 2013 von Tom Preston-Werner erschaffen. Es zielt darauf ab, lesbarer als JSON oder YAML für Konfigurationsdateien zu sein. Die Gestaltung von TOML konzentriert sich auf unzweideutige Syntax, Minimalismus und eine einfache Zuordnung zu Datentypen.

Zu den Alternativen zu TOML gehören JSON, YAML und XML, aber TOML gewinnt in Szenarien, in denen Menschenlesbarkeit und die Bearbeitung von Dateien durch Nicht-Programmierer entscheidend sind. Beim Arbeiten mit TOML in Rust bietet serde eine solide Grundlage für Serialisierung und Deserialisierung, indem Traits verwendet werden, um TOML mühelos auf Rusts Strukturen abzubilden.

Eine Herausforderung beim Arbeiten mit TOML ist seine Strenge bezüglich Typen und Struktur. Der Programmierer muss ein gut strukturiertes Rust-Typensystem definieren, das das Schema der TOML-Daten widerspiegelt, um TOML in Rust effektiv nutzen zu können.

## Siehe auch
- [TOML-Dokumentation](https://toml.io/en/)
- [serde_toml Crate](https://docs.rs/serde_toml/)
- [Buch zur Rust-Programmiersprache](https://doc.rust-lang.org/stable/book/)
- [TOML GitHub-Repo](https://github.com/toml-lang/toml)
