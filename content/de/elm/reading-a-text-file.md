---
title:                "Textdatei einlesen"
date:                  2024-01-20T17:54:16.074143-07:00
model:                 gpt-4-1106-preview
simple_title:         "Textdatei einlesen"
programming_language: "Elm"
category:             "Elm"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/elm/reading-a-text-file.md"
---

{{< edit_this_page >}}

## Was & Warum?
Das Einlesen einer Textdatei ermöglicht es Programmen, Textinformationen zu verarbeiten – vom simplen Konfigurationsfile bis zur großen Datenanalyse. Programmierer nutzen das Einlesen von Textdaten, um interaktive Anwendungen zu gestalten, die auf Benutzereingaben oder Persistenz setzen.

## How to:
Elm macht direktes Einlesen von Dateien etwas anders – es verwendet hauptsächlich Ports und Subscriptions, um Dateien über JavaScript zu verarbeiten. Hier ist ein kleines Beispiel mit einem Port:

```Elm
port module Main exposing (..)

import Html exposing (Html, button, div, text)
import Html.Events exposing (onClick)

port readFile : String -> Cmd msg
port fileRead : (String -> msg) -> Sub msg

type Msg = ReadFile | FileRead String

main =
    Html.program
        { init = ( "Click to read file", Cmd.none )
        , view = view
        , update = update
        , subscriptions = \_ -> fileRead FileRead
        }

view model =
    div []
        [ button [ onClick ReadFile ] [ text "Read File" ]
        , div [] [ text model ]
        ]

update msg model =
    case msg of
        ReadFile ->
            ( model, readFile "filename.txt" )
            
        FileRead contents ->
            ( contents, Cmd.none )
```

## Deep Dive:
Historisch gesehen ist Elm stark auf Web-Anwendungen ausgerichtet, weshalb direkter Zugriff auf das Dateisystem nicht Teil des Sprachdesigns ist. Alternativ kommt man über JavaScript-Interoperabilität ans Ziel: Mit Ports sendet man Signale an JavaScript, das dann die Dateioperationen handhabt. Der Umgang mit Ports ist für side-effect-behaftete Operationen wie Dateizugriffe typisch. Das stellt sicher, dass Eure pure Funktionen rein bleiben.

## See Also:
- Elm Ports Dokumentation: [Elm Ports](https://guide.elm-lang.org/interop/ports.html)
- Ein einführender Blogpost zu Elm und Dateien: [Elm & Files Blogpost](https://elm-lang.org/news/)
