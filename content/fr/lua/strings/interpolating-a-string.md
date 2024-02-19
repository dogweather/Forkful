---
aliases:
- /fr/lua/interpolating-a-string/
date: 2024-01-20 17:51:04.219727-07:00
description: "L'interpolation de cha\xEEnes c'est quand on ins\xE8re des valeurs variables\
  \ dans une cha\xEEne de caract\xE8res. Les programmeurs le font pour simplifier\
  \ la cr\xE9ation\u2026"
lastmod: 2024-02-18 23:09:08.954431
model: gpt-4-1106-preview
summary: "L'interpolation de cha\xEEnes c'est quand on ins\xE8re des valeurs variables\
  \ dans une cha\xEEne de caract\xE8res. Les programmeurs le font pour simplifier\
  \ la cr\xE9ation\u2026"
title: "Interpolation de cha\xEEnes de caract\xE8res"
---

{{< edit_this_page >}}

## What & Why?
L'interpolation de chaînes c'est quand on insère des valeurs variables dans une chaîne de caractères. Les programmeurs le font pour simplifier la création de texte dynamique.

## How to:
```Lua
-- Concaténation classique
local nom = "Mundo"
local message = "Hola, " .. nom .. "!"
print(message)  -- Hola, Mundo!

-- Utilisation de string.format
local age = 30
local texte = string.format("J'ai %d ans.", age)
print(texte)  -- J'ai 30 ans.
```

## Deep Dive
Historiquement, Lua n'avait pas d'interpolation de chaîne intégrée comme certaines autres langues; les développeurs utilisaient la concaténation avec `..` ou `string.format()`. Plus récemment, des bibliothèques externes ont ajouté des fonctionnalités d'interpolation, comme `interpolate` dans LuaRocks. En termes d'alternatives, certains préfèrent utiliser des fonctions comme `string.gsub()` pour remplacer les marqueurs par des valeurs spécifiques. La plupart des méthodes d’interpolation dans Lua restent cependant explicites, sans syntaxe propre à l'interpolation comme dans d'autres langages.

## See Also
- La documentation officielle de Lua pour `string.format`: https://www.lua.org/manual/5.4/manual.html#pdf-string.format
- LuaRocks, la gestionnaire de paquets de modules pour Lua, où vous pouvez trouver des bibliothèques d'interpolation : https://luarocks.org/
- Un tutoriel sur `string.gsub`: http://lua-users.org/wiki/StringLibraryTutorial
