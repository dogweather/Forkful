---
title:                "Få dagens dato"
date:                  2024-02-03T19:09:36.925981-07:00
model:                 gpt-4-0125-preview
simple_title:         "Få dagens dato"
tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/no/haskell/getting-the-current-date.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Hva & Hvorfor?
Å hente gjeldende dato i Haskell innebærer å få tak i systemets nåværende tid og omdanne den til et lesbart datoformat. Programmerere gjør dette for å utføre operasjoner basert på datoen, som logging, planlegging av oppgaver, eller tidsstempling av hendelser i applikasjoner.

## Hvordan:
Haskells standardbibliotek, `base`, tilbyr `Data.Time`-modulen som gir funksjonalitet for å arbeide med datoer og tider. Her er hvordan du bruker den for å få gjeldende dato:

```haskell
import Data.Time (getCurrentTime, utctDay)

main :: IO ()
main = do
    nå <- getCurrentTime
    let iDag = utctDay nå
    print iDag
```

Eksempel på utdata:
```
2023-04-12
```

For mer fleksibilitet, som formatering av dato eller arbeid med forskjellige tidssoner, er `time`-biblioteket uvurderlig. Her er hvordan du kan formatere gjeldende dato:

```haskell
import Data.Time

main :: IO ()
main = do
    nå <- getCurrentTime
    tidssone <- getCurrentTimeZone
    let soneNå = utcToLocalTime tidssone nå
    putStrLn $ formatTime defaultTimeLocale "%Y-%m-%d" soneNå
```

Dette skriver ut gjeldende dato i `YYYY-MM-DD`-formatet, justert til lokal tidssone.

I tillegg, for støtte fra tredjepartsbiblioteker, anbefales `time` på det sterkeste og brukes ofte innen Haskell-samfunnet for dens omfattende evner til dato- og tidsmanipulering. Eksemplene ovenfor bruker dette biblioteket.

Hvis du trenger mer omfattende datomanipulering, inkludert parsing fra strenger eller aritmetiske operasjoner med datoer og tider, vil det være nyttig å utforske ytterligere funksjoner innen `Data.Time`.
