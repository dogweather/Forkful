---
title:                "Interpolera en sträng"
date:                  2024-01-20T17:51:34.331300-07:00
model:                 gpt-4-1106-preview
simple_title:         "Interpolera en sträng"
programming_language: "Lua"
category:             "Lua"
tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/sv/lua/interpolating-a-string.md"
---

{{< edit_this_page >}}

## Vad & Varför?
Stringinterpolering innebär att du injicerar variabler direkt i en textsträng. Programmerare använder det för att enkelt bygga dynamiska meddelanden eller behandla data utan att klumpigt konkatenera strängar och variabler.

## Hur gör man:
```Lua
local användarnamn = "Erik"
local ålder = 29
-- Använd string.format för interpolering
local hälsning = string.format("Hej, %s! Du är %d år gammal.", användarnamn, ålder)
print(hälsning)
```
Output:
```
Hej, Erik! Du är 29 år gammal.
```
Alternativt:
```Lua
-- Med tabeller och uppslagning
local användare = {namn = "Erik", ålder = 29}
local hälsning = ("Hej, %s! Du är %d år gammal."):format(användare.namn, användare.ålder)
print(hälsning)
```
Output är densamma som ovan.

## Deep Dive
Före `string.format`, skedde konkatenering av strängar och variabler manuellt, exempelvis: `local hälsning = "Hej, " .. användarnamn .. "! Du är " .. ålder .. " år gammal."` Vilket var både bökigt och svårläst. `string.format` erbjuder en ren och lättläst syntax som är särskilt användbar för komplexa eller långa strängar.

Lua använder format specifierare (såsom `%s` för strängar, `%d` för decimaltal) inuti strängen som ersätts av tillhörande värden. Detta koncept är inte unikt för Lua – det är inspirerat av C:s `printf` funktion.

Som alternativ kan man använda tabeller. I Lua kan tabellfält ha nästan vilken nyckeltyp som helst, men string keys är vanligast för detta syfte. Med en vältänkt struktur kan interpolering och datahantering förenklas, vilket kan vara kraftfullt i större program.

## Se även:
- Lua's officiella dokumentation om strängar: [https://www.lua.org/manual/5.4/manual.html#6.4](https://www.lua.org/manual/5.4/manual.html#6.4)
- En guide till `string.format`: [https://www.lua.org/pil/20.2.html](https://www.lua.org/pil/20.2.html)
