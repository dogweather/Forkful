---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:23:41.947965-07:00
description: "JSONin (JavaScript Object Notation) k\xE4sittely Haskellissa sis\xE4\
  lt\xE4\xE4 JSON-datan j\xE4sent\xE4misen Haskell-tyypeiksi ja Haskell-tyyppien muuntamisen\
  \ takaisin\u2026"
lastmod: '2024-03-13T22:44:56.635731-06:00'
model: gpt-4-0125-preview
summary: "JSONin (JavaScript Object Notation) k\xE4sittely Haskellissa sis\xE4lt\xE4\
  \xE4 JSON-datan j\xE4sent\xE4misen Haskell-tyypeiksi ja Haskell-tyyppien muuntamisen\
  \ takaisin JSONiksi."
title: "Ty\xF6skentely JSON:n kanssa"
weight: 38
---

## Miten:
Haskellissa ei ole sisäänrakennettua tukea JSONille kuten JavaScriptissä, mutta kolmannen osapuolen kirjastojen, kuten **Aesonin**, avulla JSONin käsittely muuttuu suoraviivaiseksi. Aeson tarjoaa sekä korkean tason että matalan tason funktioita koodaukseen (Haskell-arvojen muuntaminen JSONiksi) ja dekoodaukseen (JSONin jäsentäminen Haskell-arvoiksi).

### Aesonin asentaminen
Lisää ensin Aeson projektisi riippuvuuksiin päivittämällä `.cabal`-tiedostosi tai käyttämällä Stackia tai Cabalia suoraan:

```shell
cabal update && cabal install aeson
```
tai, jos käytät Stackia:
```shell
stack install aeson
```

### JSONin jäsentäminen
Aloitetaan perusesimerkillä, jossa dekoodataan JSON-data Haskell-tyypiksi. Oletetaan, että meillä on seuraava JSON henkilöstä:

```json
{
  "name": "John Doe",
  "age": 30
}
```

Määritä ensin vastaava Haskell-datatyypi ja tee siitä `FromJSON`-instanssi:

```haskell
{-# LANGUAGE DeriveGeneric #-}

import GHC.Generics (Generic)
import Data.Aeson (FromJSON, decode)
import qualified Data.ByteString.Lazy as B

data Henkilo = Henkilo
  { nimi :: String
  , ika :: Int
  } deriving (Generic, Show)

instance FromJSON Henkilo

-- Funktio JSONin dekoodaamiseksi tiedostosta
dekoodaaHenkilo :: FilePath -> IO (Maybe Henkilo)
dekoodaaHenkilo tiedostopolku = do
  henkiloJson <- B.readFile tiedostopolku
  return $ decode henkiloJson
```
Käyttö:
Olettaen, että `person.json` sisältää yllä näytetyn JSON-datan, suorita:
```haskell
main :: IO ()
main = do
  maybeHenkilo <- dekoodaaHenkilo "person.json"
  print maybeHenkilo
```
Esimerkkituloste:
```haskell
Just (Henkilo {nimi = "John Doe", ika = 30})
```

### Haskell-arvojen koodaus JSONiksi
Muuntaaksesi Haskell-arvon takaisin JSONiksi, sinun on tehtävä tyypistäsi `ToJSON`-instanssi ja sitten käytettävä `encode`-funktiota.

```haskell
import Data.Aeson (ToJSON, encode)
import GHC.Generics (Generic)

-- Olettaen aikaisemmin määritellyn Henkilo-tyypin

instance ToJSON Henkilo

koodaaHenkilo :: Henkilo -> B.ByteString
koodaaHenkilo = encode

main :: IO ()
main = do
  let henkilo = Henkilo "Jane Doe" 32
  putStrLn $ show $ koodaaHenkilo henkilo
```
Esimerkkituloste:
```json
{"nimi":"Jane Doe","ika":32}
```

Nämä esimerkit demonstroivat JSONin peruskäsittelyä Haskellissa käyttäen Aesonia. Muistathan, että Aeson tarjoaa paljon muutakin, mukaan lukien mukautetut jäsentelysäännöt, monimutkaisen sisäkkäisen JSONin käsittelyn ja paljon muuta, mikä soveltuu erilaisiin tarpeisiin ja skenaarioihin.
