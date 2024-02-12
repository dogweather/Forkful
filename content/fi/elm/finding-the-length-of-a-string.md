---
title:                "Merkkijonon pituuden selvittäminen"
aliases:
- fi/elm/finding-the-length-of-a-string.md
date:                  2024-01-20T17:47:31.205422-07:00
model:                 gpt-4-1106-preview
simple_title:         "Merkkijonon pituuden selvittäminen"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/elm/finding-the-length-of-a-string.md"
---

{{< edit_this_page >}}

## What & Why? (Mitä & Miksi?)
Stringin pituuden selvittäminen tarkoittaa merkkijonossa olevien merkkien lukumäärän laskemista. Ohjelmoijat tekevät tätä, jotta saavat tietää tietorakenteiden koot, validoi syötteen tai manipuloi tekstiä esimerkiksi näytölle sopivaksi.

## How to: (Kuinka tehdä:)
Elm tarjoaa `String.length` funktion, joka ottaa merkkijonon (`String`) ja palauttaa pituuden (`Int`):

```Elm
import Html exposing (text)

main =
    text (String.fromInt (String.length "Hei Suomi!"))

-- Tulos on näyttöruudulla: 10
```

Tässä tapauksessa me muunnamme pituuden numerosta (`Int`) merkkijonoksi funktion `String.fromInt` avulla, jotta voimme näyttää sen nettisivulla.

## Deep Dive (Syvä sukellus)
Stringien pituuden laskeminen on perustavanlaatuinen ohjelmoinnin konsepti, mikä on ollut mukana ohjelmointikielissä pitemmän aikaa. Elm, kuten moni muukin funktionaalinen kieli, toimii immutaabelien merkkijonojen kanssa. Tämä tarkoittaa, että kun lasket stringin pituutta, et muuta alkuperäistä merkkijonoa.

Vaihtoehtoisia tapoja selvittää stringin pituutta Elmissä ei periaatteessa ole, koska Elm pyrkii yksinkertaiseen ja selkeään API:in. Tämä auttaa ohjelmoijia välttämään virheitä ja sekaannusta.

Stringin pituuden laskenta on suoraviivaista, mutta yksi yksityiskohta on tärkeä: Elm käsittelee UniCode-merkkejä oikeaoppisesti. Tämä tarkoittaa, että jos stringissäsi on esimerkiksi emoji, se lasketaan yhdeksi merkiksi sen teknisestä toteutuksesta huolimatta.

## See Also (Katso myös)
- Elm `String` moduulin dokumentaatio: [Elm String docs](http://package.elm-lang.org/packages/elm/core/latest/String)
- Unicode standardi ja merkkien käsittely: [Unicode Consortium](https://home.unicode.org/)
- Elm-yhteisön keskustelut ja ohjeet merkkijonojen käsittelystä: [Elm Discourse](https://discourse.elm-lang.org/)
