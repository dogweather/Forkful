---
date: 2024-01-26 04:20:37.799581-07:00
description: "Praca z TOML oznacza obs\u0142ug\u0119 danych w formacie Minimal \"\
  Tom's Obvious, Minimal Language\", popularnym w przypadku plik\xF3w konfiguracyjnych\
  \ ze wzgl\u0119du na\u2026"
lastmod: '2024-03-13T22:44:35.021104-06:00'
model: gpt-4-0125-preview
summary: "Praca z TOML oznacza obs\u0142ug\u0119 danych w formacie Minimal \"Tom's\
  \ Obvious, Minimal Language\", popularnym w przypadku plik\xF3w konfiguracyjnych\
  \ ze wzgl\u0119du na \u0142atwo\u015B\u0107 odczytu."
title: Praca z TOML
weight: 39
---

## Jak to zrobić:
Aby pracować z TOML w Clojure, potrzebujesz biblioteki takiej jak `clj-toml`. Najpierw dodaj ją do swojego `deps.edn`:

```clojure
{:deps {clj-toml {:mvn/version "0.5.0"}}}
```

Następnie przetłumacz jakiś TOML:

```clojure
(require '[clj-toml.core :as toml])

(def config-str "title = 'TOML Example'")

(def parsed-config (toml/parse-string config-str))

;; Pobierz tytuł z przetłumaczonego TOML
(println (:title parsed-config)) ;; Wyjście: TOML Example
```

Aby wygenerować TOML:

```clojure
(def data {:title "TOML Example"})

(println (toml/generate-string data))
;; Wyjście: title = "TOML Example"
```

## Zagłębiając się
TOML został stworzony około 2013 roku przez Toma Preston-Wernera, współzałożyciela GitHuba, jako prostsza alternatywa dla YAML i JSON dla plików konfiguracyjnych. Ma na celu jasność i zamierza być specyfikacją, którą ludzie mogą czytać bez dodatkowych narzędzi.

Podczas gdy JSON jest często używany dla API i aplikacji internetowych, a YAML może stać się skomplikowany z powodu odniesień i możliwości skryptowych, TOML wyróżnia się koncentracją na prostych, tabelarycznych strukturach. Ta prostota sprawia, że jest szczególnie popularny w społeczności Rust i innych nowoczesnych środowiskach językowych.

Clojure, ze swoim skupieniem na prostocie i praktyczności, dobrze współpracuje z TOML dla konfiguracji. `clj-toml` lub alternatywne biblioteki wypełniają lukę. Przekładają statyczne dane TOML na dynamiczny, funkcjonalny świat Clojure.

## Zobacz również
- Repozytorium TOML na GitHubie: [github.com/toml-lang/toml](https://github.com/toml-lang/toml)
- `clj-toml` na Clojars: [clojars.org/clj-toml](https://clojars.org/clj-toml)
- Dokumentacja Clojure: [clojure.org](https://clojure.org/guides/getting_started)
- Wprowadzenie do `clj-toml`: [github.com/lantiga/clj-toml](https://github.com/lantiga/clj-toml)
