---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:05:49.991882-07:00
description: "\xC5 kapitalisere en streng inneb\xE6rer \xE5 endre det f\xF8rste tegnet\
  \ i hvert ord i en setning til stor bokstav, samtidig som resten sikres \xE5 v\xE6\
  re sm\xE5 bokstaver.\u2026"
lastmod: '2024-03-13T22:44:40.912053-06:00'
model: gpt-4-0125-preview
summary: "\xC5 kapitalisere en streng inneb\xE6rer \xE5 endre det f\xF8rste tegnet\
  \ i hvert ord i en setning til stor bokstav, samtidig som resten sikres \xE5 v\xE6\
  re sm\xE5 bokstaver."
title: Sette stor bokstav i en streng
weight: 2
---

## Hvordan:
Lua har ikke en innebygd funksjon for å kapitalisere strenger, men du kan enkelt utføre denne oppgaven ved hjelp av grunnleggende strengmanipuleringsfunksjoner. Her er en enkel funksjon for å kapitalisere det første bokstaven i et enkelt ord:

```lua
function capitalize(word)
    return word:sub(1,1):upper() .. word:sub(2):lower()
end

print(capitalize("hello"))  -- Output: Hello
```

For å kapitalisere hvert ord i en setning, kan du dele setningen inn i ord, kapitalisere hvert enkelt, og deretter slå dem sammen igjen:

```lua
function capitalizeSentence(sentence)
    local words = {}
    for word in sentence:gmatch("%S+") do
        table.insert(words, capitalize(word))
    end
    return table.concat(words, " ")
end

print(capitalizeSentence("hello world from lua"))  -- Output: Hello World From Lua
```

Hvis du jobber med et prosjekt der ytelse er nøkkelen, og du finner deg selv i behov av mer avanserte strengmanipuleringskapasiteter, vurder å bruke et tredjepartsbibliotek som `Penlight`. Penlight forbedrer Lua med mer fleksible strengbehandlingsfunksjoner, blant annet:

```lua
-- Med forutsetning om at Penlight er installert:
local pl = require("pl.stringx")
local text = "hello lua users"
text = pl.capitalized(text)
print(text)  -- Output: Hello lua users

-- Merk: Penlights capitalized-funksjon kapitaliserer kun det første ordet.
-- For å kapitalisere hvert ord, ville du fortsatt implementere en egendefinert løsning eller utforske andre biblioteker.
```
