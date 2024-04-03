---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:31:26.559625-07:00
description: "\xC5 skrive tester i programmering inneb\xE6rer \xE5 lage sm\xE5, separate\
  \ deler av kode for automatisk \xE5 verifisere at ulike deler av applikasjonen din\
  \ fungerer som\u2026"
lastmod: '2024-03-13T22:44:40.933710-06:00'
model: gpt-4-0125-preview
summary: "\xC5 skrive tester i programmering inneb\xE6rer \xE5 lage sm\xE5, separate\
  \ deler av kode for automatisk \xE5 verifisere at ulike deler av applikasjonen din\
  \ fungerer som forventet."
title: Skrive tester
weight: 36
---

## Hvordan:
Lua, som er et lettvekts, men kraftfullt skriptspråk, inkluderer ikke et innebygd testrammeverk. Imidlertid gjør tredjepartsbiblioteker som Busted og LuaUnit testingen relativt grei. Her vil vi se på eksempler ved bruk av begge.

### Bruker Busted
Busted er et populært Lua-testrammeverk som tilbyr en fleksibel måte å skrive tester på. Først installerer du Busted gjennom LuaRocks (Luas pakkebehandler) med `luarocks install busted`. Når installert, kan du skrive testene dine. Her er en enkel test for en funksjon `add` som summerer to tall:

```lua
-- add.lua
local function add(a, b)
  return a + b
end

return add
```

```lua
-- add_spec.lua
local add = require('add')

describe("Add funksjon", function()
  it("skal legge sammen to tall korrekt", function()
    assert.are.equal(5, add(2, 3))
  end)
end)
```

For å kjøre testene, eksekverer du `busted` i terminalen din. Eksempelutdata for en vellykket test ville se slik ut:

```
●
1 suksess / 0 feil / 0 feil / 0 ventende : 0.002 sekunder
```

### Bruker LuaUnit
LuaUnit er et annet testrammeverk som følger xUnit-konvensjoner og er enkelt å sette opp. Installer LuaUnit via LuaRocks ved å bruke `luarocks install luaunit`. Her er hvordan du kan skrive en lignende test som ovenfor med LuaUnit:

```lua
-- add.lua forblir den samme

-- test_add.lua
luaunit = require('luaunit')
local add = require('add')

function testAdd()
  luaunit.assertEquals(add(2, 3), 5)
end

os.exit(luaunit.LuaUnit.run())
```

Å kjøre dette skriptet direkte via Lua (`lua test_add.lua`) vil gi noe slikt som utdata:

```
.
Kjørte 1 tester på 0.001 sekunder, 1 suksess, 0 feil
```

Både Busted og LuaUnit tilbyr omfattende funksjoner for å håndtere ulike testscenarier, inkludert mocking, spionering, og asynkron testing. Valget mellom dem ligger i de spesifikke behovene til prosjektet ditt og din personlige preferanse når det gjelder syntaks og funksjonalitet.
