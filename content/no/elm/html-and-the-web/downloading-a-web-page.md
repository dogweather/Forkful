---
title:                "Nedlasting av en nettside"
aliases:
- no/elm/downloading-a-web-page.md
date:                  2024-01-20T17:43:52.578068-07:00
model:                 gpt-4-1106-preview
simple_title:         "Nedlasting av en nettside"

tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/no/elm/downloading-a-web-page.md"
---

{{< edit_this_page >}}

## Hva & Hvorfor?
Å laste ned en nettside er prosessen med å hente innholdet til en nettside via internett, slik at du kan se eller bearbeide det i et program. Programmerere gjør dette for å samle data, integrere funksjoner fra andre nettsteder, og automatisere oppgaver som ellers ville vært manuelle.

## Hvordan gjør man det:
Elm gjør bruk av `Http` for å laste ned nettsider. Her er et grunnleggende eksempel:

```Elm
import Http
import Html exposing (Html, div, text)
import Json.Decode exposing (string)

type Msg = GotText String | FetchFail Http.Error

fetch : Cmd Msg
fetch =
    Http.get { url = "https://example.com", expect = Http.expectString GotText FetchFail }

view : String -> Html Msg
view content =
    div [] [ text content ]

-- Husk å håndtere Msg i update-funksjonen for å oppdatere view
```

Eksempel på output:
```
<!doctype html>
<html>
<head>
    <title>Example Domain</title>
...
```

## Dypdykk
Elm's `Http`-bibliotek gjør det brukervennlig å laste ned webinnhold på en typesikker måte. Tidligere brukte man kanskje JavaScript med XMLHttpRequest eller fetch API, men Elm gir et renere og sikrere alternativ. Man må håndtere JSON-dekoding selv inspirert av Elm's tanke om at man skal jobbe eksplisitt med typesikkerhet. Alternativt kan man også se på tredjeparts biblioteker som tillater mer kompleks interaksjon med HTTP-klienter i Elm.

## Se Også:
- Elm Http-pakken: https://package.elm-lang.org/packages/elm/http/latest/
- Elm JSON guide: https://guide.elm-lang.org/effects/json.html
- Elm offisiell guide for å sende HTTP-forespørsler: https://guide.elm-lang.org/effects/http.html
