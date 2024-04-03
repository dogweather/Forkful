---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 21:59:01.024352-07:00
description: "Een webpagina downloaden betekent het ophalen van de gegevens via het\
  \ internet; het is alsof je een kopie opslaat om lokaal te lezen of te verwerken.\u2026"
lastmod: '2024-03-13T22:44:50.851031-06:00'
model: gpt-4-0125-preview
summary: Een webpagina downloaden betekent het ophalen van de gegevens via het internet;
  het is alsof je een kopie opslaat om lokaal te lezen of te verwerken.
title: Een webpagina downloaden
weight: 42
---

## Hoe:
Laten we beginnen met een eenvoudig voorbeeld waarin we gebruik maken van de `http-conduit` bibliotheek van Haskell. Installeer het eerst met `cabal install http-conduit`. Dan:

```Haskell
import Network.HTTP.Conduit -- De belangrijkste netwerkbibliotheek
import qualified Data.ByteString.Lazy as L -- We hebben Lazy ByteStrings nodig

-- Functie om een webpagina te downloaden
downloadPage :: String -> IO L.ByteString
downloadPage url = simpleHttp url

main :: IO ()
main = do
    -- Gebruik de functie om een pagina te downloaden
    content <- downloadPage "http://example.com"
    -- Doe iets met de inhoud, zoals het printen
    L.putStr content
```

Bij het uitvoeren hiervan zie je de HTML van `http://example.com` op je scherm.

## Diepgaand
HTTP-verzoeken in Haskell zijn niet altijd zo netjes geweest. Oudere bibliotheken zoals `HTTP` vereisten meer boilerplate code. Met `http-conduit` wordt de complexiteit weggeabstraheerd.

Er bestaan andere methoden, zoals het `wget` commando in een shell-script of de `requests` bibliotheek in Python. Maar deze zijn niet altijd zo efficiënt of expressief in de functionele setting van Haskell.

Onder de motorkap gebruikt `http-conduit` een Manager om verbinding pooling en Keep-Alive voor HTTP1.1 te beheren, waardoor het efficiënter is voor meerdere verzoeken.

## Zie Ook
- Voor geavanceerder gebruik van `http-conduit`: [http-conduit op Hackage](https://hackage.haskell.org/package/http-conduit)
- Om ByteString te begrijpen: [ByteString op Hackage](https://hackage.haskell.org/package/bytestring)
