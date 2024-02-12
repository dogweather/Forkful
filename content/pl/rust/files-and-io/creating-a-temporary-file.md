---
title:                "Tworzenie pliku tymczasowego"
aliases:
- /pl/rust/creating-a-temporary-file/
date:                  2024-01-20T17:41:27.687220-07:00
model:                 gpt-4-1106-preview
simple_title:         "Tworzenie pliku tymczasowego"

tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/rust/creating-a-temporary-file.md"
---

{{< edit_this_page >}}

## What & Why? (Co i Dlaczego?)
Tworzenie tymczasowych plików to proces, w którym program tworzy plik, który ma być użyty tylko na krótki czas. Programiści robią to, by zarządzać danymi tymczasowymi, które nie są potrzebne po zakończeniu zadania, jak np. cachowanie, przechowywanie dużych obiektów do zadań batchowych, lub jako miejsce pracy dla dużej operacji przetwarzania.

## How to: (Jak to zrobić:)
Rust używa `tempfile` crate do łatwego tworzenia tymczasowych plików. Poniżej znajdziesz przykład:

```Rust
use tempfile::NamedTempFile;
use std::io::{Write, Read};

fn main() -> std::io::Result<()> {
    let mut temp_file = NamedTempFile::new()?;
    
    // Zapisz coś do pliku.
    writeln!(temp_file, "Witaj, tymczasowy świecie!")?;
    
    // Spójrzmy co tam mamy.
    let mut buf = String::new();
    temp_file.as_file_mut().read_to_string(&mut buf)?;
    println!("Temp file contains: {}", buf);
    
    Ok(())
}
```

Wyjście programu:
```
Temp file contains: Witaj, tymczasowy świecie!
```

## Deep Dive (Głębsze zanurzenie)
Tworzenie plików tymczasowych jest starym konceptem, podobnymi mechanizmami korzysta UNIX od lat 70-tych. W Rust, `tempfile` crate oferuje bezpieczne i wygodne metody zarządzania tymczasowymi plikami. Alternatywą jest używanie standardowej biblioteki `std::fs` i samodzielne zarządzanie nazwami i usunięciem plików, jednak można napotkać problemy z bezpieczeństwem dostępu i kolizją nazw.

Głównym atutem `tempfile` jest to, że robi za nas sprzątanie — tymczasowe pliki są usuwane, gdy `NamedTempFile` jest zrzucany. Crate używa systemowego API do tworzenia plików, co zapewnia bezpieczeństwo i minimalizuje ryzyko kolizji nazw.

## See Also (Zobacz również)
- [Dokumentacja `tempfile` crate](https://docs.rs/tempfile)
- [Dokumentacja `std::fs`](https://doc.rust-lang.org/stable/std/fs/)
