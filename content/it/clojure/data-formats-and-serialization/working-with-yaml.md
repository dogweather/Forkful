---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:24:51.560340-07:00
description: "YAML, un acronimo ricorsivo per \"YAML Ain't Markup Language\" (YAML\
  \ non \xE8 un linguaggio di markup), \xE8 un formato di serializzazione dati leggibile\u2026"
lastmod: '2024-03-13T22:44:43.062717-06:00'
model: gpt-4-0125-preview
summary: "YAML, un acronimo ricorsivo per \"YAML Ain't Markup Language\" (YAML non\
  \ \xE8 un linguaggio di markup), \xE8 un formato di serializzazione dati leggibile\
  \ dall'uomo usato per file di configurazione e scambio di dati tra linguaggi con\
  \ diverse strutture di dati."
title: Lavorare con YAML
weight: 41
---

## Come fare:
Clojure non include supporto incorporato per YAML, ma puoi utilizzare librerie di terze parti come `clj-yaml` per analizzare e generare dati YAML. Prima, aggiungi la libreria alle dipendenze del tuo progetto:

```clojure
;; Aggiungi questo alle dipendenze del tuo project.clj
[clj-yaml "0.7.0"]
```

Ecco come puoi usare `clj-yaml` per analizzare YAML e convertire mappe di Clojure in YAML.

### Analisi di YAML:
```clojure
(require '[clj-yaml.core :as yaml])

;; Analisi di una stringa YAML
(let [yaml-str "name: John Doe\nage: 30\nlanguages:\n  - Clojure\n  - Python"]
  (yaml/parse-string yaml-str))
;; Output:
;; => {"name" "John Doe", "age" 30, "languages" ["Clojure" "Python"]}
```

### Generazione di YAML da Clojure:
```clojure
(require '[clj-yaml.core :as yaml])

;; Conversione di una mappa di Clojure in una stringa YAML
(let [data-map {:name "Jane Doe" :age 28 :languages ["Java" "Ruby"]}]
  (yaml/generate-string data-map))
;; Output:
; "age: 28\nlanguages:\n- Java\n- Ruby\nname: Jane Doe\n"
```

Queste semplici operazioni con `clj-yaml` possono essere integrate in applicazioni Clojure per gestire file di configurazione o facilitare lo scambio di dati con altri servizi o componenti che usano YAML.
