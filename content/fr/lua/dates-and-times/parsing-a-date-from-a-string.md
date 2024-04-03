---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:14:49.186479-07:00
description: "Analyser une date \xE0 partir d'une cha\xEEne de caract\xE8res consiste\
  \ \xE0 convertir des repr\xE9sentations textuelles de dates et d'heures en un format\
  \ qui peut \xEAtre\u2026"
lastmod: '2024-03-13T22:44:57.946954-06:00'
model: gpt-4-0125-preview
summary: "Analyser une date \xE0 partir d'une cha\xEEne de caract\xE8res consiste\
  \ \xE0 convertir des repr\xE9sentations textuelles de dates et d'heures en un format\
  \ qui peut \xEAtre facilement manipul\xE9, stock\xE9 ou compar\xE9 au sein d'un\
  \ programme Lua."
title: "Analyser une date depuis une cha\xEEne de caract\xE8res"
weight: 30
---

## Comment faire :
Lua n'a pas de support intégré pour la manipulation des dates et des heures au-delà de la fonctionnalité limitée fournie par les fonctions `os.date` et `os.time`. Cependant, celles-ci peuvent être utilisées pour un parsing de base, et pour des besoins plus complexes, la bibliothèque `luadate`, une bibliothèque externe, peut être utilisée.

**Utilisation de `os.date` et `os.time` :**
```lua
-- Convertir une date lisible par l'homme en un timestamp et inversement
local dateString = "2023-09-21 15:00:00"
local pattern = "(%d+)-(%d+)-(%d+) (%d+):(%d+):(%d+)"
local year, month, day, hour, minute, second = dateString:match(pattern)

local timestamp = os.time({
  year = year,
  month = month,
  day = day,
  hour = hour,
  min = minute,
  sec = second
})

-- Convertir le timestamp en un format lisible par l'homme
local formattedDate = os.date("%Y-%m-%d %H:%M:%S", timestamp)
print(formattedDate)  -- Sortie : 2023-09-21 15:00:00
```

**Utilisation de `luadate` (bibliothèque tierce) :**
Pour utiliser `luadate`, assurez-vous qu'elle est installée via LuaRocks ou votre gestionnaire de paquets de choix. `luadate` ajoute des capacités étendues d'analyse et de manipulation de dates et d'heures.

```lua
local date = require('date')

-- Analyser directement une chaîne de date
local parsedDate = date.parse("2023-09-21 15:00:00")
print(parsedDate:fmt("%Y-%m-%d %H:%M:%S"))  -- Sortie : 2023-09-21 15:00:00

-- Ajouter des durées
local oneWeekLater = parsedDate:adddays(7)
print(oneWeekLater:fmt("%Y-%m-%d %H:%M:%S"))  -- Sortie : 2023-09-28 15:00:00
```

La bibliothèque `luadate` offre une manière plus intuitive et puissante de travailler avec les dates, incluant l'analyse à partir de chaînes, le formatage, et les opérations arithmétiques sur les dates, ce qui simplifie considérablement le travail avec les données temporelles en Lua.
