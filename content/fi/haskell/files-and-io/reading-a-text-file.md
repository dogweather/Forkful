---
date: 2024-01-20 17:54:20.714393-07:00
description: "Tekstin lukeminen tiedostosta on yksinkertaisesti tiedon hakemista levylt\xE4\
  . Ohjelmoijat tekev\xE4t t\xE4t\xE4 datan k\xE4sittelyn, analysoinnin tai tulosten\u2026"
lastmod: '2024-03-13T22:44:56.631912-06:00'
model: gpt-4-1106-preview
summary: "Tekstin lukeminen tiedostosta on yksinkertaisesti tiedon hakemista levylt\xE4\
  ."
title: Tekstitiedoston lukeminen
weight: 22
---

## How to:
```haskell
import System.IO

-- Tiedoston lukeminen rivillesi
main = do
    fileHandle <- openFile "esimerkki.txt" ReadMode
    contents <- hGetContents fileHandle
    putStr contents
    hClose fileHandle

-- Toisaalta, käytämme 'readFile' funktiota (helppo tapa):
mainLueHelppo = do
    contents <- readFile "esimerkki.txt"
    putStr contents

-- Yksinkertainen tapa luetella tiedoston rivit:
mainRivit = do
    contents <- readFile "esimerkki.txt"
    let rivit = lines contents
    mapM_ putStrLn rivit
```
Odotettu tuloste:
```
Moi, tämä on tiedosto esimerkki.
Tässä on toinen rivi.
```

## Deep Dive
Tekstitiedostojen käsittely on oleellista monille sovelluksille. Historiassa tiedostonkäsittelyyn käytettiin alhaisen tason IO-operaatioita C:ssä. Haskellissa se yksinkertaistui funktioiden, kuten `readFile` ja `hGetContents`, myötä.

Vaihtoehtoisesti voit käyttää `ByteString` tai `Text` kirjastoa, jotka käsittävät suuren datamäärän tehokkaammin kuin perinteiset `String`:it.

Kun avaat tiedoston, muista aina sulkea se. Tämä vapauttaa resurssit. `withFile` funktio hoitaa tämän automaattisesti.

## See Also
- [Real World Haskell, Chapter 7](http://book.realworldhaskell.org/read/io.html)
- [Hackage: ByteString package](https://hackage.haskell.org/package/bytestring)
