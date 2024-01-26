---
title:                "Webseite herunterladen"
date:                  2024-01-20T17:43:48.061787-07:00
model:                 gpt-4-1106-preview
simple_title:         "Webseite herunterladen"
programming_language: "Elm"
category:             "Elm"
tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/de/elm/downloading-a-web-page.md"
---

{{< edit_this_page >}}

## What & Why?
Webseiten herunterzuladen bedeutet, Anfragen an einen Server zu senden, um eine HTML-Seite zu erhalten. Programmierer machen das, um Daten zu sammeln, Inhalte offline zu nutzen oder Webservices zu integrieren.

## How to:
Elm verwendet `Http`-Pakete für Webanfragen. Hier ist ein einfaches Beispiel, um eine Webseite herunterzuladen:

```Elm
import Http
import Html exposing (Html, text)

type Msg = ReceivePage String

getPage : Cmd Msg
getPage =
    Http.get
        { url = "https://example.com"
        , expect = Http.expectString ReceivePage
        }

view : String -> Html Msg
view content =
    text content

main =
    Html.program
        { init = ("", getPage)
        , view = view
        , update = \_ model -> (model, Cmd.none)
        , subscriptions = \_ -> Sub.none
        }
```

Ausgabe:

```
<!doctype html>
<html>
<head>
    <title>Example Domain</title>
...
</html>
```

## Deep Dive
Elm machte Webanfragen einfacher und sicherer durch sein starkes Typensystem und Unveränderlichkeit. Historisch gesehen basierten Webanfragen auf Callbacks und Promises in Javascript. Elm benutzt stattdessen ein `Http`-Modul mit einer sauberen API. Alternativen zu Elm's Ansatz sind direkte AJAX Aufrufe in Javascript oder die Verwendung von Libraries wie Axios oder Fetch.

Für das Herunterladen von Webseiten enkapsuliert das `Http`-Modul alle notwendigen Schritte und behandelt sie in einer mehr deklarativen Art und Weise. Fehlerbehandlung wird durch das Typsystem erzwungen, was zu weniger Laufzeitfehlern führt.

Elm's `Cmd` ermöglicht es, Nebeneffekte wie HTTP-Anfragen zu managen, indem es beschreibt, was getan werden soll, anstatt wie es getan wird. Dies vereinfacht das Fehlermanagement und fördert reaktive Anwendungsarchitekturen.

## See Also
- Elm Http Dokumentation: [https://package.elm-lang.org/packages/elm/http/latest/](https://package.elm-lang.org/packages/elm/http/latest/)
- Elm Lang Guide zu Effekten: [https://guide.elm-lang.org/effects/](https://guide.elm-lang.org/effects/)
- JSON Decoding in Elm: [https://guide.elm-lang.org/effects/json.html](https://guide.elm-lang.org/effects/json.html)
