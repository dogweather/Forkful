---
date: 2024-01-26 03:39:07.668911-07:00
description: "Lainausmerkkien poistaminen merkkijonosta tarkoittaa kiusallisten kaksin-\
  \ tai yksinkertaisten lainausmerkkien h\xE4vitt\xE4mist\xE4 tekstin ymp\xE4rilt\xE4\
  . Ohjelmoijat\u2026"
lastmod: '2024-03-13T22:44:56.172917-06:00'
model: gpt-4-0125-preview
summary: "Lainausmerkkien poistaminen merkkijonosta tarkoittaa kiusallisten kaksin-\
  \ tai yksinkertaisten lainausmerkkien h\xE4vitt\xE4mist\xE4 tekstin ymp\xE4rilt\xE4\
  ."
title: Merkkijonosta lainausmerkkien poistaminen
weight: 9
---

## Kuinka:
Clojuressa merkkijonot ovat muuttumattomia, joten kun puhumme "lainausmerkkien poistamisesta", puhumme oikeastaan uuden merkkijonon luomisesta ilman lainausmerkkejä. Tässä tiivistelmä käyttäen `clojure.string/replace`:

```clojure
(require '[clojure.string :as str])

; Heitetäänpä nuo kaksoislainausmerkit mäkeen
(defn remove-double-quotes [s]
  (str/replace s #"\"" ""))

; Ja potkaistaan ulos yksinkertaiset lainausmerkit
(defn remove-single-quotes [s]
  (str/replace s #"\'" ""))

; Esimerkkikäyttö:
(remove-double-quotes "\"Hei, maailma!\"") ; => "Hei, maailma!"
(remove-single-quotes "'Hei, maailma!'")   ; => "Hei, maailma!"
```
Haluatko käsitellä sekä yksinkertaiset että kaksoislainausmerkit yhdellä iskulla? Kurkista tähän:

```clojure
(defn remove-quotes [s]
  (str/replace s #"[\"\']" ""))

; Esimerkkikäyttö:
(remove-quotes "\"Hei, 'Clojure' maailma!\"") ; => "Hei, Clojure maailma!"
```

## Syväsukellus
Aikoinaan, kun data oli sotkuisempaa kuin lapsen makuuhuone, lainausmerkit merkkijonoissa olivat normi tekstin merkitsemiseksi. Mutta tietojenkäsittelytieteen kehittyessä lainausmerkit muuttuivat enemmäksi kuin vain tekstierottimiksi - niille annettiin myös syntaktisia rooleja ohjelmointikielissä.

Clojure, sen Lisp-perinnön ansiosta, ei käytä lainausmerkkejä samalla tavalla kuin jotkin muut kielet saattavat. Ne ovat toki merkkijonojen merkitsemiseen, mutta niillä on myös erityinen rooli literaalien luomisessa. Riippumatta siitä, lainausmerkkien poistaminen merkkijonoista pysyy ajattomana tehtävänä.

Miksi et vain leikkaa merkkijonon päitä? No, se olettaa lainausmerkkiesi aina halaavan merkkijonosi alkua ja loppua kuin pari ylisöpöilevää isovanhempaa. Todellinen data on sotkuisempaa. Tässä tulevat avuksi regex (säännölliset lausekkeet), joiden avulla voit tähdätä noihin lainausmerkkeihin riippumatta siitä, missä ne piileskelevät.

Vaihtoehtoja? Toki, voit hifistellä `subs`, `trim`, `triml`, `trimr`:llä tai jopa transduserilla, jos haluat rehvastella. Mutta `replace` regex:llä on kuin toisit valomiekan veitsitaisteluun - se menee suoraan asiaan.

## Katso Myös
Jos aivosi kaipaavat lisää Clojuren merkkijonojen käsittelyn herkkuja, nämä vihjeet saattavat auttaa:

- ClojureDocs `clojure.string/replace`-osoitteesta: https://clojuredocs.org/clojure.string/replace
- Säännölliset lausekkeet Clojuressa: https://clojure.org/guides/learn/syntax#_regex
- Java-interoptio merkkijonojen käsittelyyn (Clojurehan pyörii JVM:llä): https://clojure.org/reference/java_interop#_working_with_strings

Älä pysähdy vain lainausmerkkien poistamiseen. Clojure-maassa on kokonainen maailma merkkijonotaikuutta odottamassa löytämistään.
