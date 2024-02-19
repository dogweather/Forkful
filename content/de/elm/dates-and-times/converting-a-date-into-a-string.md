---
aliases:
- /de/elm/converting-a-date-into-a-string/
date: 2024-01-20 17:36:15.868862-07:00
description: "Ein Datum in einen String umzuwandeln, bedeutet, die Date-Information\
  \ in eine Textform zu bringen, die f\xFCr Menschen lesbar ist. Programmierer machen\
  \ das,\u2026"
lastmod: 2024-02-18 23:09:04.793639
model: gpt-4-1106-preview
summary: "Ein Datum in einen String umzuwandeln, bedeutet, die Date-Information in\
  \ eine Textform zu bringen, die f\xFCr Menschen lesbar ist. Programmierer machen\
  \ das,\u2026"
title: Datum in einen String umwandeln
---

{{< edit_this_page >}}

## Was & Warum?
Ein Datum in einen String umzuwandeln, bedeutet, die Date-Information in eine Textform zu bringen, die für Menschen lesbar ist. Programmierer machen das, um Daten anzuzeigen oder zu speichern, in einer Form, die Nutzer verstehen.

## So geht's:
Ein einfaches Beispiel in Elm, um das aktuelle Datum und die Zeit in einen String umzuwandeln:

```elm
import Time exposing (Posix)
import Time.Zone exposing (custom)

toStringWithZone : Time.Zone -> Posix -> String
toStringWithZone zone time =
    Time.toIsoString time

main =
    -- Beispiel-Datum: 17. März 2023, 12:00 UTC
    let
        exampleDate = Time.millisToPosix 1679155200000
        zone = custom 60 "CET"
    in
    toStringWithZone zone exampleDate
    -- Output: "2023-03-17T13:00:00.000Z"
```

Hier nutzt `Time.toIsoString` die Unix-Zeit in Millisekunden und konvertiert sie in einen standardisierten ISO-8601 String.

## Tiefergehend:
Historisch gesehen wurden verschiedene Formate für die Darstellung von Daten benutzt – von regionalen Variationen bis zu streng standardisierten Formaten wie ISO 8601 für internationale Vereinheitlichung.

Alternative Ansätze in Elm könnten die Verwendung von Bibliotheken wie `elm-time` oder `justinmimbs/date` sein, die noch flexiblere oder intuitivere Schnittstellen zur Datumskonvertierung bieten.

Die Umsetzung der Datumskonvertierung in Elm erfolgt durch die `Time`-Module, welche Funktionen für den Umgang mit Zeitwerten (Unix-Zeit), Zonen und der Konvertierung zu lesbareren Formaten, wie ISO Strings, bereitstellen. Besonderheiten wie Zeitumstellungen und Schaltjahre werden dabei von den Funktionen berücksichtigt.

## Siehe auch:
- [`elm/time` Dokumentation](https://package.elm-lang.org/packages/elm/time/latest/)
- [ISO 8601 Standard](https://www.iso.org/iso-8601-date-and-time-format.html)
- [`justinmimbs/date` Bibliothek](https://package.elm-lang.org/packages/justinmimbs/date/latest/)
- [`elm-community/elm-time`](https://package.elm-lang.org/packages/elm-community/elm-time/latest/)
