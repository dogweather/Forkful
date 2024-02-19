---
aliases:
- /sv/elm/getting-the-current-date/
date: 2024-01-20 15:14:10.019563-07:00
description: "Att f\xE5 tag p\xE5 det aktuella datumet inneb\xE4r att vi hittar dagens\
  \ datum i realtid. Programmerare g\xF6r detta f\xF6r funktioner som loggar, tidsst\xE4\
  mplar och\u2026"
lastmod: 2024-02-18 23:08:51.719578
summary: "Att f\xE5 tag p\xE5 det aktuella datumet inneb\xE4r att vi hittar dagens\
  \ datum i realtid. Programmerare g\xF6r detta f\xF6r funktioner som loggar, tidsst\xE4\
  mplar och\u2026"
title: "Att h\xE4mta aktuellt datum"
---

{{< edit_this_page >}}

## Vad & Varför?
Att få tag på det aktuella datumet innebär att vi hittar dagens datum i realtid. Programmerare gör detta för funktioner som loggar, tidsstämplar och datumvalidering.

## Hur man gör:
```Elm
import Time
import Task
import Browser

type Msg = GotTime Time.Posix

getTime : Cmd Msg
getTime =
    Task.perform GotTime Time.now

main =
    Browser.element
        { init = \_ -> ( {}, getTime )
        , view = \_ -> Html.text ""
        , update = \msg -> \model -> (model, Cmd.none)
        , subscriptions = \_ -> Sub.none
        }

```
Körningsexempel (output varierar):
```
{ timestamp = 1615125600000 }
```

## Fördjupning
I Elm hanteras tiden genom `Time`-modulen och den bygger på POSIX-tidsstandard. Tidigare kunde man få nuvarande datum genom att använda JavaScript, men nu görs det mer Elm-idiomatiskt genom att anropa `Time.now`. Alternativen inkluderar att använda externa paket eller att skicka in tiden från JavaScript via ports, men `Time.now` är standard och enkel. Vidare hanterar Elm tidszoner genom att omvandla all tid till UTC.

## Se även
- Elm Time documentation: https://package.elm-lang.org/packages/elm/time/latest/
- An article about Elm and time management: https://medium.com/elm-shorts/working-with-time-in-elm-8ec8fa854dd5
