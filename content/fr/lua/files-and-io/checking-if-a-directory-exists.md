---
changelog:
- 2024-02-03, gpt-4-0125-preview, translated from English
date: 2024-02-03 19:07:45.810583-07:00
description: "V\xE9rifier si un r\xE9pertoire existe est une op\xE9ration fondamentale\
  \ lors de l'\xE9criture de scripts qui interagissent avec le syst\xE8me de fichiers,\
  \ en s'assurant\u2026"
lastmod: '2024-03-13T22:44:57.952560-06:00'
model: gpt-4-0125-preview
summary: "V\xE9rifier si un r\xE9pertoire existe est une op\xE9ration fondamentale\
  \ lors de l'\xE9criture de scripts qui interagissent avec le syst\xE8me de fichiers,\
  \ en s'assurant que votre programme op\xE8re sur des chemins valides et \xE9vite\
  \ les erreurs li\xE9es aux r\xE9pertoires inexistants."
title: "V\xE9rifier si un r\xE9pertoire existe"
weight: 20
---

## Comment faire :
En Lua, vous n'avez pas de fonction intégrée pour vérifier directement si un répertoire existe, donc vous comptez souvent sur la bibliothèque Lua File System (lfs), une bibliothèque tierce populaire pour les opérations sur les fichiers.

Assurez-vous d'abord d'avoir Lua File System installé. Si ce n'est pas le cas, vous pouvez généralement l'installer en utilisant LuaRocks :

```sh
luarocks install luafilesystem
```

Ensuite, vous pouvez utiliser l'exemple suivant pour vérifier l'existence d'un répertoire :

```lua
local lfs = require "lfs"

function directoryExists(directory)
    local attr = lfs.attributes(directory)
    return attr and attr.mode == "directory"
end

-- Vérifier si un répertoire spécifique existe
if directoryExists("/path/to/your/directory") then
    print("Le répertoire existe.")
else
    print("Le répertoire n'existe pas.")
end
```

Cela affichera :

```
Le répertoire existe.
```

Ou, si le répertoire n'existe pas :

```
Le répertoire n'existe pas.
```

Cette approche utilise la fonction `lfs.attributes` pour obtenir les attributs du chemin. Si le chemin existe et que son attribut `mode` est `directory`, cela confirme l'existence du répertoire.
