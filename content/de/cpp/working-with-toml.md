---
title:                "Arbeiten mit TOML"
date:                  2024-01-26T04:19:38.913958-07:00
model:                 gpt-4-0125-preview
simple_title:         "Arbeiten mit TOML"
programming_language: "C++"
category:             "C++"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/cpp/working-with-toml.md"
---

{{< edit_this_page >}}

## Was & Warum?
TOML (Tom's Obvious, Minimal Language) ist ein Daten-Serialisierungsformat, das aufgrund seiner klaren Semantik leicht zu lesen ist. Programmierer verwenden TOML für Konfigurationsdateien, da es eine Balance zwischen menschlicher Lesbarkeit und maschineller Parsbarkeit findet.

## Wie geht das:
Um mit TOML in C++ zu arbeiten, benötigt man eine Bibliothek wie `toml++`. Hier ist ein Schnellstart:

```C++
#include <toml++/toml.h>
#include <iostream>
#include <fstream>

int main() {
    // TOML aus einer Datei parsen
    std::ifstream ifs("config.toml");
    auto config = toml::parse(ifs);

    // Auf einen Wert zugreifen
    std::string title = config["title"].value_or("Ohne Titel");
    std::cout << "Titel: " << title << '\n';

    // TOML ändern und speichern
    config["title"] = "Neuer Titel";
    std::ofstream ofs("config.toml");
    ofs << config;
}
```

Beispiel `config.toml`:
```toml
title = "Beispiel"
```

Beispielausgabe:
```plaintext
Titel: Beispiel
```

## Vertiefung
TOML wurde 2013 von Tom Preston-Werner als Alternative zu YAML und JSON erstellt. Es ist darauf ausgelegt, einfach und explizit zu sein, hauptsächlich für Konfigurationsdateien. Im Gegensatz zu JSON konzentriert sich TOML darauf, eindeutig zu sein, was bedeutet, dass es deterministisch ist, wie das Dokument geparst wird.

Alternativen zu TOML umfassen YAML, das permissiver in dem ist, was erlaubt ist, allerdings manchmal auf Kosten der Vorhersagbarkeit. JSON, eine weitere Alternative, ist in seiner Struktur ziemlich streng, aber nicht so benutzerfreundlich für Konfigurationen aufgrund der fehlenden Kommentare und seiner klammerlastigen Syntax.

In der Implementierung ist `toml++` eine Header-Only C++17 Bibliothek, die mit der neuesten TOML-Spezifikation kompatibel ist. Sie bietet eine DOM-ähnliche Schnittstelle, um TOML-Daten zu navigieren und zu manipulieren, was die Integration in Projekte unkompliziert macht. Die Bibliothek kümmert sich um das Parsen, die Validierung und die Erzeugung von Ausgaben und ermöglicht es Ihnen, TOML-Daten unter Verwendung von C++-Typen zu erhalten und zu setzen.

## Siehe auch
- Das TOML GitHub-Repository: https://github.com/toml-lang/toml
- `toml++`, eine C++ Bibliothek für TOML: https://github.com/marzer/tomlplusplus
- Die offizielle TOML-Dokumentation mit detaillierten Erklärungen des Formats: https://toml.io/en/
