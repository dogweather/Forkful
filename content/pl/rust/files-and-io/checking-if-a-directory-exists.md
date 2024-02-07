---
title:                "Sprawdzanie, czy katalog istnieje"
date:                  2024-02-03T19:08:47.976522-07:00
model:                 gpt-4-0125-preview
simple_title:         "Sprawdzanie, czy katalog istnieje"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/rust/checking-if-a-directory-exists.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Co i dlaczego?
W rozwoju oprogramowania często potrzebne jest sprawdzenie, czy katalog istnieje, aby unikać błędów podczas prób dostępu, odczytu lub zapisu plików. Rust, będący językiem programowania systemowego, zapewnia solidne metody wykonania tego zadania, gwarantując, że Twój program może bezpiecznie i efektywnie obsługiwać pliki i katalogi.

## Jak to zrobić:
Standardowa biblioteka Rusta (`std`) zawiera funkcjonalność umożliwiającą sprawdzenie istnienia katalogu za pomocą modułów `std::path::Path` i `std::fs`. Oto prosty przykład użycia standardowego podejścia w Rust:

```rust
use std::path::Path;

fn main() {
    let path = Path::new("/ścieżka/do/katalogu");
    if path.exists() && path.is_dir() {
        println!("Katalog istnieje.");
    } else {
        println!("Katalog nie istnieje.");
    }
}
```

Przykładowe wyjście, zakładając, że katalog istnieje:
```
Katalog istnieje.
```

W bardziej złożonych scenariuszach lub dla zaawansowanych funkcji (takich jak asynchroniczne operacje na systemie plików) możesz rozważyć użycie biblioteki zewnętrznej, takiej jak `tokio` z jej asynchronicznym modułem `fs`, szczególnie jeśli pracujesz w środowisku asynchronicznym. Oto jak można osiągnąć to samo z `tokio`:

Najpierw dodaj `tokio` do swojego `Cargo.toml`:

```toml
[dependencies]
tokio = { version = "1.0", features = ["full"] }
```

Następnie użyj `tokio::fs`, aby asynchronicznie sprawdzić, czy katalog istnieje:

```rust
use tokio::fs;

#[tokio::main]
async fn main() {
    let path = "/ścieżka/do/katalogu";
    match fs::metadata(path).await {
        Ok(metadata) => {
            if metadata.is_dir() {
                println!("Katalog istnieje.");
            } else {
                println!("Ścieżka istnieje, ale nie jest katalogiem.");
            }
        },
        Err(_) => println!("Katalog nie istnieje."),
    }
}
```

Przykładowe wyjście, zakładając, że katalog nie istnieje:
```
Katalog nie istnieje.
```

Te przykłady podkreślają, jak Rust i jego ekosystem oferują zarówno synchroniczne, jak i asynchroniczne podejścia do sprawdzania istnienia katalogów, odpowiadając na szeroki zakres potrzeb rozwoju oprogramowania.
