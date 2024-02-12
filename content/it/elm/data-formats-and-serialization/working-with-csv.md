---
title:                "Lavorare con i CSV"
aliases:
- /it/elm/working-with-csv/
date:                  2024-02-03T19:19:19.178343-07:00
model:                 gpt-4-0125-preview
simple_title:         "Lavorare con i CSV"
tag:                  "Data Formats and Serialization"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/it/elm/working-with-csv.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Che cosa & Perché?

Lavorare con CSV (Valori Separati da Virgola) implica l'analisi e la generazione di file che memorizzano dati tabellari in un formato semplice di testo puro. Ciò è comunemente praticato dai programmatori per consentire uno scambio di dati facile tra diverse applicazioni o per elaborare grandi insiemi di dati in modo efficiente e in maniera sicura per quanto riguarda il tipo all'interno di Elm.

## Come fare:

Elm non ha un supporto integrato per l'analisi o la generazione di CSV; invece, si utilizzano spesso pacchetti di terze parti come `panosoft/elm-csv`. Gli esempi sottostanti evidenziano l'uso di base di questa libreria per l'analisi e la generazione di CSV.

### Analisi di CSV

Prima di tutto, devi aggiungere il pacchetto CSV al tuo progetto Elm:

```bash
elm install panosoft/elm-csv
```

Poi, puoi analizzare una stringa CSV in una lista di record. Un esempio semplice:

```elm
import Csv

csvData : String
csvData =
    "name,age\nJohn Doe,30\nJane Smith,25"

parseResult : Result String (List (List String))
parseResult =
    Csv.parse csvData

-- Output di esempio: Ok [["name","age"],["John Doe","30"],["Jane Smith","25"]]
```

### Generare CSV

Per generare una stringa CSV dai dati Elm, utilizza la funzione `Csv.encode`:

```elm
import Csv

records : List (List String)
records =
    [ ["name", "age"]
    , ["John Doe", "30"]
    , ["Jane Smith", "25"]
    ]

csvOutput : String
csvOutput =
    Csv.encode records

-- Output di esempio: "name,age\nJohn Doe,30\nJane Smith,25\n"
```

Questo approccio semplicistico ti consente di integrare le funzionalità CSV all'interno delle tue applicazioni Elm, sfruttando l'ambiente sicuro per tipo per la manipolazione e lo scambio di dati.
