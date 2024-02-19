---
aliases:
- /fi/lua/extracting-substrings/
date: 2024-01-20 17:46:22.798337-07:00
description: "Substringit ovat osia isommista tekstijonoista. K\xE4yt\xE4mme substringien\
  \ irrottamista, kun haluamme prosessoida tai analysoida pienempi\xE4 tietoja, kuten\u2026"
lastmod: 2024-02-18 23:09:07.745472
model: gpt-4-1106-preview
summary: "Substringit ovat osia isommista tekstijonoista. K\xE4yt\xE4mme substringien\
  \ irrottamista, kun haluamme prosessoida tai analysoida pienempi\xE4 tietoja, kuten\u2026"
title: Merkkijonojen osien poimiminen
---

{{< edit_this_page >}}

## What & Why? / Mikä & Miksi?
Substringit ovat osia isommista tekstijonoista. Käytämme substringien irrottamista, kun haluamme prosessoida tai analysoida pienempiä tietoja, kuten käyttäjänimen sähköpostiosoitteesta.

## How to: / Kuinka tehdä:
```Lua
local teksti = "tervetuloa_programmointiin!"
-- Alkuindeksi ja loppuindeksi
local substring = teksti:sub(1, 11)
print(substring) -- tulos: "tervetuloa_"

-- Negaatiiviset indeksit (lopusta alkaen)
local loppuosa = teksti:sub(-14)
print(loppuosa) -- tulos: "programmointiin!"

-- Pattern-matching leikkaus
local kayttajanimi = string.match("esimerkki@esimerkki.fi", "([^@]+)")
print(kayttajanimi) -- tulos: "esimerkki"
```

## Deep Dive / Syväsukellus:
Lua-kielen string-handling-nojaa voimakkaasti yhteenrakennettuihin funktioihin, kuten `sub` ja `match`. Historiallisesti Lua kasvoi embeddattujen systeemien tarpeista: pieni footprintti, mutta tehokkaat string-työkalut ovat aina olleet korostettuja.

Pattern-matching perustuu säännöllisiin lausekkeisiin (regex), mutta on rajoitettumpi. `match` funktio sallii monimutkaisten patternien tunnistamista stringeistä ilman että tarvitsee vetää sisään kokonaisia regex-kirjastoja.

Substring-funktioita käytettäessä indeksit alkavat ykkösestä, ei nollasta, kuten monissa muissa kielissä. Negatiiviset indeksit laskevat lopusta alkaen, mistä on usein hyötyä.

## See Also / Katso Myös:
- [Programming in Lua (Fourth Edition)](https://www.lua.org/pil/contents.html) – Luotettava kirja perusteista syvällisiin tekniikoihin.
- [Lua 5.4 Reference Manual](https://www.lua.org/manual/5.4/) – Virallinen dokumentaatio ja käyttöopas.
