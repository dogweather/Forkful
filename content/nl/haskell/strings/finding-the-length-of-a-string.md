---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 22:00:15.439252-07:00
description: "De lengte van een string vinden in Haskell betekent bepalen hoeveel\
  \ karakters deze bevat. Programmeurs hebben dit vaak nodig om lusiteratoren te\u2026"
lastmod: '2024-03-13T22:44:50.843168-06:00'
model: gpt-4-0125-preview
summary: De lengte van een string vinden in Haskell betekent bepalen hoeveel karakters
  deze bevat.
title: De lengte van een string vinden
weight: 7
---

## Hoe te:
```Haskell
-- Gebruik makend van de `length` functie
main = do
    let myString = "Hallo, Haskell!"
    print $ length myString
```

Voorbeelduitvoer:
```
15
```

## Diepere Duik
Haskell is een puur functionele taal waar strings worden weergegeven als lijsten van karakters. De `length` functie, onderdeel van de Prelude (de standaardbibliotheek die in elk Haskell-programma wordt geïmporteerd), werkt onder deze weergave.

Historisch gezien waren strings als lijsten een natuurlijke keuze voor Haskell vanwege hun eenvoud en het feit dat Lisp een vergelijkbare ontwerpkeuze maakte (en veel functionele talen beïnvloedde). De `length` functie telt gewoon de elementen in deze lijst.

Echter, `length` is O(n), wat betekent dat de functie tijd zal nemen die evenredig is aan de lengte van de string. Dit is geen probleem voor korte strings, maar voor lange kan het inefficiënt zijn.

Alternatieven zijn onder andere:
- Gebruik maken van `Text` uit het `text` pakket, een efficiëntere structuur voor Unicode-tekst.
- Gebruik maken van `ByteString` uit het `bytestring` pakket voor binaire of ASCII-gegevens.

Beiden bieden een `length` functie geoptimaliseerd voor hun respectieve datastructuren.

Wat betreft de implementatie kan een basisversie van de `length` functie er zo uitzien:

```Haskell
myLength :: [a] -> Int
myLength [] = 0          -- De lengte van een lege lijst is 0
myLength (_:xs) = 1 + myLength xs  -- Recursief 1 optellen voor de rest van de lijst
```

Voor `Text` en `ByteString` gegevenstypes hebben ze hun eigen interne implementatiedetails die ze efficiënter maken dan een simpele gelinkte lijst van karakters.

## Zie Ook
- [Haskell `length` officiële documentatie](https://hackage.haskell.org/package/base-4.16.1.0/docs/Prelude.html#v:length)
- [`text` pakket op Hackage](https://hackage.haskell.org/package/text)
- [`bytestring` pakket op Hackage](https://hackage.haskell.org/package/bytestring)
- [Learn You a Haskell for Great Good! (Een introductieboek)](http://learnyouahaskell.com/chapters)
