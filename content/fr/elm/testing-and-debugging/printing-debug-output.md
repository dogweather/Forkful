---
aliases:
- /fr/elm/printing-debug-output/
date: 2024-01-20 17:52:19.416586-07:00
description: "Qu'est-ce que c'est l'impression de d\xE9bogage ? C\u2019est l\u2019\
  art de balancer des infos dans la console pour comprendre ce qui se passe dans ton\
  \ code. Pourquoi\u2026"
lastmod: 2024-02-18 23:09:08.737104
model: gpt-4-1106-preview
summary: "Qu'est-ce que c'est l'impression de d\xE9bogage ? C\u2019est l\u2019art\
  \ de balancer des infos dans la console pour comprendre ce qui se passe dans ton\
  \ code. Pourquoi\u2026"
title: "Affichage des sorties de d\xE9bogage"
---

{{< edit_this_page >}}

## What & Why? 
Qu'est-ce que c'est l'impression de débogage ? C’est l’art de balancer des infos dans la console pour comprendre ce qui se passe dans ton code. Pourquoi on le fait ? Pour traquer les bogues plus malins qu’un renard et pour saisir le comportement de notre programme en direct.

## How to:
Déboguer dans Elm, c'est simple. Utilise `Debug.log` pour afficher des valeurs. Voici un exemple :

```Elm
import Html exposing (text)
import Debug

main =
  let
    myValue = "Hello, Elm!"
    _ = Debug.log "Debug Output" myValue
  in
    text myValue
```

Résultat dans la console :
```
Debug Output: "Hello, Elm!"
```

La valeur `"Hello, Elm!"` est imprimée avec le label `"Debug Output"`. Facile, non ?

## Deep Dive
Elm a intégré `Debug.log` bien avant que ce soit cool, mais attention, c'est juste pour le développement. Pourquoi ? Elm mise sur la fiabilité, alors `Debug.log` va disparaître dans les builds de production. Autres alternatives ? Pourquoi pas `console.log` de JavaScript via les ports, mais c'est moins élégant et direct. Détail d'implémentation, `Debug.log` prend deux arguments, un tag et une valeur, et retourne la valeur. Comme ça, tu peux l’insérer où tu veux sans casser ton flux de données.

## See Also
- Documentation Elm sur `Debug`: https://package.elm-lang.org/packages/elm/core/latest/Debug
- Guide Elm sur les ports (pour intégrer du `console.log` JS): https://guide.elm-lang.org/interop/ports.html
- Article sur les méthodes de débogage Elm avancées : https://elm-lang.org/news/debugging-elm

Ce sont tes outils. Maintenant, va jouer avec le débogage et rends ton code impeccable !
