---
date: 2024-01-26 01:11:19.016616-07:00
description: "Organiser son code en fonctions, c'est fractionner le script en morceaux\
  \ digestes\u2014comme des blocs LEGO fonctionnels. On le fait pour la clart\xE9\
  , la\u2026"
lastmod: '2024-03-13T22:44:57.942309-06:00'
model: gpt-4-1106-preview
summary: "Organiser son code en fonctions, c'est fractionner le script en morceaux\
  \ digestes\u2014comme des blocs LEGO fonctionnels."
title: Organisation du code en fonctions
weight: 18
---

## Comment faire :
```Lua
-- Définir une fonction simple pour saluer
function greet(name)
    return "Bonjour, " .. name .. "!"
end

-- Utiliser la fonction
print(greet("Programmeur Lua")) -- Exemple de sortie : Bonjour, Programmeur Lua!
```

Les fonctions deviennent plus complexes et gèrent diverses tâches :
```Lua
-- Une fonction pour calculer la surface d'un rectangle
function calculateArea(width, height)
    return width * height
end

-- Appeler la fonction et afficher le résultat
local area = calculateArea(5, 4)
print(area)  -- Exemple de sortie : 20
```

## Plongée en profondeur
Lua, depuis ses débuts dans les années 90, a encouragé la conception modulaire. Organiser le code avec des fonctions n'est pas propre à Lua—cela se pratique depuis l'aube des langues de programmation telles que Fortran et Lisp. Les alternatives telles que le code inline et la copie de même code à maintes reprises ne sont pas seulement déconseillées ; elles sont des nids potentiels de bogues.

Dans Lua, les fonctions sont des citoyens de première classe, ce qui signifie qu'elles peuvent être stockées dans des variables, passées en tant qu'arguments, et retournées par d'autres fonctions. Elles sont polyvalentes. La nature mono-threadée de Lua signifie que vous devez garder les fonctions épurées et efficaces pour la performance. Les fonctions peuvent être locales (à portée limitée) ou globales, et comprendre quand utiliser chacune peut faire toute la différence pour l'efficacité de votre script.

## Voir aussi
- Documentation officielle de Lua sur les fonctions : https://www.lua.org/pil/6.html
- Exemples pratiques d'utilisation des fonctions en Lua : https://lua-users.org/wiki/SampleCode
- Pratiques de code propre en Lua : https://github.com/Olivine-Labs/lua-style-guide
