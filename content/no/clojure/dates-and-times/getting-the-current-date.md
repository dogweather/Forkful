---
aliases:
- /no/clojure/getting-the-current-date/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:09:16.363112-07:00
description: "\xC5 f\xE5 den n\xE5v\xE6rende datoen i programmering er avgj\xF8rende\
  \ av en rekke grunner, inkludert logging, tidsstempel p\xE5 hendelser og planlegging\
  \ av oppgaver. I\u2026"
lastmod: 2024-02-18 23:08:53.574322
model: gpt-4-0125-preview
summary: "\xC5 f\xE5 den n\xE5v\xE6rende datoen i programmering er avgj\xF8rende av\
  \ en rekke grunner, inkludert logging, tidsstempel p\xE5 hendelser og planlegging\
  \ av oppgaver. I\u2026"
title: "F\xE5 dagens dato"
---

{{< edit_this_page >}}

## Hva & Hvorfor?
Å få den nåværende datoen i programmering er avgjørende av en rekke grunner, inkludert logging, tidsstempel på hendelser og planlegging av oppgaver. I Clojure, en Lisp-dialekt på JVM, utnytter denne oppgaven Java-interoperabilitetsmuligheter, som tillater enkel tilgang til det rike Java Date-Time API-et.

## Hvordan:

### Ved bruk av Java Interop
Clojures sømløse interoperabilitet med Java lar deg tappe direkte inn i Java Date-Time API-et. Slik kan du få den nåværende datoen:

```clojure
(import java.time.LocalDate)

(defn get-current-date []
  (str (LocalDate/now)))

;; Eksempel på utdata
(get-current-date) ; "2023-04-15"
```

### Ved å bruke clj-time-biblioteket
For en mer idiomatisk Clojure-løsning, kan du velge `clj-time`-biblioteket, en innpakning rundt Joda-Time, selv om det for de fleste nye prosjekter anbefales å bruke det innebygde Java 8 Date-Time API-et. Men, skulle du foretrekke eller trenge `clj-time`:

Først, legg til `clj-time` i prosjektavhengighetene dine. I din `project.clj`, inkluder:

```clojure
[clj-time "0.15.2"]
```

Deretter, bruk det for å få den nåværende datoen:

```clojure
(require '[clj-time.core :as time])

(defn get-current-date-clj-time []
  (str (time/now)))

;; Eksempel på utdata
(get-current-date-clj-time) ; "2023-04-15T12:34:56.789Z"
```

Begge metodene gir raske, effektive måter å få den nåværende datoen på i Clojure, ved å utnytte kraften fra den underliggende Java-plattformen eller bekvemmeligheten av et Clojure-spesifikt bibliotek.
