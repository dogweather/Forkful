---
aliases:
- /sv/clojure/working-with-toml/
date: 2024-01-26 04:20:39.508304-07:00
description: "Att arbeta med TOML inneb\xE4r att du hanterar data i det minimala formatet\
  \ \"Toms Obvious, Minimal Language\", popul\xE4rt f\xF6r konfigurationsfiler p\xE5\
  \ grund av\u2026"
lastmod: 2024-02-18 23:08:51.484728
model: gpt-4-0125-preview
summary: "Att arbeta med TOML inneb\xE4r att du hanterar data i det minimala formatet\
  \ \"Toms Obvious, Minimal Language\", popul\xE4rt f\xF6r konfigurationsfiler p\xE5\
  \ grund av\u2026"
title: Att arbeta med TOML
---

{{< edit_this_page >}}

## Vad & Varför?
Att arbeta med TOML innebär att du hanterar data i det minimala formatet "Toms Obvious, Minimal Language", populärt för konfigurationsfiler på grund av dess lättlästa format. Programmerare använder det för enkel konfigurationshantering som fungerar direkt ur lådan med ett människovänligt syntax.

## Hur man gör:
För att arbeta med TOML i Clojure behöver du ett bibliotek som `clj-toml`. Lägg först till det i din `deps.edn`:

```clojure
{:deps {clj-toml {:mvn/version "0.5.0"}}}
```

Sedan tolkar du lite TOML:

```clojure
(require '[clj-toml.core :as toml])

(def config-str "title = 'TOML Example'")

(def parsed-config (toml/parse-string config-str))

;; Hämta titeln från det tolkade TOML
(println (:title parsed-config)) ;; Utdata: TOML Example
```

För att generera TOML:

```clojure
(def data {:title "TOML Example"})

(println (toml/generate-string data))
;; Utdata: title = "TOML Example"
```

## Djupdykning
TOML skapades runt 2013 av Tom Preston-Werner, medgrundare av GitHub, som ett enklare alternativ till YAML och JSON för konfigurationsfiler. Det syftar till klarhet och avser att vara en spec människor kan läsa utan ytterligare verktyg.

Medan JSON ofta används för API:er och webbapplikationer, och YAML kan bli komplicerat med referenser och skriptmöjligheter, sticker TOML ut med fokus på enkla, tabellbaserade strukturer. Denna enkelhet gör det särskilt populärt i Rust-gemenskapen och andra moderna programspråksmiljöer.

Clojure, med fokus på enkelhet och praktisk tillämpning, passar väl ihop med TOML för konfig. `clj-toml` eller alternativa bibliotek överbryggar klyftan. De översätter TOMLs statiska data till Clojures dynamiska, funktionella värld.

## Se även
- TOMLs GitHub Repo: [github.com/toml-lang/toml](https://github.com/toml-lang/toml)
- `clj-toml` på Clojars: [clojars.org/clj-toml](https://clojars.org/clj-toml)
- Clojure Dokumentation: [clojure.org](https://clojure.org/guides/getting_started)
- Introduktion till `clj-toml`: [github.com/lantiga/clj-toml](https://github.com/lantiga/clj-toml)
