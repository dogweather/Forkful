---
aliases:
- /fi/lua/working-with-xml/
date: 2024-01-26 04:33:43.001779-07:00
description: "XML:n kanssa ty\xF6skentelyn yhteydess\xE4 k\xE4sitell\xE4\xE4n XML-dokumentteja\
  \ koodin avulla. Ohjelmoijat tekev\xE4t t\xE4m\xE4n lukeakseen, kirjoittaakseen\
  \ ja muokatakseen\u2026"
lastmod: 2024-02-18 23:09:07.783371
model: gpt-4-0125-preview
summary: "XML:n kanssa ty\xF6skentelyn yhteydess\xE4 k\xE4sitell\xE4\xE4n XML-dokumentteja\
  \ koodin avulla. Ohjelmoijat tekev\xE4t t\xE4m\xE4n lukeakseen, kirjoittaakseen\
  \ ja muokatakseen\u2026"
title: "XML:n k\xE4sittely"
---

{{< edit_this_page >}}

## Mikä & Miksi?
XML:n kanssa työskentelyn yhteydessä käsitellään XML-dokumentteja koodin avulla. Ohjelmoijat tekevät tämän lukeakseen, kirjoittaakseen ja muokatakseen dataa rakenteellisessa, siirrettävässä muodossa, jota käytetään laajalti datan vaihdossa ja tallennuksessa.

## Kuinka:
Lua ei sisällä natiivia XML-jäsennystä, mutta on olemassa kirjastoja, kuten LuaXML ja xml2lua, jotka suorittavat tehtävän. Tässä on nopea katsaus XML:n jäsentämiseen xml2lua:lla:

```Lua
local xml2lua = require("xml2lua")
local handler = require("xmlhandler.tree")

local xmlParser = xml2lua.parser(handler)
xmlParser:parse([[<root><book id="123">Ohjelmointi Lualla</book></root>]])

print(handler.root.book._attr.id)  -- Tulostaa: 123
print(handler.root.book[1])        -- Tulostaa: Ohjelmointi Lualla
```

XML:n kirjoittamista varten, tässä on miniesimerkki käyttäen LuaXML:ää:

```Lua
local luaxml = require("LuaXML")

local xml = xml.new("root")
xml:append("book")[1] = "Ohjelmointi Lualla"
xml.book._attr = {id="123"}

print(xml:tag())  -- Tulostaa: <root><book id="123">Ohjelmointi Lualla</book></root>
```

## Syväsukellus
XML, lyhenteenä Extensible Markup Language, on ollut standardi datan esittämisessä ja vaihdossa 90-luvun puolivälistä lähtien. Se antaa rakenteen datalle ja on sekä ihmisen luettavissa että koneellisesti jäsentävissä.

Vaikka JSON ja YAML ovat nykyään suosittuja niiden yksinkertaisuuden vuoksi, XML on edelleen yleinen monissa yritys- ja perintöjärjestelmissä. Luassa natiivi XML-käsittely ei ole sisäänrakennettu, koska Luat on suunniteltu olemaan pieni ja laajennettavissa moduulien kautta.

Lua:lle suunnatut XML-kirjastot, kuten LuaXML, xml2lua ja muut, paikkaavat tämän aukon. LuaXML tarjoaa kevyen XML-lukijan ja -kirjoittajan, kun taas xml2lua käyttää tapahtumavetoista lähestymistapaa, joka on samankaltainen kuin SAX-jäsentimet. Nämä kirjastot on yleensä toteutettu puhtaasti Luassa siirrettävyyden vuoksi, kun taas jotkut saattavat nojata C:hen suorituskyvyn vuoksi.

Suorituskyvyn ja muistinkäytön osalta Luat XML-kirjastot eivät ehkä ole yhtä nopeita kuin kielet, joissa on natiivi tuki. Kuitenkin useimmissa Luat käyttötarkoituksissa, erityisesti pelikehityksessä tai upotettujen järjestelmien skriptauksessa, nämä kirjastot tekevät hyvää työtä ylikuormittamatta järjestelmää.

## Katso myös
- LuaXML GitHubissa: https://github.com/LuaDist/luaxml
- xml2lua GitHubissa: https://github.com/manoelcampos/xml2lua
- Luat kirjastojen lista: https://lua-users.org/wiki/LibrariesAndBindings
