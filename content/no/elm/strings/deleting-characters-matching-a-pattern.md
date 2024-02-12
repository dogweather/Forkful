---
title:                "Slette tegn som matcher et mønster"
aliases:
- /no/elm/deleting-characters-matching-a-pattern/
date:                  2024-01-20T17:41:58.077726-07:00
model:                 gpt-4-1106-preview
simple_title:         "Slette tegn som matcher et mønster"

tag:                  "Strings"
editURL:              "https://github.com/dogweather/forkful/blob/master/content/no/elm/deleting-characters-matching-a-pattern.md"
---

{{< edit_this_page >}}

## What & Why?
I Elm handler det om å slette tegn som matcher et mønster for å rense data eller formatere strenger for spesifikke brukstilfeller. Det hjelper å holde dataene konsistente og letter lesbarheten.

## How to:
Elm har ikke innebygd regex, så vi bruker `String` funksjoner for å fjerne spesifikke tegn.

```Elm
import String

removeVowels : String -> String
removeVowels str =
    String.filter (\char -> not (char `elem` "aeiouAEIOU")) str

-- Bruk:
result = removeVowels "Hello, Elm Programmer!"
-- result == "Hll, Elm Prgrmmr!"
```

Output vil være strengen med vokaler fjernet.

## Deep Dive
Elm fokuserer på enkelhet og pålitelighet, så det har ikke med komplekse funksjoner som regex som standard. Historisk sett er dette valget for å unngå de kompleksitetene og potensielle feilene som følger med regex. Istedenfor, bruk `String` funksjoner for å skape custom filtreringslogikk som vist ovenfor. Alternativer inkluderer å lage en Elm Native Module eller bruke ports for å håndtere regex i JavaScript.

## See Also
- Elm String documentation: https://package.elm-lang.org/packages/elm/core/latest/String
- Elm community discussions on string manipulation: https://discourse.elm-lang.org/
- Ports in Elm for advanced manipulation: https://guide.elm-lang.org/interop/ports.html
