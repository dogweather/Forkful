---
aliases:
- /fi/elm/sending-an-http-request/
date: 2024-01-20 17:59:23.247905-07:00
description: "HTTP-pyynn\xF6n l\xE4hett\xE4minen on tiedon pyyt\xE4mist\xE4 palvelimelta.\
  \ Ohjelmoijat tekev\xE4t sen, koska heid\xE4n sovelluksensa tarvitsevat tietoa p\xE4\
  ivitty\xE4kseen tai\u2026"
lastmod: 2024-02-18 23:09:07.500182
model: gpt-4-1106-preview
summary: "HTTP-pyynn\xF6n l\xE4hett\xE4minen on tiedon pyyt\xE4mist\xE4 palvelimelta.\
  \ Ohjelmoijat tekev\xE4t sen, koska heid\xE4n sovelluksensa tarvitsevat tietoa p\xE4\
  ivitty\xE4kseen tai\u2026"
title: "HTTP-pyynn\xF6n l\xE4hett\xE4minen"
---

{{< edit_this_page >}}

## What & Why? (Mikä & Miksi?)
HTTP-pyynnön lähettäminen on tiedon pyytämistä palvelimelta. Ohjelmoijat tekevät sen, koska heidän sovelluksensa tarvitsevat tietoa päivittyäkseen tai käsitelläkseen käyttäjän pyyntöjä.

## How to: (Kuinka tehdä:)
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

getUser : Cmd Msg
getUser =
  Http.get
    { url = "https://api.example.com/users/1"
    , decoder = userDecoder
    }
```
Kun suoritat tämän, saat käyttäjän tiedot, jos kaikki menee hyvin: `{ id = 1, name = "Alice" }`.

## Deep Dive (Syväsukellus)
HTTP-pyynnöt ovat nettisovellusten selkäranka. Historiassa käytettiin pääasiassa vain XMLHttpReqest-objektia, mutta Elm tarjoaa yksinkertaistetun HTTP-moduulin, joka kapseloi monimutkaisuuden ja keskittyy puhtaaseen toiminnallisuuteen. Elmissä kaikki HTTP-pyynnöt käsitellään komentoina (Cmd), jotka seuraavat sovelluksen tilan puhtaiden päivitysten mallia. Vaihtoehtoisesti voit käyttää WebSocketsia reaaliaikaiseen viestintään. Elm 0.19 version myötä, Json.Decode-moduulin käyttö on tehty helpommaksi tietojen jäsentämiseksi.

## See Also (Katso Myös)
- Elm HTTP package documentation: [https://package.elm-lang.org/packages/elm/http/latest/](https://package.elm-lang.org/packages/elm/http/latest/)
- JSON Decoding in Elm: [https://guide.elm-lang.org/effects/json.html](https://guide.elm-lang.org/effects/json.html)
- Elm Lang Official Guide (HTTP Requests): [https://guide.elm-lang.org/effects/http.html](https://guide.elm-lang.org/effects/http.html)
