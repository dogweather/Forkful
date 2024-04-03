---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:05:21.651103-07:00
description: "Merkkijonon alkukirjaimen muuttaminen isoksi kirjaimeksi samalla kun\
  \ varmistetaan, ett\xE4 loput kirjaimet pysyv\xE4t pienin\xE4, on merkkijonon p\xE4\
  \xE4omanlisointia.\u2026"
lastmod: '2024-03-13T22:44:56.599431-06:00'
model: gpt-4-0125-preview
summary: "Merkkijonon alkukirjaimen muuttaminen isoksi kirjaimeksi samalla kun varmistetaan,\
  \ ett\xE4 loput kirjaimet pysyv\xE4t pienin\xE4, on merkkijonon p\xE4\xE4omanlisointia."
title: Merkkijonon muuttaminen isoiksi kirjaimiksi
weight: 2
---

## Miten:
Haskellissa voit pääomanlisoida merkkijonon käyttämällä standardikirjastoa ilman, että tarvitset kolmannen osapuolen kirjastoja.

```haskell
import Data.Char (toUpper, toLower)

capitalize :: String -> String
capitalize "" = ""
capitalize (head:tail) = toUpper head : map toLower tail

-- Esimerkki käytöstä:
main = putStrLn $ capitalize "hello world"
```

Tuloste:
```
Hello world
```

Monimutkaisemmissa skenaarioissa tai käytön helpottamiseksi saattaisit haluta käyttää kolmannen osapuolen kirjastoa, kuten `text`, joka on suosittu tehokkaaseen merkkijonon käsittelyyn Haskellissa.

Ensin sinun täytyy lisätä `text` projektisi riippuvuuksiin. Sen jälkeen voit käyttää sen funktioita pääomanlisoimaan merkkijonon seuraavasti:

```haskell
import qualified Data.Text as T
import Data.Char (toUpper)

capitalizeText :: T.Text -> T.Text
capitalizeText text = case T.uncons text of
    Nothing -> T.empty
    Just (first, rest) -> T.cons (toUpper first) (T.toLower rest)

-- Esimerkki käytöstä text-kirjaston kanssa:
main = putStrLn $ T.unpack $ capitalizeText (T.pack "hello world")
```

Tuloste:
```
Hello world
```

Molemmat näistä esimerkeistä osoittavat yksinkertaisia, mutta tehokkaita tapoja pääomanlisoida merkkijono Haskellissa, kolmannen osapuolen kirjastojen kanssa tai ilman.
