---
date: 2024-01-26 04:43:17.953657-07:00
description: "Kompleksiluvut laajentavat yksiulotteisen lukusuoran ideaa kaksiulotteiseen\
  \ tasoon sis\xE4llytt\xE4m\xE4ll\xE4 pystysuoran imagin\xE4\xE4riakselin. Ohjelmoijat\u2026"
lastmod: '2024-03-13T22:44:56.691822-06:00'
model: gpt-4-0125-preview
summary: "Kompleksiluvut laajentavat yksiulotteisen lukusuoran ideaa kaksiulotteiseen\
  \ tasoon sis\xE4llytt\xE4m\xE4ll\xE4 pystysuoran imagin\xE4\xE4riakselin."
title: "Kompleksilukujen k\xE4sittely"
weight: 14
---

## Miten:
Luassa voit esittää kompleksilukuja taulukoiden avulla. Perustoiminnot sisältävät taulukoiden lisäämisen, vähentämisen, kertomisen ja jakamisen. Näin se tapahtuu:

```lua
-- Määritä kaksi kompleksilukua taulukoina
local complex_a = { real = 3, imag = 5 }
local complex_b = { real = 2, imag = -4 }

-- Funktio kahden kompleksiluvun lisäämiseen
local function add_complex(a, b)
  return { real = a.real + b.real, imag = a.imag + b.imag }
end

-- Esimerkkituloste
print(add_complex(complex_a, complex_b))  -- { real = 5, imag = 1 }
```

## Syväsukellus
Kompleksiluvut ovat olleet olemassa 1500-luvulta lähtien, auttaen ratkaisemaan yhtälöitä, joita ei voitu selvittää pelkillä reaaliluvuilla. Luassa itsessään ei ole sisäänrakennettua kompleksiluvun tyyppiä. Tämä ei kuitenkaan ole suuri ongelma—voit luoda omia kompleksilukujen käsittelyjä käyttämällä taulukoita ja funktioita, kuten yllä on esitetty. Tai, jos tarpeesi ovat syvemmät, voit hankkia kirjaston kuten LuaComplex. Se on hyvä valinta, koska se on erityisesti Lualle rakennettu ja ottaa manuaalityön pois harteiltasi. Tällaiset kirjastot myös usein optimoivat operaatioita taustalla, joten ne ovat nopeampia kuin omien ratkaisujen kehittäminen.

## Katso Myös
Lisää yksityiskohtaisia esimerkkejä ja edistyneitä operaatioita varten, tutustu näihin:

- LuaComplex-kirjasto: https://github.com/davidm/lua-complex
- "Programming in Lua" -kirja, mukautettujen tietotyyppien luomisesta: https://www.lua.org/pil/11.1.html
- Wikipedia kompleksilukujen käytöstä eri aloilla: https://en.wikipedia.org/wiki/Complex_number#Applications
