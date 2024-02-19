---
aliases:
- /it/elm/finding-the-length-of-a-string/
date: 2024-01-20 17:47:15.247992-07:00
description: "(Find out the length) Capire la lunghezza di una stringa significa determinare\
  \ quanti caratteri contiene. I programmatori lo fanno per validare l'input,\u2026"
lastmod: 2024-02-18 23:08:55.797666
model: gpt-4-1106-preview
summary: "(Find out the length) Capire la lunghezza di una stringa significa determinare\
  \ quanti caratteri contiene. I programmatori lo fanno per validare l'input,\u2026"
title: Trovare la lunghezza di una stringa
---

{{< edit_this_page >}}

## What & Why?
(Find out the length)
Capire la lunghezza di una stringa significa determinare quanti caratteri contiene. I programmatori lo fanno per validare l'input, limitare il testo, o semplicemente per manipolare dati testuali.

## How to:
(Step by step)
Elm rende semplice trovare la lunghezza di una stringa. Usa la funzione `String.length`:

```Elm
module Main exposing (..)
import String

stringLength : String -> Int
stringLength str =
    String.length str

-- Uso
main =
    stringLength "Ciao, mondo!" 
    |> toString
    |> text
```

Output:

```
12
```

## Deep Dive:
(Curious insights)
La funzione `String.length` è diretta e affidabile, ma è interessante notare che contava i caratteri in modo diverso nelle prime versioni di Elm. Prima, calcolava la lunghezza in base a unità di codice UTF-16, cosa che poteva portare a conteggi errati con emoji o alcuni caratteri speciali. Ora, Elm misura correttamente i caratteri Unicode, rendendo il conteggio universale. Alcuni linguaggi offrono alternative, come loop personalizzati o funzioni basate su espressioni regolari, ma in Elm, `String.length` è la via da seguire.

## See Also:
(Fonti utili)
- Elm `String` package: [https://package.elm-lang.org/packages/elm/core/latest/String](https://package.elm-lang.org/packages/elm/core/latest/String)
- Discussione sulla misurazione della lunghezza delle stringhe Unicode: [https://unicode.org/reports/tr29/](https://unicode.org/reports/tr29/)
