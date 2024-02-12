---
title:                "Envoi d'une requête HTTP"
aliases:
- fr/elm/sending-an-http-request.md
date:                  2024-01-20T17:59:20.915027-07:00
model:                 gpt-4-1106-preview
simple_title:         "Envoi d'une requête HTTP"

tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/elm/sending-an-http-request.md"
---

{{< edit_this_page >}}

## What & Why? (Quoi et Pourquoi ?)
Envoyer une requête HTTP, c’est demander des données à un serveur web. Les programmeurs le font pour récupérer des données extérieures, comme des infos météo ou des posts de blog.

## How to: (Comment faire :)
```Elm
import Http
import Json.Decode as Decode

type alias User =
    { id : Int
    , name : String
    }

userDecoder : Decode.Decoder User
userDecoder =
    Decode.map2 User
        (Decode.field "id" Decode.int)
        (Decode.field "name" Decode.string)

fetchUser : Int -> Cmd Msg
fetchUser userId =
    Http.get
        { url = "https://api.example.com/users/" ++ String.fromInt(userId)
        , decoder = userDecoder
        }
        |> Http.send UserFetched

type Msg
    = UserFetched (Result Http.Error User)

update : Msg -> Model -> (Model, Cmd Msg)
update msg model =
    case msg of
        UserFetched (Ok user) ->
            ({ model | user = Just user }, Cmd.none)

        UserFetched (Err _) ->
            (model, Cmd.none)
```

## Deep Dive (Plongée en profondeur)
Historiquement, Elm a rendu les requêtes HTTP plus sûres en utilisant The Elm Architecture, qui gère les effets de bord de façon prévisible. Côté alternatives, on pourrait regarder vers des packages comme `elm-http-builder` pour une plus grande flexibilité. En coulisses, Elm utilise des commandes pour déclencher des requêtes HTTP, évitant ainsi les effets de bord aléatoires et garantissant un flux de données unidirectionnel.

## See Also (Voir aussi)
- Documentation officielle sur HTTP en Elm : [Elm HTTP](https://package.elm-lang.org/packages/elm/http/latest/)
- JSON Decoder : [Elm JSON Decode Pipeline](https://package.elm-lang.org/packages/NoRedInk/elm-json-decode-pipeline/latest)
- Handling HTTP in Elm : [Elm Guide - HTTP](https://guide.elm-lang.org/effects/http.html)
