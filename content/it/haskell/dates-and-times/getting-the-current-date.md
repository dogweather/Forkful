---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:09:38.505539-07:00
description: "Ottenere la data corrente in Haskell comporta il recupero del tempo\
  \ corrente del sistema e la sua trasformazione in un formato di data leggibile.\
  \ I\u2026"
lastmod: '2024-03-13T22:44:43.485582-06:00'
model: gpt-4-0125-preview
summary: Ottenere la data corrente in Haskell comporta il recupero del tempo corrente
  del sistema e la sua trasformazione in un formato di data leggibile.
title: Ottenere la data corrente
weight: 29
---

## Come fare:
La libreria standard di Haskell, `base`, fornisce il modulo `Data.Time` che offre funzionalità per lavorare con date e orari. Ecco come usarlo per ottenere la data corrente:

```haskell
import Data.Time (getCurrentTime, utctDay)

main :: IO ()
main = do
    now <- getCurrentTime
    let today = utctDay now
    print today
```

Output di esempio:
```
2023-04-12
```

Per maggiore flessibilità, come la formattazione della data o il lavoro con diversi fusi orari, la libreria `time` è inestimabile. Ecco come potreste formattare la data corrente:

```haskell
import Data.Time

main :: IO ()
main = do
    now <- getCurrentTime
    timezone <- getCurrentTimeZone
    let zoneNow = utcToLocalTime timezone now
    putStrLn $ formatTime defaultTimeLocale "%Y-%m-%d" zoneNow
```

Questo stampa la data corrente nel formato `AAAA-MM-GG`, aggiustato al fuso orario locale.

Inoltre, per il supporto di librerie di terze parti, `time` è fortemente raccomandata ed è spesso usata all'interno della comunità Haskell per le sue ampie capacità di manipolazione di date e orari. Gli esempi sopra utilizzano questa libreria.

Se avete bisogno di una manipolazione delle date più comprensiva, inclusa l'analisi da stringhe o operazioni aritmetiche con date e orari, esplorare funzioni aggiuntive all'interno di `Data.Time` sarà utile.
