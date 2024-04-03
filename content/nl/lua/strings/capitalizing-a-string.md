---
changelog:
- 2024-01-28, gpt-4-0125-preview, translated from English
date: 2024-01-28 21:56:09.093862-07:00
description: "Het kapitaliseren van een tekenreeks betekent het met een hoofdletter\
  \ schrijven van de eerste letter van elk woord. Programmeurs doen dit voor\u2026"
lastmod: '2024-03-13T22:44:50.920807-06:00'
model: gpt-4-0125-preview
summary: Het kapitaliseren van een tekenreeks betekent het met een hoofdletter schrijven
  van de eerste letter van elk woord.
title: Een string met hoofdletters maken
weight: 2
---

## Hoe te:
Lua heeft geen ingebouwde hoofdletterfunctie, dus laten we er een maken:

```lua
function capitalize(str)
  return (str:gsub("(%l)(%w*)", function(first, rest) return first:upper()..rest end))
end

print(capitalize("hello world"))  -- Output: Hallo Wereld
```

## Diepgaand
Hoofdletterfuncties zijn standaard in veel programmeertalen. In Lua maken we er een met `string.gsub()`, een krachtige functie voor patroonovereenkomst. Onze aangepaste `capitalize` functie gebruikt een patroon om kleine letters (`%l`) te vinden gevolgd door nul of meer woordkarakters (`%w*`), en vervangt deze door de hoofdletter en de rest van het woord.

```lua
-- Hier is nog een manier om alleen het eerste woord te kapitaliseren
function capitalizeFirst(str)
  if str == "" then return str end
  return str:sub(1, 1):upper()..str:sub(2)
end
```

Lua's patroonvergelijkingsmogelijkheden zijn minder krachtig dan volledige reguliere expressies, maar zijn geschikt voor veel taken op het gebied van tekenreeksmanipulatie. Let op dat onze `capitalize` functie geen woorden zal kapitaliseren die volgen op bepaalde leestekens, dus het is niet waterdicht. Voor robuustere oplossingen kunt u extra patroonvergelijkingen of externe bibliotheken overwegen.

Historisch gezien is de behoefte aan hoofdletterfuncties ontstaan ​​uit het verlangen om tekstgegevens uniform te presenteren, vooral in gebruikersinterfaces. Er moet echter voorzichtig worden omgegaan met het begrijpen van de context: verschillende talen en culturen hebben hun eigen regels voor kapitalisatie, verder dan simpelweg de eerste letter van een zin of naam.

## Zie Ook
- Lua `string` bibliotheek: https://www.lua.org/manual/5.4/manual.html#6.4
- Lua Patronen: https://www.lua.org/pil/20.2.html
- Tekstverwerking in Lua: https://www.lua.org/pil/20.html
