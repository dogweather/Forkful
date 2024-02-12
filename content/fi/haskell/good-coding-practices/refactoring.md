---
title:                "Koodin uudelleenjärjestely"
aliases:
- fi/haskell/refactoring.md
date:                  2024-01-26T01:37:46.349654-07:00
model:                 gpt-4-0125-preview
simple_title:         "Koodin uudelleenjärjestely"

tag:                  "Good Coding Practices"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/haskell/refactoring.md"
---

{{< edit_this_page >}}

## Mitä & Miksi?
Koodin refaktorointi on prosessi, jossa koodia muokataan siten, että sen ulkoinen toiminta ei muutu. Kyse on koodin siistimisestä ja järjestämisestä, jotta koodi olisi helpompi lukea, ylläpitää ja laajentaa. Se voi myös auttaa korjaamaan bugeja ja parantamaan suorituskykyä.

## Miten:
Oletetaan, että sinulla on pätkä Haskell-koodia, joka toistaa itseään enemmän kuin lempikappaleesi. Tässä on nopea katsaus siihen, miten voisit refaktoroida sitä funktioiden avulla.

Ennen refaktorointia:

```haskell
printInvoice :: String -> Float -> String -> IO ()
printInvoice asiakas yhteensä tuote = do
  putStrLn $ "Asiakas: " ++ asiakas
  putStrLn $ "Yhteensä: " ++ show yhteensä
  putStrLn $ "Tuote: " ++ tuote
```

Pienen refaktoroinnin jälkeen:

```haskell
printDetail :: String -> String -> IO ()
printDetail otsikko arvo = putStrLn $ otsikko ++ ": " ++ arvo

printInvoice :: String -> Float -> String -> IO ()
printInvoice asiakas yhteensä tuote = do
  printDetail "Asiakas" asiakas
  printDetail "Yhteensä" (show yhteensä)
  printDetail "Tuote" tuote

-- Esimerkkituloste:
-- Asiakas: Alice
-- Yhteensä: $42.00
-- Tuote: Haskell-ohjelmointiopas
```

Kuten näette, yleisen kaavan eriyttämällä erilliseen `printDetail`-funktioon vältämme toiston ja teemme `printInvoice`-funktiosta selvemmän ja helpommin hallittavan.

## Syväsukellus
Kun Haskell ilmestyi näyttämölle 80-luvun lopulla, oli selvää, että funktionaalinen paradigma voisi tuoda raikasta ilmaa koodauskäytäntöihin. Ajan myötä Haskellin refaktorointi on erityisen eleganttia, koska funktiot ovat ensiluokkaisia kansalaisia ja sillä on vahva staattinen tyypitysjärjestelmä. Voit refaktoroida pelkäämättä, että rikkoisit sovelluksesi, koska kääntäjä on tukenasi.

Manuaalisen refaktoroinnin vaihtoehtoja voivat olla automatisoidut työkalut, vaikka Haskellin funktionaalinen luonne ja tyypin turvallisuus voivat joskus tehdä tästä vähemmän yleistä verrattuna muihin kieliin. Toteutuksen kannalta on tärkeää hyödyntää Haskellin ominaisuuksia, kuten korkeamman asteen funktioita, puhtautta ja muuttumattomuutta, jotta refaktorointi sujuisi sujuvammin.

Refaktoroinnit, kuten juuri esitelty "Erota Funktio", ovat yleisiä, mutta voit myös tehdä "Inline-funktio", "Nimeä uudelleen muuttuja" ja "Muuta funktion allekirjoitusta" luottavaisesti, kiitos tyypitysjärjestelmän. Haskellin tehokas tyypin päätteleminen voi joskus napata virheitä, jotka saattaisivat livahtaa läpi muissa kielissä.

## Katso myös
Sukelteemisen syvemmälle Haskellin refaktoroinnissa, tutustu kirjaan "Refaktorointi: Olemassa olevan koodin suunnittelun parantaminen" kirjoittanut Martin Fowler, jossa konseptit ovat yleisesti sovellettavissa. Tutustu hlint-työkaluun automatisoituja vinkkejä varten Haskell-koodisi parantamiseksi. Käy myös Haskell wikissä (https://wiki.haskell.org/Refactoring) yhteisön oivalluksia ja lisälukemista varten.
