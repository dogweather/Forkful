---
date: 2024-01-20 17:36:34.355068-07:00
description: "Omforming fra dato til streng lar oss vise datoer som lesbare tekststrenger.\
  \ Dette er essensielt for brukergrensesnitt og datalagring i et forst\xE5elig\u2026"
lastmod: '2024-03-13T22:44:40.853855-06:00'
model: gpt-4-1106-preview
summary: Omforming fra dato til streng lar oss vise datoer som lesbare tekststrenger.
title: Konvertere en dato til en streng
weight: 28
---

## How to:
I Haskell, bruk `Data.Time`-biblioteket for å håndtere datoer og `formatTime` for å konvertere dem.

```Haskell
import Data.Time

main :: IO ()
main = do
  let someDay = fromGregorian 2023 3 14 -- År, måned, dag
  let dateString = formatTime defaultTimeLocale "%Y-%m-%d" someDay
  putStrLn dateString -- Viser: 2023-03-14
```

## Deep Dive
Haskell bruker `Data.Time` for datoer, en del av `time`-pakken. Introduced in GHC 6.6.1, den erstatter eldre `System.Time` fra `old-time`-pakken. `formatTime` tillater skreddersydde dato-strenger ved å ta i bruk formateringsdirektiver, som `%Y-%m-%d` for ISO 8601-format. 
Alternativt, for predefinerte formater brukes `Show`-instansen til `UTCTime` men med mindre fleksibilitet. Under hetten konverterer `formatTime` interne dato-representasjoner til strenger basert på lokal tidssone og ønsket format.

## See Also
- Haskell `time`-biblioteket: http://hackage.haskell.org/package/time
- `Data.Time`-modulen: http://hackage.haskell.org/package/time-1.9.3/docs/Data-Time.html
- Format-direktiver for `formatTime`: https://hackage.haskell.org/package/time-1.9.3/docs/Data-Time-Format.html#v:formatTime
