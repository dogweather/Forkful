---
aliases:
- /sv/haskell/using-a-debugger/
date: 2024-01-26 03:50:28.100090-07:00
description: "Att anv\xE4nda en fels\xF6kare inneb\xE4r att dyka ner i koden med verktyg\
  \ utformade f\xF6r att inspektera, pausa och manipulera ett program under k\xF6\
  rning.\u2026"
lastmod: 2024-02-18 23:08:51.841421
model: gpt-4-0125-preview
summary: "Att anv\xE4nda en fels\xF6kare inneb\xE4r att dyka ner i koden med verktyg\
  \ utformade f\xF6r att inspektera, pausa och manipulera ett program under k\xF6\
  rning.\u2026"
title: "Att anv\xE4nda en debugger"
---

{{< edit_this_page >}}

## Vad & Varför?
Att använda en felsökare innebär att dyka ner i koden med verktyg utformade för att inspektera, pausa och manipulera ett program under körning. Programmerare gör detta för att jaga buggar, förstå programflödet och försäkra sig om att deras kod gör exakt det de förväntar sig.

## Hur gör man:
Låt oss ta en promenad med GHCi, Haskell's interaktiva miljö som kan fungera som en grundläggande felsökare. Du startar den med din Haskell-kod och börjar utforska. Här är ett exempel:

```Haskell
main :: IO ()
main = do
    putStrLn "Hej, vad heter du?"
    namn <- getLine
    putStrLn $ "Hej, " ++ namn ++ "! Låt oss felsöka."
    let resultat = buggigFunktion 5
    print resultat

buggigFunktion :: Int -> Int
buggigFunktion n = n * 2 -- Låtsas att det finns en bugg här
```

För att börja felsöka med GHCi:

```bash
$ ghci DinHaskellFil.hs
```

Sätt en brytpunkt vid `buggigFunktion`:

```Haskell
Prelude> :break buggigFunktion
```

Kör ditt program:

```Haskell
Prelude> :main
Hej, vad heter du?
```

Ditt program pausar vid `buggigFunktion`. Nu kan du inspektera variabler, stega genom koden och utvärdera uttryck.

## Djupdykning:
Historiskt har Haskell's rykte om rena funktioner och stark typning lett till tron att felsökningsverktyg var mindre kritiska. Verkligheten är annorlunda—komplexa program drar alltid nytta av bra felsökningsverktyg. GHCi tillhandahåller grundläggande felsökningskommandon. Dock, för en mer visuell upplevelse eller applikationer i större skala, kan du utforska IDEs med integrerade felsökare, som Visual Studio Code med Haskell-tillägg eller IntelliJ's Haskell-plugin.

Alternativ till felsökare inkluderar att använda utskriftsuttalanden, känt som "printf-debugging", eller att utnyttja Haskell's starka typsystem för att göra felaktiga tillstånd orepresenterbara. Ändå ersätter inget ibland att stega genom koden.

När det gäller genomförandedetaljer, fungerar Haskell's felsökare med körtidssystemet. Den kan hantera brytpunkter, stegexekvering och tillåter variabelinspektion. Dock, eftersom Haskell är latvärderat, kan saker bli lite icke-intuitiva. Att felsöka ett Haskell-program innebär ofta att hålla ett öga på när och hur uttryck utvärderas.

## Se även:
- [GHC Användarhandbok - Felsökare](https://downloads.haskell.org/~ghc/latest/docs/html/users_guide/debugging.html)
- [IntelliJ Haskell-plugin](https://plugins.jetbrains.com/plugin/8258-intellij-haskell)
