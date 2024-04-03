---
date: 2024-01-20 17:52:59.681210-07:00
description: "Debug-utskrifter hj\xE4lper programmerare att f\xF6rst\xE5 vad deras\
  \ kod g\xF6r genom att visa mellanliggande v\xE4rden och processfl\xF6den. De anv\xE4\
  nds f\xF6r att snabbt\u2026"
lastmod: '2024-03-13T22:44:37.957591-06:00'
model: gpt-4-1106-preview
summary: "Debug-utskrifter hj\xE4lper programmerare att f\xF6rst\xE5 vad deras kod\
  \ g\xF6r genom att visa mellanliggande v\xE4rden och processfl\xF6den."
title: "Skriva ut fels\xF6kningsdata"
weight: 33
---

## How to:
Att skriva ut debug-meddelanden i Haskell kan göras med `print` eller `putStrLn`. Här kommer några exempel:

```Haskell
main :: IO ()
main = do
  putStrLn "This is a debug message"

  let number = 42
  print number  -- print kan hantera alla typer som är en instans av Show
```
Kör du detta får du följande utskrift:

```
This is a debug message
42
```

## Deep Dive
I Haskell's tidiga dagar var I/O, inklusive enkel utskrift, omständlig på grund av språkets rena funktionsnatur. Nu har vi `IO` monaden som hanterar effekter. För debug-ändamål kan `Debug.Trace` också användas, men den bör undvikas i produktionskod eftersom den får sidoeffekter i vad som ser ut att vara ren kod. Vi har också `printf` från `Text.Printf` för formaterad text, som är lik `printf` i C.

```Haskell
import Debug.Trace (trace)

traceExample :: Int -> Int -> Int
traceExample x y = trace ("Adding " ++ show x ++ " and " ++ show y) (x + y)
```

Användning av `trace` ska dock användas med försiktighet då det kan orsaka svåråtkomliga buggar. Andra verktyg för debugging, som GHCi's debugger och mer specialiserade bibliotek finns, som kan vara lämpligare för avancerade behov.

## See Also
- The GHC User's Guide on debugging: https://downloads.haskell.org/~ghc/latest/docs/html/users_guide/debugging.html
- `Debug.Trace` module: http://hackage.haskell.org/package/base-4.16.0.0/docs/Debug-Trace.html
- `Text.Printf` module: http://hackage.haskell.org/package/base-4.16.0.0/docs/Text-Printf.html
