---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:18:52.039532-07:00
description: "Wyra\u017Cenia regularne, czyli regex, pozwalaj\u0105 programistom wyszukiwa\u0107\
  , dopasowywa\u0107 i manipulowa\u0107 ci\u0105gami znak\xF3w, wykorzystuj\u0105\
  c zaawansowane techniki\u2026"
lastmod: '2024-03-13T22:44:35.174120-06:00'
model: gpt-4-0125-preview
summary: "Wyra\u017Cenia regularne, czyli regex, pozwalaj\u0105 programistom wyszukiwa\u0107\
  , dopasowywa\u0107 i manipulowa\u0107 ci\u0105gami znak\xF3w, wykorzystuj\u0105\
  c zaawansowane techniki dopasowywania wzorc\xF3w."
title: "Korzystanie z wyra\u017Ce\u0144 regularnych"
weight: 11
---

## Jak to zrobić:
Biblioteka `regex` w Rust jest podstawowym narzędziem do pracy z wyrażeniami regularnymi. Aby jej użyć, najpierw należy dodać ją do pliku `Cargo.toml`:

```toml
[dependencies]
regex = "1"
```

Następnie, możesz zacząć implementować funkcje regex w swoim kodzie Rust. Oto jak wykonać kilka typowych operacji:

### Dopasowywanie wzorca w ciągu znaków
```rust
use regex::Regex;

fn main() {
    let re = Regex::new(r"^\d{4}-\d{2}-\d{2}$").unwrap();
    let date = "2023-04-15";

    println!("Czy tekst pasuje do wzorca daty? {}", re.is_match(date));
    // Wyjście: Czy tekst pasuje do wzorca daty? true
}
```

### Znajdowanie i dostęp do dopasowań
```rust
use regex::Regex;

fn main() {
    let text = "Rust 2023, C++ 2022, Python 2021";
    let re = Regex::new(r"\b(\w+)\s(\d{4})").unwrap();

    for cap in re.captures_iter(text) {
        println!("Język: {}, Rok: {}", &cap[1], &cap[2]);
    }
    // Wyjście:
    // Język: Rust, Rok: 2023
    // Język: C++, Rok: 2022
    // Język: Python, Rok: 2021
}
```

### Zamiana tekstu
```rust
use regex::Regex;

fn main() {
    let re = Regex::new(r"\b(\w+)\s(\d{4})").unwrap();
    let text = "Rust 2023, C++ 2022, Python 2021";
    let replaced = re.replace_all(text, "$1 został zaktualizowany w $2");

    println!("Zaktualizowany tekst: {}", replaced);
    // Wyjście: Zaktualizowany tekst: Rust został zaktualizowany w 2023, C++ został zaktualizowany w 2022, Python został zaktualizowany w 2021
}
```

### Dzielenie tekstu przy użyciu regex
```rust
use regex::Regex;

fn main() {
    let re = Regex::new(r"\W+").unwrap(); // dzielenie przy każdym znaku nie będącym słowem
    let text = "Rust-C++-Python-Go";

    let fields: Vec<&str> = re.split(text).collect();

    for field in fields {
        println!("Język: {}", field);
    }
    // Wyjście:
    // Język: Rust
    // Język: C++
    // Język: Python
    // Język: Go
}
```

Te przykłady stanowią podstawowy przewodnik po pierwszych krokach z wyrażeniami regularnymi w Rust. W miarę rosnących potrzeb, skrzynka `regex` oferuje bogactwo funkcjonalności dla złożonych zadań związanych z dopasowywaniem wzorców i manipulacją tekstem.
