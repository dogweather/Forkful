---
aliases:
- /pl/elm/downloading-a-web-page/
date: 2024-01-20 17:43:48.546941-07:00
description: "Pobranie strony internetowej to proces \u015Bci\u0105gania tre\u015B\
  ci ze zdalnego serwera. Programi\u015Bci robi\u0105 to, aby przetwarza\u0107 dane,\
  \ pobiera\u0107 aktualizacje lub\u2026"
lastmod: 2024-02-18 23:08:49.517747
model: gpt-4-1106-preview
summary: "Pobranie strony internetowej to proces \u015Bci\u0105gania tre\u015Bci ze\
  \ zdalnego serwera. Programi\u015Bci robi\u0105 to, aby przetwarza\u0107 dane, pobiera\u0107\
  \ aktualizacje lub\u2026"
title: Pobieranie strony internetowej
---

{{< edit_this_page >}}

## What & Why? (Co i Dlaczego?)
Pobranie strony internetowej to proces ściągania treści ze zdalnego serwera. Programiści robią to, aby przetwarzać dane, pobierać aktualizacje lub wypełniać aplikacje treścią.

## How to: (Jak to zrobić:)
W Elm downloadowanie strony może być wykonane za pomocą modułu `Http`. Oto przykład prostego żądania GET:

```Elm
import Http
import Json.Decode exposing (string)

type Msg
    = GotText (Result Http.Error String)

getText : Cmd Msg
getText =
    Http.get
        { url = "http://example.com"
        , expect = Http.expectString GotText
        }

-- To jest wywołane, gdy odpowiedź przychodzi
update : Msg -> Model -> (Model, Cmd Msg)
update msg model =
    case msg of
        GotText (Ok text) ->
            -- zrób coś z pobranym tekstem
            (model, Cmd.none)

        GotText (Err httpError) ->
            -- obsłuż błąd
            (model, Cmd.none)
```

Sample output może wyglądać tak:
```Elm
-- W przypadku sukcesu:
GotText (Ok "Tutaj treść strony...")

-- W przypadku błędu:
GotText (Err Http.NetworkError)
```

## Deep Dive (Dogłębna analiza)
W przeszłości Elm wykorzystywał `elm-lang/http`, ale obecnie używa się `elm/http` jako standardowego modułu do żądań HTTP. Alternatywą dla wbudowanych funkcji HTTP jest korzystanie z JavaScript'u poprzez porty.

Szczegóły implementacji to:
- Użycie `Http.expectString`, by zinterpretować odpowiedź jako tekst.
- Dekodowanie JSON za pomocą `Json.Decode` dla uzyskania bardziej złożonych typów danych.
- Bezpieczne obsługiwanie błędów poprzez typ `Result`.

Programowanie w Elm skupia się na czystości funkcji i niezmienności, co sprzyja tworzeniu przewidywalnych aplikacji webowych.

## See Also (Zobacz również)
- [Elm HTTP package documentation](https://package.elm-lang.org/packages/elm/http/latest/)
- [Elm Guide on HTTP](https://guide.elm-lang.org/effects/http.html)
- [Json.Decode API Documentation](https://package.elm-lang.org/packages/elm/json/latest/Json-Decode)
