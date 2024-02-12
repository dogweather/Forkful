---
title:                "HTML:n jäsentäminen"
aliases:
- /fi/clojure/parsing-html/
date:                  2024-01-20T15:30:45.707879-07:00
simple_title:         "HTML:n jäsentäminen"

tag:                  "HTML and the Web"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/clojure/parsing-html.md"
---

{{< edit_this_page >}}

## What & Why?
(Mitä & Miksi?)
HTML:n jäsentäminen tarkoittaa HTML-koodin rakenteen lukemista ja sen sisällön muuntamista käsiteltäväksi tietorakenteeksi. Ohjelmoijat tekevät tätä sisällön automaattiseksi käsittelyksi, tiedon kaivamiseksi tai web-sivujen manipulointia varten.

## How to:
(Miten tehdään:)
```Clojure
; Valitse ja lisää projektiisi kirjasto, esim. Enlive
(require '[net.cgrand.enlive-html :as html])

; Esimerkki HTML-dokumentin jäsentämisestä
(def page "<html><head><title>Tervetuloa</title></head><body><h1>Hei Maailma</h1></body></html>")

; Jäsentäminen ja elementin etsiminen
(defn parse-and-find []
  (let [document (html/html-resource (java.io.StringReader. page))
        h1-text (html/text (first (html/select document [:h1])))]
    h1-text))

; Tulos
(prn (parse-and-find))
; Tulostuu: "Hei Maailma"
```

## Deep Dive:
(Syväsukellus:)
Alunperin HTML:n jäsentämisen tarve tuli siitä, että internetin sisällöstä haluttiin hyötyä automaattisesti. Vaihtoehtoina jäsentimille ovat olleet regex-pohjaiset ratkaisut, jotka voivat olla riskialttiita ja virheherkkiä puutteellisen standardinmukaisuuden vuoksi.

Käytännössä HTML-jäsentimet kuten Enlive (Clojure) tai Beautiful Soup (Python) ottavat käsiteltävän HTML-koodin, luovat siitä Document Object Model (DOM) -puun ja mahdollistavat sen elementtien käytön ohjelmoinnissa.

DOM-puun rakentaminen on keskeistä, koska se mahdollistaa monimutkaistenkin HTML-dokumenttien rakenteen käsittelyn ja manipuloimisen koherentilla ja virheettömällä tavalla. Tämä on välttämätöntä palvelimien välisessä kommuniokoinnissa ja automatisoiduissa prosesseissa.

Clojure-ympäristössä suosittuja HTML-jäsentimiä ovat muun muassa Enlive ja Hickory, joista kumpikin käsittelee HTML:ää eri tavoin. Enlive keskittyy selektori- ja muokkausoperaatioihin, kun taas Hickory muuntaa HTML:n Clojure-dataksi.

## See Also:
(Lisää tietoa:)
- Enlive dokumentaatio: [https://github.com/cgrand/enlive](https://github.com/cgrand/enlive)
- "Practical Web Scraping for Data Science: Best Practices and Examples with Python" kirja, joka antaa kontekstia web scraperien maailmaan: [Linkki kirjaan](https://www.datascraping.co/practical-web-scraping/)
- Hickory GitHub-sivu: [https://github.com/davidsantiago/hickory](https://github.com/davidsantiago/hickory)
