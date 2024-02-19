---
aliases:
- /fi/clojure/calculating-a-date-in-the-future-or-past/
date: 2024-01-20 17:31:15.736891-07:00
description: "Menneisyyden tai tulevaisuuden p\xE4iv\xE4m\xE4\xE4r\xE4n laskeminen\
  \ tarkoittaa tietyn ajanjakson lis\xE4\xE4mist\xE4 tai v\xE4hent\xE4mist\xE4 nykyisest\xE4\
  \ p\xE4iv\xE4st\xE4. Ohjelmoijat k\xE4ytt\xE4v\xE4t\u2026"
lastmod: 2024-02-18 23:09:07.242819
model: gpt-4-1106-preview
summary: "Menneisyyden tai tulevaisuuden p\xE4iv\xE4m\xE4\xE4r\xE4n laskeminen tarkoittaa\
  \ tietyn ajanjakson lis\xE4\xE4mist\xE4 tai v\xE4hent\xE4mist\xE4 nykyisest\xE4\
  \ p\xE4iv\xE4st\xE4. Ohjelmoijat k\xE4ytt\xE4v\xE4t\u2026"
title: "Tulevan tai menneen p\xE4iv\xE4m\xE4\xE4r\xE4n laskeminen"
---

{{< edit_this_page >}}

## What & Why?
Menneisyyden tai tulevaisuuden päivämäärän laskeminen tarkoittaa tietyn ajanjakson lisäämistä tai vähentämistä nykyisestä päivästä. Ohjelmoijat käyttävät tätä esimerkiksi vanhentumispäivien, määräaikojen ja aikavälien hallintaan.

## How to:
Clojure käyttää Javan `java.time` kirjastoa päivämäärien käsittelyyn. Tässä yksinkertainen esimerkki:

```Clojure
(require '[java-time :as jt])

;; Lisätään päiviä nykyhetkeen
(defn add-days [days]
  (-> (jt/local-date-now)
      (jt/plus-days days)))

;; Vähennetään päiviä nykyhetkestä
(defn subtract-days [days]
  (-> (jt/local-date-now)
      (jt/minus-days days)))

;; Esimerkkituloste
(println (add-days 10))     ;; 10 päivää tulevaisuuteen nykyhetkestä
(println (subtract-days 5))  ;; 5 päivää menneisyyteen nykyhetkestä
```

## Deep Dive:
Menetelmät päivämäärän laskemisesta ovat kehittyneet vuosien saatossa. Aiemmin, UTC-aikaa ja epätarkkoja menetelmiä käytettiin laajasti, mutta ajan myötä, `java.time` kirjasto on tuonut tarkkoja ja helppokäyttöisiä työkaluja päivämäärien käsittelyyn. Clojure, hyödyntämällä Javan tarjoamia kirjastoja, mahdollistaa puhtaat ja funktionaaliset ratkaisut ajankäsittelyyn.

On olemassa myös muita tapoja käsitellä päivämääriä Clojuressa, kuten `clj-time` kirjasto, mutta `java.time` on nykyään suosittu ja suositeltu vaihtoehto sen suorituskyvyn ja uudenaikaisuuden vuoksi.

Tarkkaa ajanhallintaa varten, on tärkeää ottaa huomioon aikavyöhykkeet ja kesäaika, mikä `java.time` tekee hyvin. Kun tehdään laskelmia menneisyyden tai tulevaisuuden päiville, ohjelmoijan tulee myös olla tietoinen näistä seikoista, jotta vältetään virheet.

## See Also:
- Java Platform, Standard Edition 8 Date and Time Guide: https://docs.oracle.com/javase/8/docs/technotes/guides/datetime/index.html
- Clojure java.time library documentation: https://clj-time.github.io/clj-time/doc/index.html
- Clojure for the Brave and True - Working with Time: https://www.braveclojure.com/do-things/#3-4-2-Working_with_Time
