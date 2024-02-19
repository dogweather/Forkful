---
aliases:
- /fr/lua/using-regular-expressions/
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:17:25.104872-07:00
description: "Les expressions r\xE9guli\xE8res en programmation permettent de rechercher\
  \ et de manipuler des cha\xEEnes de caract\xE8res bas\xE9es sur des motifs sp\xE9\
  cifiques. Les\u2026"
lastmod: 2024-02-18 23:09:08.958546
model: gpt-4-0125-preview
summary: "Les expressions r\xE9guli\xE8res en programmation permettent de rechercher\
  \ et de manipuler des cha\xEEnes de caract\xE8res bas\xE9es sur des motifs sp\xE9\
  cifiques. Les\u2026"
title: "Utilisation des expressions r\xE9guli\xE8res"
---

{{< edit_this_page >}}

## Quoi et pourquoi ?

Les expressions régulières en programmation permettent de rechercher et de manipuler des chaînes de caractères basées sur des motifs spécifiques. Les programmeurs les utilisent pour des tâches telles que la validation, la recherche et la manipulation de texte en raison de leur polyvalence et de leur efficacité pour gérer des opérations de chaîne complexes.

## Comment faire :

Lua ne prend pas en charge les expressions régulières nativement de la même manière que des langages comme Perl ou Python. Au lieu de cela, il offre des capacités de correspondance de motifs qui couvrent de nombreux cas d'usage communs des expressions régulières. Cependant, pour un support complet des expressions régulières, on peut utiliser une bibliothèque tierce telle que `lrexlib`.

### Correspondance de motifs basique en Lua :

Lua fournit un système de correspondance de motifs puissant que vous pouvez utiliser pour des substitutions et des recherches simples :

```lua
-- Recherche simple
local str = "Bonjour, Monde !"
if string.find(str, "Monde") then
  print("Correspondance trouvée !")
end
-- Sortie : Correspondance trouvée !

-- Substitution simple
local s = string.gsub("Lua est génial !", "génial", "fantastique")
print(s)
-- Sortie : Lua est fantastique !
```

### Capture de sous-chaînes :

Vous pouvez capturer des parties de la chaîne qui correspondent aux motifs :

```lua
local date = "Aujourd'hui, nous sommes le 17/05/2023."
local d, m, a = string.match(date, "(%d+)/(%d+)/(%d+)")
print("Jour :", d, "Mois :", m, "An :", a)
-- Sortie : Jour : 17 Mois : 05 An : 2023
```

### Utilisation de `lrexlib` pour les expressions régulières :

Pour utiliser de véritables expressions régulières, vous pouvez installer et utiliser `lrexlib`. En supposant que vous l'avez installé (`luarocks install lrexlib-pcre`), vous pouvez réaliser une correspondance de motifs plus complexe :

```lua
local rex = require 'rex_pcre'

local texte = "La pluie en Espagne reste principalement dans la plaine."
local regex = "\\bS\\w+"
local nombre, err = rex.gsub(texte, regex, function(w)
  return w:upper()
end)
if err then
  print("Erreur :", err)
else
  print("Texte modifié :", texte)
  print("Substitutions effectuées :", nombre)
end
-- Exemple de sortie : Texte modifié : La PLUIE en ESPAGNE reste PRINCIPALEMENT dans la plaine.
-- Substitutions effectuées : 3
```

Les exemples ci-dessus illustrent l'utilisation basique au sein du propre système de correspondance de motifs de Lua et comment exploiter la puissance des expressions régulières via `lrexlib`. Que vous effectuiez de simples manipulations de chaînes ou que vous nécessitiez toute la polyvalence des expressions régulières, Lua, couplé à des bibliothèques puissantes, peut répondre à vos besoins.
