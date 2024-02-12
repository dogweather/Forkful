---
title:                "Sammenslåing av strenger"
aliases:
- /no/elm/concatenating-strings/
date:                  2024-01-20T17:34:36.708009-07:00
model:                 gpt-4-1106-preview
simple_title:         "Sammenslåing av strenger"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/no/elm/concatenating-strings.md"
---

{{< edit_this_page >}}

## What & Why?
I Elm handler sammenslåing av strenger om å sette sammen to eller flere tekstfragmenter til en lengre tekst. Vi gjør dette for å bygge dynamisk innhold, som brukernavn eller datoer i meldinger.

## How to:
Elm gjør det lett å slå sammen strenger med `++` operatoren. Her er et eksempel:

```Elm
main =
  let
    greeting = "Hei, "
    name = "Ola"
  in
    text (greeting ++ name ++ "!")
```

Kjører du dette, vil utdataen bli `Hei, Ola!`

## Deep Dive
Tilbake i tiden var sammensmelting av strenger litt av et styr siden man måtte holde øye med minne og ytelse. Moderne språk som Elm tar seg av dette for deg. Elm bruker `(++)` operator til å slå sammen strenger, og det gjør koden ren og lett. Men det er greit å være oppmerksom på at for store mengder string konkatenasjon kan være tregt, fordi Elm må traversere hele strengen hver gang.

Det er også alternativer for å slå sammen strenger:
- `String.concat` tar en liste med strenger og smelter dem sammen.
- `String.join` slår sammen en liste med strenger med en delimiter.

Her er et eksempel:

```Elm
main =
  let
    words = [ "Elm", "er", "gøy!" ]
  in
    text (String.join " " words)
```

Dette vil også gi deg `Elm er gøy!`

## See Also
Ta en titt på Elm sin offisielle dokumentasjon for mer detaljer:
- [String - Elm Documentation](https://package.elm-lang.org/packages/elm/core/latest/String)
- Lær mer om funksjonell programmering [Haskell.org](http://www.haskell.org) (Elm er inspirert av Haskell).
- [Elm Guide - Text](https://guide.elm-lang.org/core_language.html) for en intro til strenger og mer.
