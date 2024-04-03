---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:27:39.098128-07:00
description: "Tekstitiedoston kirjoittaminen Clojuren avulla tarkoittaa tiedostojen\
  \ luomista tai muokkaamista tietojen tallentamiseksi sovelluksen ulkopuolelle,\u2026"
lastmod: '2024-03-13T22:44:56.202587-06:00'
model: gpt-4-0125-preview
summary: "Tekstitiedoston kirjoittaminen Clojuren avulla tarkoittaa tiedostojen luomista\
  \ tai muokkaamista tietojen tallentamiseksi sovelluksen ulkopuolelle, mahdollistaen\
  \ tietojen s\xE4ilymisen, konfiguraation, lokituksen tai prosessien v\xE4lisen viestinn\xE4\
  n."
title: Tekstitiedoston kirjoittaminen
weight: 24
---

## Kuinka:


### Tekstin kirjoittaminen tiedostoon Clojuren sisäänrakennettujen funktioiden avulla
`spit` funktio on yksinkertaisin tapa kirjoittaa tekstiä tiedostoon Clojuressa. Se ottaa kaksi argumenttia: tiedostopolun ja kirjoitettavan merkkijonon. Jos tiedostoa ei ole olemassa, `spit` luo sen. Jos se on, `spit` ylikirjoittaa sen.

```clojure
(spit "example.txt" "Hei, maailma!")
```

Tekstin lisäämiseksi olemassa olevaan tiedostoon voit käyttää `spit` funktiota `:append`-vaihtoehdon kanssa.

```clojure
(spit "example.txt" "\nLisätään tämä uusi rivi." :append true)
```

Ajettuasi nämä katkelmat, "example.txt" sisältää:

```
Hei, maailma!
Lisätään tämä uusi rivi.
```

### Kolmannen osapuolen kirjastojen käyttö
Vaikka Clojuren sisäänrakennetut toiminnot ovat usein riittäviä, yhteisö on kehittänyt vankkoja kirjastoja monimutkaisempia tai spesifisempiä tehtäviä varten. Tiedosto I/O:tä varten suosittu kirjasto on `clojure.java.io`, joka tarjoaa enemmän Java-tyylisen lähestymistavan tiedostojen käsittelyyn.

`clojure.java.io` kirjaston käyttämiseen tiedoston kirjoittamiseen, sinun tulee ensin tuoda se:

```clojure
(require '[clojure.java.io :as io])
```

Sen jälkeen voit käyttää `writer` funktiota kirjoitustarkoitusten saavuttamiseksi ja `spit` funktiota (tai muita kuten `print`, `println`) kirjoittaaksesi tiedostoon:

```clojure
(with-open [w (io/writer "example_with_io.txt")]
  (.write w "Tämä on kirjoitettu käyttäen clojure.java.io"))
```

Tämä luo (tai ylikirjoittaa, jos se jo on olemassa) "example_with_io.txt" tekstillä:

```
Tämä on kirjoitettu käyttäen clojure.java.io
```

Muista: `with-open` varmistaa, että tiedosto suljetaan kunnolla kirjoittamisen jälkeen, välttäen mahdolliset resurssivuodot.
