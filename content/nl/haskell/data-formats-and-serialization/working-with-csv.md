---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:10:18.185528-07:00
description: "Werken met CSV (Comma-Separated Values), betekent het lezen en schrijven\
  \ van gegevens in tabelvorm. Programmeurs gebruiken CSV vanwege de eenvoud en brede\u2026"
lastmod: '2024-03-13T22:44:50.874687-06:00'
model: gpt-4-0125-preview
summary: Werken met CSV (Comma-Separated Values), betekent het lezen en schrijven
  van gegevens in tabelvorm.
title: Werken met CSV
weight: 37
---

## Hoe:
Om CSV in Haskell te hanteren, kun je de `cassava` bibliotheek gebruiken. Installeer het door `cassava` toe te voegen aan je `.cabal` bestand of door Stack te gebruiken. Hier is hoe je CSV-gegevens kunt decoderen en coderen:

```haskell
{-# LANGUAGE OverloadedStrings #-}

import Data.Csv
import qualified Data.ByteString.Lazy as BL
import qualified Data.Vector as V

-- Stel dat we met dit type werken
type Persoon = (String, Int, Bool)

-- Voorbeeld CSV-gegevens
csvData :: BL.ByteString
csvData = "John Doe,30,true\nJane Smith,25,false"

-- Decoderen van CSV-gegevens
decodeerMensen :: BL.ByteString -> Either String (V.Vector Persoon)
decodeerMensen = fmap snd . decode NoHeader

-- Gegevens coderen naar CSV
codeerMensen :: V.Vector Persoon -> BL.ByteString
codeerMensen = encode

-- Gebruiksvoorbeeld
main :: IO ()
main = do
  -- Decoderen
  case decodeerMensen csvData of
    Left err -> putStrLn err
    Right v -> print v
  
  -- Coderen
  let mensen = V.fromList [("Alice", 23, True), ("Bob", 35, False)]
  BL.putStrLn $ codeerMensen mensen
```

Voorbeelduitvoer:
```plaintext
[("John Doe",30,True),("Jane Smith",25,False)]
"Alice",23,True
"Bob",35,False
```

## Diepgaande duik
De behandeling van CSV in Haskell is geëvolueerd. De vroegste methoden omvatten handmatige tekenreeksanalyse, wat foutgevoelig was. `cassava` biedt typeveilige parsing, steunend op het sterke typesysteem van Haskell. Alternatieven omvatten het `csv` pakket, maar `cassava` is efficiënter en flexibeler. Wat de implementatie betreft, gebruikt `cassava` streams voor geheugenefficiëntie en snelheid, wat belangrijk is bij het omgaan met grote datasets.

## Zie ook
- De `cassava` bibliotheek op Hackage: https://hackage.haskell.org/package/cassava
- Haskell's ByteString bibliotheek voor het omgaan met binaire gegevens: https://hackage.haskell.org/package/bytestring
- Een gids naar de Vector bibliotheek, voor efficiënte lijsten: https://hackage.haskell.org/package/vector
