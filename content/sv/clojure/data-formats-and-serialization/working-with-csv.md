---
title:                "Arbeta med CSV"
aliases:
- sv/clojure/working-with-csv.md
date:                  2024-02-03T19:19:11.303957-07:00
model:                 gpt-4-0125-preview
simple_title:         "Arbeta med CSV"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/clojure/working-with-csv.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Vad och varför?

Att arbeta med CSV-filer (Comma-Separated Values, komma-separerade värden) innebär att tolka och generera textdata strukturerad som rader och kolumner, likt data i kalkylblad. Denna process är avgörande för datautbyte mellan applikationer, databaser och för uppgifter som innefattar datatransformation, på grund av CSV:s breda acceptans som ett lättviktigt, interoperabelt format.

## Hur man gör:

### Läsa en CSV-fil
Clojure har ingen inbyggd CSV-tolkning i sitt standardbibliotek, men du kan använda `clojure.data.csv`-biblioteket för detta ändamål. Lägg först till biblioteket i dina projektberoenden.

I din `project.clj`, lägg till följande beroende:
```clojure
[clojure.data.csv "1.0.0"]
```
För att läsa en CSV-fil och skriva ut varje rad:
```clojure
(require '[clojure.data.csv :as csv]
         '[clojure.java.io :as io])

(with-open [reader (io/reader "path/to/yourfile.csv")]
  (doall
   (map println (csv/read-csv reader))))
```
Detta kommer att skriva ut varje rad av CSV-filen som en Clojure-vektor.

### Skriva till en CSV-fil
För att skriva data till en CSV-fil kan du använda samma `clojure.data.csv`-bibliotek:
```clojure
(require '[clojure.data.csv :as csv]
         '[clojure.java.io :as io])

(let [data [["id" "name" "age"]
            ["1" "John Doe" "28"]
            ["2" "Jane Doe" "31"]]]
  (with-open [writer (io/writer "path/to/outputfile.csv")]
    (csv/write-csv writer data)))
```
Detta skapar eller skriver över `outputfile.csv`, och fyller den med den specificerade datan.

### Använda ett tredjepartsbibliotek: `clojure.data.csv`

Även om `clojure.data.csv` är det kanske mest okomplicerade biblioteket för hantering av CSV i Clojure, för mer komplexa uppgifter, såsom hantering av CSV-filer med speciella tecken eller oortodoxa avgränsare, kan du utforska ytterligare alternativ inom ekosystemet eller till och med överväga Java-interoperabilitet med bibliotek som Apache Commons CSV. Dock, för de flesta standardiserade CSV-behandlingsuppgifter i Clojure, tillhandahåller `clojure.data.csv` en enkel och effektiv verktygslåda.
