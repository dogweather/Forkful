---
title:                "Lecture des arguments de ligne de commande"
aliases:
- fr/lua/reading-command-line-arguments.md
date:                  2024-01-20T17:56:23.737941-07:00
model:                 gpt-4-1106-preview
simple_title:         "Lecture des arguments de ligne de commande"

tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/lua/reading-command-line-arguments.md"
---

{{< edit_this_page >}}

## What & Why? (Quoi et Pourquoi ?)
Lire les arguments de ligne de commande en Lua, c'est récupérer les infos tapées par l'utilisateur quand il lance votre script. Les programmeurs font ça pour personnaliser le comportement du script selon les besoins de l'utilisateur sans changer le code.

## How to: (Comment faire ?)
```Lua
-- Exemple de base pour lire les arguments de ligne de commande en Lua

-- Affiche tous les arguments passés au script
for i = 1, #arg do
    print(string.format("Argument %d: %s", i, arg[i]))
end

-- Utilisation dans un terminal:
-- lua monscript.lua premier second "troisième argument"
-- Sortie:
-- Argument 1: premier
-- Argument 2: second
-- Argument 3: troisième argument
```

## Deep Dive (Plongée en Profondeur)
Historiquement, Lua n'a pas toujours été cohérent dans la façon de lire les arguments de ligne de commande ; c'est en Lua 5.1 que `arg` a été standardisé. Alternatives ? Des bibliothèques tierces existent mais sont souvent overkill pour des besoins simples. Concernant l'implémentation, les arguments sont accessibles via le tableau `arg` où `arg[0]` est le nom du script et `arg[n]`, n > 0, sont les arguments passés.

## See Also (Voir Aussi)
- Documentation Lua de base: https://www.lua.org/manual/5.4/manual.html#6.1
- Tutoriel plus détaillé sur les scripts Lua: https://www.lua.org/pil/contents.html
- Forum Lua pour demander de l'aide: https://www.lua.org/lua-l.html
