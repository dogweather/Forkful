---
title:                "Pisanie pliku tekstowego"
date:                  2024-02-03T19:27:55.389469-07:00
model:                 gpt-4-0125-preview
simple_title:         "Pisanie pliku tekstowego"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/pl/clojure/writing-a-text-file.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Co i dlaczego?

Pisanie pliku tekstowego w Clojure polega na tworzeniu lub modyfikowaniu plików w celu zapisania danych poza aplikacją, umożliwiając trwałość, konfigurację, logowanie lub komunikację międzyprocesową. Programiści wykonują to zadanie, aby zewnętrznie przechowywać stan aplikacji, konfiguracje lub dzielić informacje między różnymi częściami programu lub różnymi programami.

## Jak to zrobić:

### Pisanie tekstu do pliku przy użyciu wbudowanych funkcji Clojure

Funkcja `spit` jest najprostszym sposobem na zapis tekst do pliku w Clojure. Przyjmuje dwa argumenty: ścieżkę pliku i łańcuch do zapisania. Jeśli plik nie istnieje, `spit` go utworzy. Jeśli istnieje, `spit` go nadpisze.

```clojure
(spit "example.txt" "Witaj, świecie!")
```

Aby dodać tekst do istniejącego pliku, możesz użyć funkcji `spit` z opcją `:append`.

```clojure
(spit "example.txt" "\nDodajmy tę nową linię." :append true)
```

Po uruchomieniu tych fragmentów, "example.txt" będzie zawierać:

```
Witaj, świecie!
Dodajmy tę nową linię.
```

### Korzystanie z bibliotek stron trzecich

Chociaż wbudowane możliwości Clojure często są wystarczające, społeczność opracowała solidne biblioteki do bardziej skomplikowanych lub specyficznych zadań. Dla operacji na plikach popularną biblioteką jest `clojure.java.io`, która zapewnia bardziej java'owe podejście do obsługi plików.

Aby użyć `clojure.java.io` do zapisywania do pliku, najpierw musisz ją zaimportować:

```clojure
(require '[clojure.java.io :as io])
```

Następnie można użyć funkcji `writer`, aby uzyskać obiekt piszący, i funkcji `spit` (lub innych takich jak `print`, `println`), aby pisać do pliku:

```clojure
(with-open [w (io/writer "example_with_io.txt")]
  (.write w "To zostało napisane przy użyciu clojure.java.io"))
```

To utworzy (lub nadpisze, jeśli już istnieje) "example_with_io.txt" z tekstem:

```
To zostało napisane przy użyciu clojure.java.io
```

Pamiętaj: `with-open` zapewnia, że plik jest odpowiednio zamknięty po zapisie, unikając potencjalnych wycieków zasobów.
