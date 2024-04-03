---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:16:49.350347-07:00
description: "S\xE4\xE4nn\xF6lliset lausekkeet (regex) ohjelmoinnissa ovat malleja,\
  \ joita k\xE4ytet\xE4\xE4n merkkiyhdistelmien vastaavuuden tarkistamiseen merkkijonoissa.\
  \ Elm:ss\xE4, kuten\u2026"
lastmod: '2024-03-13T22:44:56.478497-06:00'
model: gpt-4-0125-preview
summary: "S\xE4\xE4nn\xF6lliset lausekkeet (regex) ohjelmoinnissa ovat malleja, joita\
  \ k\xE4ytet\xE4\xE4n merkkiyhdistelmien vastaavuuden tarkistamiseen merkkijonoissa."
title: "S\xE4\xE4nn\xF6llisten lausekkeiden k\xE4ytt\xF6"
weight: 11
---

## Kuinka:
Elm ei sisällä sisäänrakennettuja regex-funktioita sen ydinkirjastossa, joten näiden operaatioiden suorittamiseen tarvitaan kolmannen osapuolen kirjastoja. Yksi suosittu valinta regexin kanssa työskentelyyn on `elm/regex`. Voit lisätä sen projektiisi käyttäen `elm install elm/regex`.

Tässä on, miten voit käyttää `elm/regex`iä muutamassa yleisessä tehtävässä:

### 1. Mallin vastaavuuden tarkistaminen
Tarkistaaksesi, vastaako merkkijono mallia, voit käyttää `Regex.contains`.

```elm
import Regex

pattern : Regex.Regex
pattern = Regex.fromString "^[a-zA-Z0-9]+$" |> Maybe.withDefault Regex.never

isAlphanumeric : String -> Bool
isAlphanumeric input = Regex.contains pattern input

-- Esimerkin käyttö:
isAlphanumeric "Elm2023"     -- Tuloste: True
isAlphanumeric "Elm 2023!"   -- Tuloste: False
```

### 2. Kaikkien vastaavuuksien löytäminen
Löytääksesi kaikki mallin esiintymät merkkijonossa, voit käyttää `Regex.find`.

```elm
matches : Regex.Regex
matches = Regex.fromString "\\b\\w+\\b" |> Maybe.withDefault Regex.never

getWords : String -> List String
getWords input = 
    input
        |> Regex.find matches
        |> List.map (.match)

-- Esimerkin käyttö:
getWords "Elm on kivaa!"  -- Output: ["Elm", "on", "kivaa"]
```

### 3. Tekstin korvaaminen
Korvataksesi osia merkkijonosta, jotka vastaavat mallia, käytä `Regex.replace`.

```elm
replacePattern : Regex.Regex
replacePattern = Regex.fromString "Elm" |> Maybe.withDefault Regex.never

replaceElmWithHaskell : String -> String
replaceElmWithHaskell input = 
    Regex.replace replacePattern (\_ -> "Haskell") input

-- Esimerkin käyttö:
replaceElmWithHaskell "Elmin oppiminen on kivaa!"  
-- Tuloste: "Haskellin oppiminen on kivaa!"
```

Näissä esimerkeissä `Regex.fromString` käytetään regex-mallin kokoamiseen, jossa `\b` vastaa sanarajoja ja `\w` vastaa mitä tahansa sanamerkkiä. Käsittele aina `Regex.fromString` tuloksena saatu `Maybe` varmistaaksesi, että et joudu invalidin regex-mallin kanssa ongelmiin, tyypillisesti käyttämällä `Maybe.withDefault`.
