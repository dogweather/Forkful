---
aliases:
- /es/elm/sending-an-http-request-with-basic-authentication/
date: 2024-01-20 18:01:40.211579-07:00
description: "Enviar una petici\xF3n HTTP con autenticaci\xF3n b\xE1sica significa\
  \ incluir credenciales de usuario para acceder a recursos protegidos. Los programadores\
  \ lo hacen\u2026"
lastmod: 2024-02-18 23:09:09.890425
model: gpt-4-1106-preview
summary: "Enviar una petici\xF3n HTTP con autenticaci\xF3n b\xE1sica significa incluir\
  \ credenciales de usuario para acceder a recursos protegidos. Los programadores\
  \ lo hacen\u2026"
title: "Enviando una solicitud http con autenticaci\xF3n b\xE1sica"
---

{{< edit_this_page >}}

## ¿Qué y Por Qué?
Enviar una petición HTTP con autenticación básica significa incluir credenciales de usuario para acceder a recursos protegidos. Los programadores lo hacen para interactuar con servidores y APIs que requieren una capa extra de seguridad.

## Cómo Hacerlo:
```Elm
import Http
import Base64

type alias Model =
    { response : String }

type Msg
    = GotData (Result Http.Error String)

basicAuthHeader : String -> String -> Http.Header
basicAuthHeader username password =
    let
        encodedCredentials =
            Base64.encode (username ++ ":" ++ password)
    in
    Http.header "Authorization" ("Basic " ++ encodedCredentials)

sendRequest : Cmd Msg
sendRequest =
    Http.request
        { method = "GET"
        , headers = [ basicAuthHeader "your-username" "your-password" ]
        , url = "https://example.com/protected-resource"
        , body = Http.emptyBody
        , expect = Http.expectString GotData
        , timeout = Nothing
        , tracker = Nothing
        }

update : Msg -> Model -> ( Model, Cmd Msg )
update msg model =
  case msg of
    GotData (Ok data) ->
      ( { model | response = data }, Cmd.none )

    GotData (Err error) ->
      ( { model | response = "An error occurred" }, Cmd.none )
```

## Inmersión Profunda:
Enviar una petición HTTP con autenticación básica no es concepto nuevo; existe desde los primeros días de la web para proteger contra accesos no autorizados. Alternativas modernas como la autenticación de token, OAuth, y JWT se han vuelto populares por ofrecer más seguridad y flexibilidad. Sin embargo, para algunos casos simples y controlados, la autenticación básica aún se utiliza. En Elm, esto implica codificar las credenciales en base64 y agregarlas al encabezado 'Authorization' de nuestras peticiones HTTP.

## Ver También:
- Elm HTTP package documentation: [Elm HTTP](https://package.elm-lang.org/packages/elm/http/latest/)
- Base64 encoding for credentials: [Base64 Elm Package](https://package.elm-lang.org/packages/truqu/elm-base64/latest/)
- HTTP authentication methods overview: [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication)
