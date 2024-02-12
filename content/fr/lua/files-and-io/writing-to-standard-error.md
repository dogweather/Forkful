---
title:                "Écrire sur l'erreur standard"
date:                  2024-02-03T19:33:45.687361-07:00
model:                 gpt-4-0125-preview
simple_title:         "Écrire sur l'erreur standard"
tag:                  "Files and I/O"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/fr/lua/writing-to-standard-error.md"
changelog:
  - 2024-02-03, gpt-4-0125-preview, translated from English
---

{{< edit_this_page >}}

## Quoi & Pourquoi ?
Écrire dans l'erreur standard (stderr) consiste à diriger les messages d'erreur et les sorties de diagnostic vers un canal distinct, différent de la sortie standard (stdout). Les programmeurs font cela pour différencier les résultats réguliers du programme des informations d'erreur, rationalisant ainsi le débogage et les processus de journalisation.

## Comment faire :
En Lua, l'écriture dans stderr peut être réalisée en utilisant la fonction `io.stderr:write()`. Voici comment vous pouvez écrire un simple message d'erreur dans l'erreur standard :

```lua
io.stderr:write("Erreur : Entrée invalide.\n")
```

Si vous avez besoin de sortir une variable ou de combiner plusieurs morceaux de données, concaténez-les à l'intérieur de la fonction d'écriture :

```lua
local errorMessage = "Entrée invalide."
io.stderr:write("Erreur : " .. errorMessage .. "\n")
```

**Exemple de sortie sur stderr :**
```
Erreur : Entrée invalide.
```

Pour des scénarios plus complexes, ou lorsqu'on travaille avec des applications plus larges, vous pourriez envisager des bibliothèques de journalisation tierces telles que LuaLogging. Avec LuaLogging, vous pouvez diriger les journaux vers différentes destinations, y compris stderr. Voici un bref exemple :

D'abord, assurez-vous que LuaLogging est installé en utilisant LuaRocks :

```
luarocks install lualogging
```

Ensuite, pour écrire un message d'erreur dans stderr en utilisant LuaLogging :

```lua
local logging = require("logging")
local logger = logging.stderr()
logger:error("Erreur : Entrée invalide.")
```

Cette approche offre l'avantage d'une journalisation standardisée à travers votre application, avec la flexibilité ajoutée de définir les niveaux de log (par exemple, ERREUR, AVERTISSEMENT, INFO) grâce à une API simple.
