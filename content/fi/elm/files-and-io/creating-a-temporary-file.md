---
date: 2024-01-20 17:40:13.191330-07:00
description: "Luodaan v\xE4liaikainen tiedosto: se on tilap\xE4inen s\xE4ilytyspaikka\
  \ datalle. K\xE4yt\xE4mme sit\xE4, kun haluamme k\xE4sitell\xE4 tietoa, jota ei\
  \ tarvitse s\xE4ilytt\xE4\xE4\u2026"
lastmod: '2024-03-13T22:44:56.508186-06:00'
model: gpt-4-1106-preview
summary: "Luodaan v\xE4liaikainen tiedosto: se on tilap\xE4inen s\xE4ilytyspaikka\
  \ datalle."
title: "V\xE4liaikaistiedoston luominen"
weight: 21
---

## How to: (Miten Tehdään:)
Elmissä ei ole suoraa tapaa luoda väliaikaisia tiedostoja, koska se keskittyy puhtaasti frontend-kehitykseen ja pyörii selainympäristössä, missä pääsy tiedostojärjestelmään on erittäin rajoitettua. Voit kuitenkin manipuloida väliaikaista dataa käyttäen `Web Storage API:a`, johon pääset käsiksi Elm-kielellä.

```Elm
-- Elm-toteutus väliaikaisen datan tallentamiseksi Web Storageen:
import Browser
import Html
import Json.Decode as Decode
import Json.Encode as Encode

-- localStorageen tallentava komento
storeTempData : String -> String -> Cmd msg
storeTempData key value =
    Browser.Dom.setStorage key (Encode.string value)

-- localStoragesta poistava komento
removeTempData : String -> Cmd msg
removeTempData key =
    Browser.Dom.removeStorage key

-- Käytön esimerkki tallentaen väliaikainen "tempValue"
exampleUsage : Cmd msg
exampleUsage =
    storeTempData "temporaryKey" "tempValue"
```

Huomaa, että tämä toimii vain selaimessa ja data pysyy siellä, kunnes se poistetaan tai selain tyhjentää välimuistinsa.

## Deep Dive (Sukellus Syvyyksiin)
Ennen pilvipalveluita väliaikaiset tiedostot olivat arkipäivää tiedon väliaikaista säilytystä varten. Väliaikaiset tiedostot ovat olleet arvokkaita etenkin batch-prosessoinnissa ja suorituskykyä vaativissa sovelluksissa, kun halutaan varmistaa, ettei muistia kuormiteta liikaa.

Elmissä ei ole sisäänrakennettuja keinoja väliaikaisten tiedostojen käsittelylle koska se on suunniteltu toimimaan selainympäristössä, missä tiedostojärjestelmän käsittely on rajoitettua. Vaihtoehtoja väliaikaiselle datan tallennukselle voivat olla esimerkiksi Web Storage API, IndexedDB tai pilvipalvelut.

Web Storage API:ssa on kaksi säilytysvaihtoehtoa: `localStorage` ja `sessionStorage`. `localStorage` säilyttää tietoja ilman vanhentumispäivää, kun taas `sessionStorage` säilyttää dataa vain selainistunnon ajan.

Implementointi tapahtuu selain API -kutsujen kautta, jotka Elm mahdollistaa suorittaa komentojen (`Cmd`) avulla. Tätä voidaan laajentaa käyttämällä portteja (`Ports`) kommunikoida suoraan JavaScriptin kanssa, mikäli tarvitset enemmän hallintaa yli selaimen datan tallennusominaisuuksien.

## See Also (Katso Myös)
- Elm ohjeet Web Storage API:n käyttöön: [https://guide.elm-lang.org/effects/](https://guide.elm-lang.org/effects/)
- MDN Web Docs Web Storage API: [https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API)
- MDN Web Docs IndexedDB API: [https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API)
  
Elm ja sen ekosysteemi keskittyvät vahvasti turvalliseen ja helppokäyttöiseen frontend-kehitykseen. Tiedostojen käsittely suoraan Elm-koodista ei ole perustoiminnallisuus, mutta selaimen tarjoamat rajapinnat tarjoavat väylän väliaikaiseen datan tallennukseen ja käsittelyyn.
