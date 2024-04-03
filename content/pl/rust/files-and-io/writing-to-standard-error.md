---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:34:53.367298-07:00
description: "Pisanie do standardowego b\u0142\u0119du (stderr) w Rust oznacza kierowanie\
  \ komunikat\xF3w o b\u0142\u0119dach i diagnostyki na konsol\u0119 oddzielnie od\
  \ standardowego wyj\u015Bcia\u2026"
lastmod: '2024-03-13T22:44:35.202592-06:00'
model: gpt-4-0125-preview
summary: "Pisanie do standardowego b\u0142\u0119du (stderr) w Rust oznacza kierowanie\
  \ komunikat\xF3w o b\u0142\u0119dach i diagnostyki na konsol\u0119 oddzielnie od\
  \ standardowego wyj\u015Bcia (stdout)."
title: "Pisanie do standardowego b\u0142\u0119du"
weight: 25
---

## Jak to zrobić:
Rust oferuje prosty sposób na pisanie do stderr za pomocą makra `eprintln!`, podobnie jak `println!` jest używane dla stdout. Oto podstawowy przykład:

```rust
fn main() {
    eprintln!("To jest komunikat o błędzie!");
}
```

Przykładowe wyjście (do standardowego błędu):
```
To jest komunikat o błędzie!
```

Aby mieć większą kontrolę nad komunikatami o błędach, na przykład kiedy chcesz formatować tekst lub obsługiwać wyniki operacji I/O, użyj funkcji `stderr` z modułu `std::io`. Ta metoda dostarcza uchwyt do globalnego strumienia stderr, do którego możesz następnie pisać, używając metod takich jak `write_all` lub `writeln` z cechy `Write`:

```rust
use std::io::{self, Write};

fn main() {
    let stderr = io::stderr();
    let mut handle = stderr.lock();
    
    writeln!(handle, "Sformatowany komunikat o błędzie: {}", 404).expect("Nie udało się zapisać do stderr");
}
```

Przykładowe wyjście (do standardowego błędu):
```
Sformatowany komunikat o błędzie: 404
```

Jeśli pracujesz w środowiskach lub aplikacjach, gdzie polegasz na bibliotekach do logowania lub obsługi błędów, popularne są takie biblioteki jak `log` i `env_logger`. Chociaż są one używane bardziej do celów logowania, są konfigurowalne i mogą kierować poziomy logowania błędów do stderr. Poniżej znajduje się prosty przykład użycia `log` i `env_logger`:

Najpierw dodaj zależności do pliku `Cargo.toml`:
```toml
[dependencies]
log = "0.4"
env_logger = "0.9"
```

Następnie, skonfiguruj i użyj logowania w swojej aplikacji:
```rust
fn main() {
    env_logger::init();
    log::error!("Ten komunikat o błędzie został zalogowany do stderr");
}
```

Uruchomienie tego programu (po skonfigurowaniu `env_logger` z odpowiednią zmienną środowiskową, na przykład `RUST_LOG=error`) spowoduje wyjście komunikatu o błędzie do stderr, wykorzystując infrastrukturę logowania.

```plaintext
ERROR: Ten komunikat o błędzie został zalogowany do stderr
```
