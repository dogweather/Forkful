---
date: 2024-01-26 04:39:22.981520-07:00
description: "Les nombres complexes sont une combinaison de nombres r\xE9els et imaginaires,\
  \ comme `a + bi` o\xF9 `i` est la racine carr\xE9e de -1. Ils sont cl\xE9s dans\
  \ des\u2026"
lastmod: '2024-03-13T22:44:57.682422-06:00'
model: gpt-4-0125-preview
summary: "Les nombres complexes sont une combinaison de nombres r\xE9els et imaginaires,\
  \ comme `a + bi` o\xF9 `i` est la racine carr\xE9e de -1."
title: Manipulation des nombres complexes
weight: 14
---

## Comment faire :
Elm n'a pas de support intégré pour les nombres complexes, donc vous allez créer votre propre type et fonctions. Voici une configuration rapide :

```Elm
type alias Complex =
    { real : Float, imaginary : Float }

add : Complex -> Complex -> Complex
add a b =
    { real = a.real + b.real, imaginary = a.imaginary + b.imaginary }

-- Exemple d'utilisation :
a = { real = 3, imaginary = 2 }
b = { real = 1, imaginary = -4 }

somme = add a b
-- somme est { real = 4.0, imaginary = -2.0 }
```

## Exploration Approfondie
Historiquement, les nombres complexes n'ont pas toujours été acceptés. Ils sont devenus un élément transformateur au 16e siècle pour résoudre les équations cubiques. Les alternatives dans d'autres langages comme Python offrent un support intégré pour les nombres complexes avec des opérations directement disponibles. Elm nécessite une approche DIY comme vous l'avez vu. Mais vous pouvez le rendre aussi sophistiqué que nécessaire, en construisant la multiplication, la division, et d'autres opérations, en ajustant les problèmes de performance.

## Voir Aussi
- La Documentation Officielle d'Elm : https://package.elm-lang.org/ pour créer des types personnalisés et maîtriser les bases d'Elm.
- Les passionnés d'histoire des mathématiques pourraient consulter "Une Histoire Imaginaire" de Paul J. Nahin pour un voyage à travers le temps des nombres complexes.
- Plongez dans les défis de programmation orientés maths sur Project Euler (https://projecteuler.net) pour appliquer votre magie des nombres complexes.
