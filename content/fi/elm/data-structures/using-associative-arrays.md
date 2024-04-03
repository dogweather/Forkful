---
changelog:
- 2024-01-30, gpt-4-0125-preview, translated from English
date: 2024-01-30 19:10:55.674921-07:00
description: "Assosiatiiviset taulukot, tai kuten Elm kutsuu niit\xE4, Sanakirjat,\
  \ kartoittavat avaimet arvoihin tavalla, joka tekee arvojen hakemisesta, lis\xE4\
  \xE4misest\xE4 ja\u2026"
lastmod: '2024-03-13T22:44:56.481473-06:00'
model: gpt-4-0125-preview
summary: "Assosiatiiviset taulukot, tai kuten Elm kutsuu niit\xE4, Sanakirjat, kartoittavat\
  \ avaimet arvoihin tavalla, joka tekee arvojen hakemisesta, lis\xE4\xE4misest\xE4\
  \ ja poistosta eritt\xE4in nopeaa."
title: "Assosiatiivisten taulukoiden k\xE4ytt\xF6"
weight: 15
---

## Kuinka:
Elmissä työskentelet Sanakirjojen kanssa `Dict` moduulissa, joten sukellamme nopeasti esimerkkiin:

```Elm
import Dict exposing (Dict)

-- Alustetaan sanakirja, jossa on String-avaimet ja Int-arvot
exampleDict : Dict String Int
exampleDict = Dict.fromList [("apple", 5), ("banana", 2), ("orange", 8)]

-- Arvon lisääminen tai päivittäminen
updatedDict = Dict.insert "grape" 10 exampleDict

-- Arvon hakeminen (huomaa Maybe-tyyppi, koska avainta ei välttämättä ole)
fruitCount : Maybe Int
fruitCount = Dict.get "apple" updatedDict

-- Avain-arvo -parin poistaminen
finalDict = Dict.remove "banana" updatedDict

-- Muunnetaan sanakirja takaisin listaksi
dictToList = Dict.toList finalDict
```

Esimerkkitulostus, kun näytetään `dictToList`:

```Elm
[("apple", 5), ("grape", 10), ("orange", 8)]
```

Tämä osoittaa perusoperaatiot: luomisen, päivittämisen, käyttämisen ja iteroimisen Sanakirjan yli.

## Syväsukellus
Elmin Sanakirjat sisäisesti käyttävät rakennetta, joka tunnetaan nimellä AVL-puu - tyyppi itseään tasapainottava binäärihakupuu. Tämä valinta löytää tasapainon varmistamalla, että operaatiot kuten insert, get ja remove ovat hyvän suorituskyvyn omaavia (logaritminen aikavaativuus) ja ylläpitävät yksinkertaisuutta datan käsittelyssä.

Elmin `Dict` vahvuuksista huolimatta, se ei ole kaikille kokoelmatyypeille sopiva ratkaisu. Järjestetyille kokoelmille tai sellaisille, jotka täytyy iteroida peräkkäin, Lista tai Taulukko saattaisi olla sopivampi. Lisäksi, kun työskennellään kiinteän joukon tunnettujen avainten kanssa, käyttäjän määrittelemät tyypit (Elmin versio enumeraatioista) voivat tarjota enemmän tyyppiturvallisuutta ja selvempiä aikomuksia koodissasi.

Elmin ekosysteemissä `Dict` tarjoaa luotettavan tavan hallita avain-arvo -pareja kokoelmia, joissa avaimet ovat uniikkeja ja järjestyksellä ei ole merkitystä. Vaikka uudempia tai kehittyneempiä rakenteita voi ilmestyä, `Dict` moduuli pysyy perustyökaluna Elm-ohjelmoijan työkalupakissa sen yksinkertaisuuden ja tehokkuuden vuoksi assosiatiivisten taulukoiden käsittelyssä.
