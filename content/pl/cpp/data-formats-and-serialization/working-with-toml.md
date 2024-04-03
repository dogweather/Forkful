---
date: 2024-01-26 04:19:58.316251-07:00
description: "TOML (Tom's Obvious, Minimal Language) to format serializacji danych\
  \ \u0142atwy do odczytu dzi\u0119ki jasnej semantyce. Programi\u015Bci u\u017Cywaj\u0105\
  \ TOML do plik\xF3w\u2026"
lastmod: '2024-03-13T22:44:35.736221-06:00'
model: gpt-4-0125-preview
summary: "TOML (Tom's Obvious, Minimal Language) to format serializacji danych \u0142\
  atwy do odczytu dzi\u0119ki jasnej semantyce."
title: Praca z TOML
weight: 39
---

## Jak to zrobić:
Aby pracować z TOML w C++, potrzebujesz biblioteki takiej jak `toml++`. Oto szybki start:

```C++
#include <toml++/toml.h>
#include <iostream>
#include <fstream>

int main() {
    // Parsowanie TOML z pliku
    std::ifstream ifs("config.toml");
    auto config = toml::parse(ifs);

    // Dostęp do wartości
    std::string title = config["title"].value_or("Bez tytułu");
    std::cout << "Tytuł: " << title << '\n';

    // Modyfikacja i zapis TOML
    config["title"] = "Nowy Tytuł";
    std::ofstream ofs("config.toml");
    ofs << config;
}
```

Przykładowy `config.toml`:
```toml
title = "Przykład"
```

Przykładowe wyjście:
```plaintext
Tytuł: Przykład
```

## Dogłębna analiza
TOML został stworzony przez Toma Preston-Wernera w 2013 roku jako alternatywa dla YAML i JSON. Został zaprojektowany tak, aby być prostym i jednoznacznym, głównie dla plików konfiguracyjnych. W przeciwieństwie do JSON, TOML koncentruje się na byciu niejednoznacznym, co oznacza, że jest deterministyczny w sposobie parsowania dokumentu.

Alternatywami dla TOML są YAML, który jest bardziej liberalny w tym, co jest dozwolone, chociaż czasami kosztem przewidywalności. Inną alternatywą jest JSON, który jest dość ścisły w strukturze, ale nie tak przyjazny dla ludzi w konfiguracjach z powodu braku komentarzy i obfitości nawiasów.

W implementacji, `toml++` to biblioteka C++17 tylko z nagłówkami, zgodna z najnowszą specyfikacją TOML. Zapewnia interfejs podobny do DOM, umożliwiający nawigację i manipulację danymi TOML, co ułatwia integrację z projektami. Biblioteka zajmuje się parsowaniem, walidacją i generowaniem wyjścia, pozwalając na pobieranie i ustawianie danych TOML za pomocą typów C++.

## Zobacz także
- Repozytorium TOML na GitHubie: https://github.com/toml-lang/toml
- `toml++`, biblioteka C++ dla TOML: https://github.com/marzer/tomlplusplus
- Oficjalna dokumentacja TOML z szczegółowymi wyjaśnieniami formatu: https://toml.io/en/
