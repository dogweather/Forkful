---
title:                "Tulevan tai menneen päivämäärän laskeminen"
aliases:
- fi/lua/calculating-a-date-in-the-future-or-past.md
date:                  2024-01-20T17:31:24.723669-07:00
model:                 gpt-4-1106-preview
simple_title:         "Tulevan tai menneen päivämäärän laskeminen"

tag:                  "Dates and Times"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fi/lua/calculating-a-date-in-the-future-or-past.md"
---

{{< edit_this_page >}}

## What & Why? - Mitä & Miksi?
Lasketaan päivämäärä tulevaisuudessa tai menneisyydessä. Koodarit tekevät tätä ajoituksen, määräaikojen ja tapahtumaseurannan vuoksi.

## How to: - Kuinka tehdä:
Lua ei sisällä sisäänrakennettuja päivämääräkäsittelyn työkaluja, mutta `os.date` ja `os.time` funktioilla selviää paljon. Esimerkki tulevaisuuden päivämäärän laskemisesta:

```Lua
-- Nykyinen aika
local nyt = os.time()

-- Lisätään 7 päivää (7 päivää * 24 tuntia * 60 minuuttia * 60 sekuntia)
local viikon_paasta = os.time{year=os.date("%Y", nyt), month=os.date("%m", nyt), day=os.date("%d", nyt) + 7}

-- Tulostetaan päivämäärä
print("Tänään on: " .. os.date("%x", nyt))
print("Viikon päästä on: " .. os.date("%x", viikon_paasta))
```

Esimerkkituloste:

```
Tänään on: 03/17/23
Viikon päästä on: 03/24/23
```

Menneisyyden päivämäärä lasketaan samalla tavalla, mutta vähennetään päiviä.

## Deep Dive - Syväsukellus:
Päivämäärälaskelmat ovat olleet ohjelmoinnissa pitkään. Ne ovat välttämättömiä mm. ajanhallintasovelluksille ja historiatiedoille. Lua ei keskity päivämääräkäsittelyyn, mutta `os`-kirjaston funktiot hoitavat perustarpeet. Eri käyttötarkoituksiin on olemassa kirjastoja kuten *Penlight*, joka voi tarjota laajempia toimintoja.

Koodin luetettavuus on tärkeää. On suositeltavaa käyttää kuvaavia muuttujanimiä, kuten `nyt` ja `viikon_paasta`. Joustavuuden maksimoimiseksi suunnittele funktioista riippumattomia ja helposti muokattavia.

## See Also - Katso Myös:
- Lua:n viralliset ohjedokumentit: https://www.lua.org/manual/5.4/manual.html#6.9
- Penlight-kirjaston dokumentointi: https://stevedonovan.github.io/Penlight/api/index.html
- Stack Overflow keskusteluja ja ohjeita päivämääristä: https://stackoverflow.com/questions/tagged/lua+date
