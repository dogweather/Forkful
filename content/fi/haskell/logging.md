---
title:                "Lokitus"
date:                  2024-01-26T01:07:04.110977-07:00
model:                 gpt-4-1106-preview
simple_title:         "Lokitus"
programming_language: "Haskell"
category:             "Haskell"
tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/haskell/logging.md"
---

{{< edit_this_page >}}

## Mikä & Miksi?
Ohjelmoinnissa lokitus tarkoittaa käytännössä murusten jättämistä jälkeensa tapahtumien tai viestien muodossa, jotka auttavat seuraamaan, mitä sovelluksessasi tapahtuu milloinkin. Ohjelmoijat tekevät sitä vikojen jäljitykseen, järjestelmän suorituskyvyn valvontaan sekä turvallisuuden ja vaatimustenmukaisuuden seurantaan.

## Kuinka:
Haskellissa lokituksen voi toteuttaa käyttämällä kirjastoja kuten `monad-logger` tai `hslogger`. Tässä pikainen esimerkki käyttäen `monad-logger`-kirjastoa:

```Haskell
{-# LANGUAGE OverloadedStrings #-}

import Control.Monad.Logger
import Control.Monad.IO.Class (liftIO)

logExample :: LoggingT IO ()
logExample = do
    logInfoN "Sovelluksen käynnistäminen..."
    liftIO $ putStrLn "Tehdään jotain kriittistä työtä..."
    logErrorN "Hups! Jokin meni vikaan."

main :: IO ()
main = runStdoutLoggingT logExample

{- Esimerkkituloste
[Info] Sovelluksen käynnistäminen...
Tehdään jotain kriittistä työtä...
[Error] Hups! Jokin meni vikaan.
-}
```

Tämä yksinkertainen esimerkki osoittaa, kuinka voit ripotella lokiviestejä koodiisi saadaksesi tietoa siitä, mitä suoritusajalla tapahtuu. `logInfoN` ja `logErrorN` käytetään tiedotteiden ja virheviestien lokittamiseen vastaavasti.

## Syväluotaus:
Lokitus on kehittynyt yksinkertaisista tulostuskäskyistä monimutkaisiin lokitusjärjestelmiin. Historiallisesti lokit olivat pelkkiä tekstiulosteita konsoliin tai tiedostoon, mutta nykyään ne sisältävät rakenteistettua dataa, jota voidaan jäsentää ja analysoida eri työkaluilla.

Haskellissa lokitusta voidaan suorittaa puhtaassa funktionaalisessa tyylissä, johon sisältyy loki-toimintojen eksplisiittinen välittäminen tai impuurissa monadikonteksteissa, joissa lokittajat kudotaan implisiittisesti laskennan läpi.

Esimerkiksi `hslogger`-kirjasto on perinteisempi ja muuttuvampi verrattuna `monad-logger`iin. `monad-logger` tarjoaa integraatiota monadipinoon ja tarjoaa lisää joustavuutta ulostulomuotoilun ja kontrollin suhteen. Molemmat kirjastot sallivat lokitasojen asettamisen, joiden avulla voi suodattaa lokiviestejä niiden tärkeyden mukaan. Lokitasoihin kuuluvat debug, info, notice, warning, error, critical, alert ja emergency.

Haskellin lähestymistapa lokitukseen usein vastaa sen tyyppiturvallisuuden ja puhtauden korostusta. Lokit voidaan käsitellä siten, että vaikka lokitus epäonnistuisi, se ei kaada pääsovellusta, ansiosta Haskellin vankkumattomista virheenkäsittelykyvyistä.

## Katso Myös:
- [`monad-logger` dokumentaatio Hackage-sivustolla](https://hackage.haskell.org/package/monad-logger)
- [`hslogger` paketti Hackage-sivustolla](https://hackage.haskell.org/package/hslogger)
- [Real World Haskell, Luku 19, virheenkäsittelystä](http://book.realworldhaskell.org/read/error-handling.html)
- [The Logging Facade for Haskell (log-base)](https://hackage.haskell.org/package/log-base)
