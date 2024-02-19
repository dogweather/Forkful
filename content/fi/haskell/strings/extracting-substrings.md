---
aliases:
- /fi/haskell/extracting-substrings/
date: 2024-01-20 17:46:05.335070-07:00
description: "Subjonojen poiminta tarkoittaa merkkijonon osien irrottamista. Ohjelmoijat\
  \ tekev\xE4t sit\xE4, kun tarvitsevat k\xE4sitell\xE4 merkkijonojen erityisi\xE4\
  \ segmenttej\xE4 \u2013\u2026"
lastmod: 2024-02-18 23:09:07.654666
model: gpt-4-1106-preview
summary: "Subjonojen poiminta tarkoittaa merkkijonon osien irrottamista. Ohjelmoijat\
  \ tekev\xE4t sit\xE4, kun tarvitsevat k\xE4sitell\xE4 merkkijonojen erityisi\xE4\
  \ segmenttej\xE4 \u2013\u2026"
title: Merkkijonojen osien poimiminen
---

{{< edit_this_page >}}

## What & Why?
Subjonojen poiminta tarkoittaa merkkijonon osien irrottamista. Ohjelmoijat tekevät sitä, kun tarvitsevat käsitellä merkkijonojen erityisiä segmenttejä – kuten tietojen siistimistä tai merkkijonon analysointia.

## How to:
Haskellissa käytetään usein funktioita `take`, `drop` ja `substring` merkkijonorakenteiden käsittelyyn. Tässä pari esimerkkiä:

```Haskell
import Data.List

-- Otetaan merkkijonon alusta 5 merkkiä
takeExample :: String -> String
takeExample = take 5

-- Poistetaan alusta 5 merkkiä
dropExample :: String -> String
dropExample = drop 5

-- Otetaan merkkijonosta alkaen kolmas merkki ja otetaan 5 merkkiä
substringExample :: String -> String
substringExample = take 5 . drop 2

-- Esimerkkien käyttö:
main :: IO ()
main = do
  let testString = "Moikka maailma!"
  putStrLn $ takeExample testString      -- Tulostuu "Moikk"
  putStrLn $ dropExample testString      -- Tulostuu "maailma!"
  putStrLn $ substringExample testString -- Tulostuu "ikka "
```

## Deep Dive
Haskellin funktiot `take` ja `drop` ovat peräisin funktionaalisen ohjelmoinnin maailmasta ja ne ovat olleet kielessä sen alkuaikoina. Substring-toiminnallisuudelle ei ole vakioratkaisua, mutta edellä esitetyt funktiot tekevät työn hyvin. Nämä funktiot toimivat 'lazy evaluation' periaatteella, mikä on tehokasta isojen datasettien kanssa.

Vaihtoehtoina on kirjastoja kuten `text` ja `bytestring`, jotka tarjoavat tehokkaampia työkaluja, kun työstetään suuria tekstiaineistoja. Suorituskyky syistä, näiden kirjastojen käyttäminen voi olla fiksumpaa, jos sovellus käsittelee paljon dataa.

Haskellissa voit myös toteuttaa substring-funktion itse, mikä antaa lisää joustavuutta ja voi olla opettavaista, erityisesti jos haluat ymmärtää miten Haskellissa työskennellään listojen ja rekursiivisten funktioiden kanssa.

## See Also
- Haskell Wiki: [https://wiki.haskell.org](https://wiki.haskell.org/Introduction)
- "Learn You a Haskell for Great Good!" online-kirja: [http://learnyouahaskell.com](http://learnyouahaskell.com/)
- `text` kirjaston dokumentaatio: [https://hackage.haskell.org/package/text](https://hackage.haskell.org/package/text)
- `bytestring` kirjaston dokumentaatio: [https://hackage.haskell.org/package/bytestring](https://hackage.haskell.org/package/bytestring)
