---
title:                "Aktuelles Datum abrufen"
aliases:
- de/elm/getting-the-current-date.md
date:                  2024-01-20T15:14:15.658251-07:00
simple_title:         "Aktuelles Datum abrufen"

tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/elm/getting-the-current-date.md"
---

{{< edit_this_page >}}

## Was & Warum?
Das Abrufen des aktuellen Datums ist ein Prozess, bei dem wir die momentane Datumswerte (Tag, Monat, Jahr) vom Computer erhalten. Programmierer nutzen diese Funktion für Features wie Kalender, Zeitstempel oder Gültigkeitsprüfungen.

## Anleitung:
In Elm, holen Sie das aktuelle Datum mit der `Time`-Modul. Verbinden Sie dies mit einer Subscription, um das Datum im Model zu aktualisieren.

```Elm
import Browser
import Html exposing (Html, text)
import Task
import Time

type Msg
    = Tick Time.Posix

type alias Model =
    { currentTime : Time.Posix }

main =
    Browser.element
        { init = init
        , view = view
        , update = update
        , subscriptions = subscriptions
        }

init : () -> (Model, Cmd Msg)
init _ =
    (Model (Time.millisToPosix 0), Cmd.none)

subscriptions : Model -> Sub Msg
subscriptions _ =
    Time.every 1000 Tick

update : Msg -> Model -> (Model, Cmd Msg)
update msg model =
    case msg of
        Tick newTime ->
            ({ model | currentTime = newTime }, Cmd.none)

view : Model -> Html Msg
view model =
    let
        currentTimeString = Time.posixToMillis model.currentTime |> String.fromInt
    in
    text ("Aktuelles Datum und Uhrzeit: " ++ currentTimeString)

```

Die `view`-Funktion konvertiert die Posix-Zeit in einen String, um sie anzuzeigen. Beachten Sie, dass das Datum als Millisekunden seit dem 1. Januar 1970 (Epochenzeit) dargestellt ist.

## Tiefgang:
Historisch gesehen ist die Posix-Zeit ein Standard, der in den 70er Jahren für Unix-Systeme entwickelt wurde. Alternativ gibt es Bibliotheken wie `justinmimbs/time-extra`, die zusätzliche Funktionen für Datumsoperationen bieten. Die Elm-Uhrzeit wird als Posix-Zeit in Millisekunden gespeichert; das erlaubt einfache Umrechnungen und Manipulationen.

## Siehe Auch:
- Elm Time Dokumentation: [https://package.elm-lang.org/packages/elm/time/latest/](https://package.elm-lang.org/packages/elm/time/latest/)
- Justinmimbs Zeit-Extra: [https://package.elm-lang.org/packages/justinmimbs/time-extra/latest/](https://package.elm-lang.org/packages/justinmimbs/time-extra/latest/)
- Elm Guide zu Zeit: [https://guide.elm-lang.org/effects/time.html](https://guide.elm-lang.org/effects/time.html)
