---
date: 2024-01-20 17:37:05.492103-07:00
description: "Datum till str\xE4ng-konvertering handlar om att omvandla den s\xE4\
  tt som datum lagras i kod (ofta som ett numeriskt v\xE4rde eller ett datumobjekt)\
  \ till en l\xE4sbar\u2026"
lastmod: '2024-03-13T22:44:38.050161-06:00'
model: gpt-4-1106-preview
summary: "Datum till str\xE4ng-konvertering handlar om att omvandla den s\xE4tt som\
  \ datum lagras i kod (ofta som ett numeriskt v\xE4rde eller ett datumobjekt) till\
  \ en l\xE4sbar textform."
title: "Omvandla ett datum till en str\xE4ng"
weight: 28
---

## Hur gör man:
```Lua
os.setlocale('sv_SE')  -- Sätt lokalen till svensk för datumformat

local datum = os.date("*t") -- Hämta aktuell tid som en tabell
local datumSomStrang = os.date("%Y-%m-%d %H:%M:%S", os.time(datum))

print(datumSomStrang)  -- Exempel: 2023-03-15 14:20:35
```
Ovanstående kod visar hur du använder `os.date()` för att konvertera dagens datum till en sträng.

## Fördjupning:
I Lua görs datum till sträng-konverteringar med standardbiblioteket `os`. Historiskt sett har datumhantering och dess representation varierat mycket mellan olika programmeringsspråk och system. Lua erbjuder en flexibel modell där programvaruutvecklare kan välja formatsträngar själva.

Det finns andra sätt att konvertera datum till strängar, till exempel genom att använda externa bibliotek som `luadate`, men `os.date()` är direkt tillgängligt och tillräckligt för de flesta behov.

När det gäller implementering, jobbar `os.date()` genom att ta ett format och en tidsstämpel. Om tidsstämpeln utelämnas används aktuell tid. Formatsträngen bestämmer strängens utseende och kan inkludera år, månad, dag, timme, minut och sekund.

## Se även:
- Lua's officiella dokumentation om `os.date`: https://www.lua.org/manual/5.4/manual.html#6.9
- `luadate`: https://github.com/Tieske/date, ett mer avancerat datumhanteringsbibliotek för Lua.
