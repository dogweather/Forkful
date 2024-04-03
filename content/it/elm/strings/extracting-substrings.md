---
date: 2024-01-20 17:45:22.986945-07:00
description: "Estrarre sottostringhe significa selezionare parti specifiche di una\
  \ stringa. I programmatori lo fanno per manipolare o analizzare testi in modo pi\xF9\
  \u2026"
lastmod: '2024-03-13T22:44:43.339631-06:00'
model: gpt-4-1106-preview
summary: Estrarre sottostringhe significa selezionare parti specifiche di una stringa.
title: Estrazione di sottostringhe
weight: 6
---

## How to:
Elm usa funzioni come `String.slice` per estrarre sottostringhe. Ecco come funziona:

```Elm
import String

-- Estrai una sottostringa dalla posizione `start` alla posizione `end`.
substring : String -> Int -> Int -> String
substring text start end =
    String.slice start end text

-- Esempio d'uso:
main =
    let
        text = "Ciao, mondo!"
    in
    substring text 0 4  -- Risultato: "Ciao"
```

Output:
```Elm
"Ciao"
```

## Deep Dive
Il concetto di estrarre sottostringhe risale ai primi giorni della programmazione. Prima di funzioni dedicate, gli sviluppatori dovevano iterare carattere per carattere. In Elm, oltre a `String.slice`, puoi usare `String.left` o `String.right` per ottenere parti di una stringa dal principio o dalla fine. Dettagli importanti da tenere a mente includono l'indexing in Elm che inizia da 0 e che `String.slice` prenderà caratteri fino, ma non inclusi, l'indice `end`.

## See Also
- Documentazione Elm `String`: https://package.elm-lang.org/packages/elm/core/latest/String
- Elm Guide sui record e le stringhe: https://guide.elm-lang.org/records/strings.html
- Stack Overflow per domande specifiche: https://stackoverflow.com/questions/tagged/elm
